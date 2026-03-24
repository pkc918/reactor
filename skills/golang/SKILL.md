---
name: golang
description: Go coding conventions, idiomatic patterns, and CLI commands reference. Follows Effective Go and Go Code Review Comments strictly. Trigger on any Go-related question — code style, error handling, concurrency, project structure, go mod, testing, etc.
---

# Golang Skill

Go best practices, idiomatic patterns, and toolchain reference. Strictly follows [Effective Go](https://go.dev/doc/effective_go) and [Go Code Review Comments](https://go.dev/wiki/CodeReviewComments).

## How to use this skill

Read the relevant reference file based on the user's question:

### 1. [Rules](../../rules/golang/rules.md)
Read when writing or reviewing Go code — naming, formatting, error handling, documentation, package design.

Covers:
- Naming conventions (MixedCaps, acronyms, interface names)
- Error handling (don't panic, wrap errors, sentinel errors)
- Package design (small, focused, no circular deps)
- Documentation comments (godoc format)
- Import organization and blank imports
- Variable declaration style
- Receiver naming and type

### 2. [Patterns](references/patterns.md)
Read when implementing Go features or asking about idiomatic Go approaches.

Covers:
- Interface design (small interfaces, accept interfaces return structs)
- Concurrency (goroutines, channels, sync primitives, context)
- Error patterns (custom errors, error wrapping, errors.Is/As)
- Functional options pattern
- Table-driven tests
- Struct embedding
- init() and package initialization
- Graceful shutdown

### 3. Commands
Read when the user needs Go build or test commands.

- [go-build](../../commands/go-build.md) — go build, cross-compilation, build tags, ldflags
- [go-test](../../commands/go-test.md) — go test, coverage, benchmarks, fuzzing
