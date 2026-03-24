# Go Coding Rules

Based on [Effective Go](https://go.dev/doc/effective_go) and [Go Code Review Comments](https://go.dev/wiki/CodeReviewComments).

## Table of Contents

- [Formatting](#formatting)
- [Naming](#naming)
- [Documentation](#documentation)
- [Package Design](#package-design)
- [Imports](#imports)
- [Variable Declaration](#variable-declaration)
- [Error Handling](#error-handling)
- [Control Flow](#control-flow)
- [Receiver](#receiver)
- [Don't Panic](#dont-panic)

## Formatting

Use `gofmt`. No exceptions. All Go code in a project should be formatted by `gofmt` — it eliminates style debates entirely.

- Indentation: tabs, not spaces
- Line length: no hard limit, but break long lines for readability
- Braces: opening brace on same line, never on its own line

## Naming

Go's naming conventions are a core part of the language's philosophy. Names are visible across package boundaries and the choice of name carries semantic weight.

### General rules

- **MixedCaps** or **mixedCaps**, never underscores — `ServeHTTP`, not `Serve_HTTP`
- Short names for short scopes: `i` for loop index, `r` for reader, `ctx` for context
- Longer names for larger scopes: package-level variables and exported names should be descriptive
- Don't stutter: `http.Server`, not `http.HTTPServer`

### Acronyms

Acronyms should be all caps or all lower: `URL`, `HTTP`, `ID` — not `Url`, `Http`, `Id`.

```go
// Good
var userID string
type HTTPClient struct{}
func ServeHTTP(w http.ResponseWriter, r *http.Request)

// Bad
var oderId string
type HttpClient struct{}
```

### Interface names

Single-method interfaces use the method name + "er": `Reader`, `Writer`, `Formatter`, `Stringer`.

```go
type Reader interface {
    Read(p []byte) (n int, err error)
}
```

### Getters

Go doesn't provide automatic getter/setter support. If you have a field `owner`, the getter should be `Owner()` (not `GetOwner()`), and the setter should be `SetOwner()`.

```go
// Good
func (o *Object) Owner() string { return o.owner }
func (o *Object) SetOwner(owner string) { o.owner = owner }

// Bad
func (o *Object) GetOwner() string { return o.owner }
```

### Package names

- Lowercase, single-word, no underscores or mixedCaps
- Should be short and clear: `net/http`, `encoding/json`
- Avoid generic names like `util`, `common`, `misc` — they tell the reader nothing
- Package name is part of the type name: `bytes.Buffer`, not `bytes.ByteBuffer`

## Documentation

Every exported name should have a doc comment. This is not optional — it's how godoc generates documentation.

```go
// Package sort provides primitives for sorting slices and user-defined collections.
package sort

// Fprint formats using the default formats for its operands and writes to w.
// Spaces are added between operands when neither is a string.
// It returns the number of bytes written and any write error encountered.
func Fprint(w io.Writer, a ...any) (n int, err error) {
```

Rules:
- Start with the name being declared: `// Fprint formats...`
- Complete sentences, ending with periods
- Package comments: `// Package <name> ...`
- For multi-file packages, the package comment only needs to be in one file

### Deprecation

```go
// Deprecated: Use NewFunction instead.
func OldFunction() {}
```

## Package Design

- Each package should have a single, clear purpose
- No circular imports — if A imports B, B cannot import A
- Keep the public API surface small: export only what consumers need
- Internal packages (`internal/`) restrict visibility to the parent module

### Project layout

```
project/
├── cmd/           ← entry points (main packages)
│   └── myapp/
│       └── main.go
├── internal/      ← private packages
│   ├── service/
│   └── repo/
├── pkg/           ← public libraries (optional, use sparingly)
├── go.mod
└── go.sum
```

## Imports

Group imports in three blocks, separated by blank lines:

```go
import (
    // 1. Standard library
    "context"
    "fmt"
    "net/http"

    // 2. Third-party
    "github.com/gin-gonic/gin"
    "go.uber.org/zap"

    // 3. Local/internal
    "myproject/internal/service"
)
```

### Blank imports

Only use blank imports (`_ "pkg"`) for side effects (e.g., registering drivers), and document why:

```go
import (
    // Register the MySQL driver.
    _ "github.com/go-sql-driver/mysql"
)
```

### Dot imports

Don't use dot imports (`. "pkg"`) except in test files where they can occasionally improve readability.

## Variable Declaration

Use `:=` for local variables when the type is obvious from the right side. Use `var` when zero value matters or the type isn't obvious.

```go
// Short declaration — type is clear
s := "hello"
m := make(map[string]int)
user := NewUser(name)

// var — zero value is meaningful
var count int        // intentionally 0
var err error        // will be assigned later
var mu sync.Mutex    // zero value is valid
```

Don't declare and then assign separately when you can initialize directly:

```go
// Good
users, err := db.Query(ctx, query)

// Bad
var users []User
var err error
users, err = db.Query(ctx, query)
```

## Error Handling

Errors are values — handle them explicitly. This is not bureaucracy; explicit error handling is one of Go's biggest strengths because it forces you to think about failure paths.

### Always check errors

```go
// Good
f, err := os.Open(name)
if err != nil {
    return fmt.Errorf("open config: %w", err)
}

// Bad — silently ignoring errors leads to debugging nightmares
f, _ := os.Open(name)
```

### Wrap errors with context

Use `fmt.Errorf` with `%w` to add context while preserving the error chain:

```go
if err := db.Ping(ctx); err != nil {
    return fmt.Errorf("check database connection: %w", err)
}
```

### Error strings

Error strings should not be capitalized or end with punctuation — they're often composed:

```go
// Good
fmt.Errorf("open file: %w", err)

// Bad
fmt.Errorf("Failed to open file: %w.", err)
```

### Sentinel errors and custom types

```go
// Sentinel errors — for callers to check with errors.Is
var ErrNotFound = errors.New("not found")

// Custom error types — for callers to inspect with errors.As
type ValidationError struct {
    Field   string
    Message string
}

func (e *ValidationError) Error() string {
    return fmt.Sprintf("validation error on %s: %s", e.Field, e.Message)
}
```

### Don't use error as boolean

```go
// Bad — this loses the error information
if err := doSomething(); err != nil {
    return false, nil
}
return true, nil

// Good — propagate the error
if err := doSomething(); err != nil {
    return err
}
```

## Control Flow

### Early return

Reduce nesting by handling errors first and returning early:

```go
// Good
func doWork() error {
    val, err := step1()
    if err != nil {
        return err
    }
    result, err := step2(val)
    if err != nil {
        return err
    }
    return save(result)
}

// Bad — unnecessary nesting
func doWork() error {
    val, err := step1()
    if err == nil {
        result, err := step2(val)
        if err == nil {
            return save(result)
        }
        return err
    }
    return err
}
```

### Don't use `else` after return

```go
// Good
if err != nil {
    return err
}
doSomething()

// Bad
if err != nil {
    return err
} else {
    doSomething()
}
```

## Receiver

### Naming

Use one or two letters based on the type name — consistent within all methods:

```go
// Good
func (s *Server) Start() error
func (s *Server) Stop() error

// Bad
func (srv *Server) Start() error
func (server *Server) Stop() error
func (this *Server) Start() error  // never use "this" or "self"
```

### Value vs pointer

Use pointer receiver when:
- The method modifies the receiver
- The receiver is a large struct
- Consistency: if one method has pointer receiver, all should

Use value receiver when:
- The receiver is a small, immutable value type (e.g., `time.Time`)
- The receiver is a map, func, or chan (already reference types)

Don't mix receiver types on the same struct.

## Don't Panic

`panic` is for truly unrecoverable situations — programming errors, impossible states. Never use it for expected error conditions.

```go
// Good — return errors to the caller
func parseConfig(path string) (*Config, error) {
    data, err := os.ReadFile(path)
    if err != nil {
        return nil, fmt.Errorf("read config: %w", err)
    }
    // ...
}

// Acceptable — fail fast on programmer error during init
func MustCompileRegex(pattern string) *regexp.Regexp {
    re, err := regexp.Compile(pattern)
    if err != nil {
        panic(fmt.Sprintf("invalid regex %q: %v", pattern, err))
    }
    return re
}
```

`Must*` prefix signals to the caller that this function panics on error — use this convention when providing panic variants.
