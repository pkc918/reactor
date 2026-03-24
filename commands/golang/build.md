# Go Build

Build Go packages and binaries.

## Usage

`/build [flags] [packages]`

## Build

```bash
go build ./...                    # build all packages
go build -o myapp ./cmd/myapp     # custom output name
go run ./cmd/myapp                # build and run directly
go install ./cmd/myapp            # build and install to $GOBIN
```

## Flags

```bash
go build -v ./...                 # verbose — print package names
go build -race ./...              # enable race detector
go build -ldflags "-s -w" ./...   # strip debug info (smaller binary)
go build -tags "integration" ./...                      # build tags
go build -ldflags "-X main.version=1.0.0" ./cmd/myapp   # inject variables
```

## Cross-Compilation

```bash
# Linux
GOOS=linux GOARCH=amd64 go build -o myapp-linux ./cmd/myapp

# Windows
GOOS=windows GOARCH=amd64 go build -o myapp.exe ./cmd/myapp

# macOS ARM
GOOS=darwin GOARCH=arm64 go build -o myapp-darwin ./cmd/myapp

# List all supported platforms
go tool dist list
```

## Build Tags

```go
//go:build linux
//go:build !windows
//go:build integration
```

```bash
go build -tags "integration,debug" ./...
```

## Common Patterns

```bash
# Production build — stripped, with version
go build -ldflags "-s -w -X main.version=$(git describe --tags)" -o myapp ./cmd/myapp

# Build all binaries in cmd/
go build ./cmd/...

# Check if code compiles without producing binary
go build -o /dev/null ./...
```
