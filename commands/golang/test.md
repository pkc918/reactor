---
name: go-test
description: Run Go tests with coverage, benchmarks, and fuzzing
allowed-tools: Bash, Read, Grep
---

# Go Test

Run Go tests with coverage, benchmarks, and fuzzing.

## Usage

`/test [flags] [packages]`

## Run Tests

```bash
go test ./...                     # all packages
go test -v ./...                  # verbose output
go test -run TestName ./pkg/...   # specific test by regex
go test -short ./...              # skip long-running tests
go test -count=1 ./...            # disable test caching
go test -race ./...               # enable race detector
go test -parallel 4 ./...         # max parallel tests
go test -timeout 30s ./...        # set timeout
```

## Coverage

```bash
go test -cover ./...                          # show percentage
go test -coverprofile=coverage.out ./...      # write profile
go tool cover -html=coverage.out              # open in browser
go tool cover -func=coverage.out              # per-function summary
```

## Benchmarks

```bash
go test -bench=. ./...                        # run all benchmarks
go test -bench=BenchmarkName ./pkg/...        # specific benchmark
go test -bench=. -benchmem ./...              # include memory stats
go test -bench=. -count=5 ./...               # run N times
go test -bench=. -benchtime=5s ./...          # set duration
```

## Fuzzing

```bash
go test -fuzz=FuzzName ./pkg/...              # run fuzzer
go test -fuzz=FuzzName -fuzztime=30s ./...    # run for 30 seconds
```

## Common Patterns

```bash
# Run tests with race detector and coverage
go test -race -cover ./...

# Run a specific subtest
go test -run TestName/SubTest ./pkg/...

# Generate coverage report and open
go test -coverprofile=coverage.out ./... && go tool cover -html=coverage.out

# Clean test cache before running
go clean -testcache && go test ./...
```
