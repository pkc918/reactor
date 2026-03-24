# Go Idiomatic Patterns

Common patterns and idiomatic approaches in Go.

## Table of Contents

- [Interface Design](#interface-design)
- [Functional Options](#functional-options)
- [Concurrency](#concurrency)
- [Context](#context)
- [Error Patterns](#error-patterns)
- [Table-Driven Tests](#table-driven-tests)
- [Struct Embedding](#struct-embedding)
- [Graceful Shutdown](#graceful-shutdown)
- [init() and Package Initialization](#init-and-package-initialization)
- [Type Assertion and Type Switch](#type-assertion-and-type-switch)
- [Defer](#defer)

## Interface Design

### Accept interfaces, return structs

Functions should accept the narrowest interface they need and return concrete types. This keeps the API flexible for callers while being precise about what's returned.

```go
// Good — accepts any io.Reader, returns concrete type
func ParseConfig(r io.Reader) (*Config, error) {
    // ...
}

// Bad — accepting concrete type limits callers
func ParseConfig(f *os.File) (*Config, error) {
    // ...
}
```

### Small interfaces

The bigger the interface, the weaker the abstraction. Go's best interfaces are tiny:

```go
type Reader interface {
    Read(p []byte) (n int, err error)
}

type Stringer interface {
    String() string
}
```

Define interfaces where they're consumed, not where they're implemented:

```go
// In the consumer package, not the provider
type UserStore interface {
    GetUser(ctx context.Context, id string) (*User, error)
}
```

## Functional Options

For structs with many optional configuration parameters, use the functional options pattern — it's cleaner than config structs and allows for sensible defaults:

```go
type Server struct {
    addr    string
    timeout time.Duration
    logger  *slog.Logger
}

type Option func(*Server)

func WithTimeout(d time.Duration) Option {
    return func(s *Server) {
        s.timeout = d
    }
}

func WithLogger(l *slog.Logger) Option {
    return func(s *Server) {
        s.logger = l
    }
}

func NewServer(addr string, opts ...Option) *Server {
    s := &Server{
        addr:    addr,
        timeout: 30 * time.Second,     // sensible default
        logger:  slog.Default(),        // sensible default
    }
    for _, opt := range opts {
        opt(s)
    }
    return s
}

// Usage
srv := NewServer(":8080",
    WithTimeout(10*time.Second),
    WithLogger(myLogger),
)
```

## Concurrency

### Goroutines

Start goroutines only when you have a clear plan for how they'll stop. Every goroutine must have a clear exit path — a leaked goroutine is a resource leak.

```go
func process(ctx context.Context) {
    done := make(chan struct{})
    go func() {
        defer close(done)
        // work...
    }()

    select {
    case <-done:
        // completed
    case <-ctx.Done():
        // cancelled
    }
}
```

### Channels

- Use channels for communication, mutexes for state protection
- Prefer unidirectional channel types in function signatures
- The sender closes the channel, never the receiver

```go
func generate(ctx context.Context) <-chan int {
    ch := make(chan int)
    go func() {
        defer close(ch)
        for i := 0; ; i++ {
            select {
            case ch <- i:
            case <-ctx.Done():
                return
            }
        }
    }()
    return ch
}
```

### sync.WaitGroup

Use for waiting on a known number of goroutines:

```go
func processAll(ctx context.Context, items []Item) error {
    var wg sync.WaitGroup
    errs := make(chan error, len(items))

    for _, item := range items {
        wg.Add(1)
        go func() {
            defer wg.Done()
            if err := process(ctx, item); err != nil {
                errs <- err
            }
        }()
    }

    wg.Wait()
    close(errs)

    for err := range errs {
        return err // return first error
    }
    return nil
}
```

### sync.Once

For initialization that must happen exactly once:

```go
var (
    instance *Database
    once     sync.Once
)

func GetDB() *Database {
    once.Do(func() {
        instance = connectDB()
    })
    return instance
}
```

### sync.Mutex

Declare the mutex close to the data it protects:

```go
type SafeCounter struct {
    mu    sync.Mutex
    count map[string]int
}

func (c *SafeCounter) Inc(key string) {
    c.mu.Lock()
    defer c.mu.Unlock()
    c.count[key]++
}
```

Use `sync.RWMutex` when reads vastly outnumber writes.

## Context

Context carries deadlines, cancellation signals, and request-scoped values. It's the backbone of Go's approach to managing goroutine lifecycles.

- First parameter, always named `ctx`
- Never store in a struct (except rare framework cases)
- Propagate from top to bottom — never ignore a context

```go
func HandleRequest(ctx context.Context, req *Request) (*Response, error) {
    ctx, cancel := context.WithTimeout(ctx, 5*time.Second)
    defer cancel()

    result, err := db.Query(ctx, req.Query)
    if err != nil {
        return nil, fmt.Errorf("query: %w", err)
    }
    return &Response{Data: result}, nil
}
```

### Context values

Use sparingly — only for request-scoped data that transits process boundaries (request ID, auth token). Never for function parameters.

```go
type contextKey string

const requestIDKey contextKey = "request_id"

func WithRequestID(ctx context.Context, id string) context.Context {
    return context.WithValue(ctx, requestIDKey, id)
}

func RequestID(ctx context.Context) string {
    id, _ := ctx.Value(requestIDKey).(string)
    return id
}
```

## Error Patterns

### Wrapping and checking

```go
// Wrap with context
if err := sendEmail(to, body); err != nil {
    return fmt.Errorf("notify user %s: %w", to, err)
}

// Check sentinel errors
if errors.Is(err, sql.ErrNoRows) {
    return nil, ErrNotFound
}

// Extract custom error types
var ve *ValidationError
if errors.As(err, &ve) {
    log.Printf("validation failed on field: %s", ve.Field)
}
```

### Error groups (golang.org/x/sync/errgroup)

For running multiple goroutines that can fail:

```go
func fetchAll(ctx context.Context, urls []string) ([][]byte, error) {
    g, ctx := errgroup.WithContext(ctx)
    results := make([][]byte, len(urls))

    for i, url := range urls {
        g.Go(func() error {
            data, err := fetch(ctx, url)
            if err != nil {
                return fmt.Errorf("fetch %s: %w", url, err)
            }
            results[i] = data
            return nil
        })
    }

    if err := g.Wait(); err != nil {
        return nil, err
    }
    return results, nil
}
```

## Table-Driven Tests

The standard Go testing pattern — keeps tests organized, easy to extend, and easy to read:

```go
func TestAdd(t *testing.T) {
    tests := []struct {
        name string
        a, b int
        want int
    }{
        {"positive", 1, 2, 3},
        {"negative", -1, -2, -3},
        {"zero", 0, 0, 0},
        {"mixed", -1, 1, 0},
    }

    for _, tt := range tests {
        t.Run(tt.name, func(t *testing.T) {
            got := Add(tt.a, tt.b)
            if got != tt.want {
                t.Errorf("Add(%d, %d) = %d, want %d", tt.a, tt.b, got, tt.want)
            }
        })
    }
}
```

### Test helpers

Use `t.Helper()` for functions that assist tests — it makes failure messages point to the right line:

```go
func assertEqual(t *testing.T, got, want any) {
    t.Helper()
    if got != want {
        t.Errorf("got %v, want %v", got, want)
    }
}
```

### Testdata

Put test fixtures in a `testdata/` directory — `go build` ignores it automatically.

## Struct Embedding

Embedding promotes the embedded type's methods, giving a form of composition. Use it to reuse behavior, not to model "is-a" relationships.

```go
type Logger struct {
    *slog.Logger
}

// ReadWriter composes Reader and Writer
type ReadWriter struct {
    *Reader
    *Writer
}
```

Be careful: embedding exports all the embedded type's public methods. Only embed when you want that full interface to be part of your type's API.

## Graceful Shutdown

A clean pattern for shutting down HTTP servers and background workers:

```go
func main() {
    srv := &http.Server{Addr: ":8080", Handler: mux}

    go func() {
        if err := srv.ListenAndServe(); err != nil && err != http.ErrServerClosed {
            log.Fatalf("listen: %v", err)
        }
    }()

    // Wait for interrupt signal
    quit := make(chan os.Signal, 1)
    signal.Notify(quit, syscall.SIGINT, syscall.SIGTERM)
    <-quit

    log.Println("shutting down...")
    ctx, cancel := context.WithTimeout(context.Background(), 10*time.Second)
    defer cancel()

    if err := srv.Shutdown(ctx); err != nil {
        log.Fatalf("forced shutdown: %v", err)
    }
    log.Println("server exited")
}
```

## init() and Package Initialization

`init()` runs automatically when a package is imported. Use sparingly — it makes code harder to test and reason about.

Acceptable uses:
- Registering drivers or codecs
- Setting up package-level state that can't fail

```go
func init() {
    sql.Register("mydriver", &MyDriver{})
}
```

Avoid `init()` for anything that can fail or has side effects that tests might not want. Prefer explicit initialization functions instead.

## Type Assertion and Type Switch

```go
// Type assertion — when you know the concrete type
r, ok := val.(io.Reader)
if !ok {
    return errors.New("value does not implement io.Reader")
}

// Type switch — when handling multiple possible types
switch v := val.(type) {
case string:
    fmt.Println("string:", v)
case int:
    fmt.Println("int:", v)
case error:
    fmt.Println("error:", v.Error())
default:
    fmt.Printf("unexpected type: %T\n", v)
}
```

Always use the comma-ok form for type assertions to avoid panics.

## Defer

`defer` schedules a function call to run when the enclosing function returns. Use it for cleanup — files, locks, connections.

```go
func readFile(path string) ([]byte, error) {
    f, err := os.Open(path)
    if err != nil {
        return nil, err
    }
    defer f.Close()

    return io.ReadAll(f)
}
```

Key behaviors:
- Deferred calls execute in LIFO order (last deferred, first called)
- Arguments are evaluated when `defer` is called, not when it executes
- Deferred functions can read and modify named return values

```go
func doWork() (err error) {
    tx, err := db.Begin()
    if err != nil {
        return err
    }
    defer func() {
        if err != nil {
            tx.Rollback()
        } else {
            err = tx.Commit()
        }
    }()

    // work with tx...
    return nil
}
```
