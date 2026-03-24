---
name: git-commit
description: Create a commit following Conventional Commits
allowed-tools: Bash, Read, Grep
---

# Git Commit

Create a commit following Conventional Commits specification.

## Usage

`/commit [message]`

## Format

```
<type>(<scope>): <subject>

[optional body]

[optional footer(s)]
```

## Types

| Type       | When to use                                      |
|------------|--------------------------------------------------|
| `feat`     | A new feature                                    |
| `fix`      | A bug fix                                        |
| `docs`     | Documentation only changes                       |
| `style`    | Formatting, missing semicolons, etc. (no logic)  |
| `refactor` | Code change that neither fixes nor adds feature  |
| `perf`     | Performance improvement                          |
| `test`     | Adding or correcting tests                       |
| `build`    | Build system or external dependencies            |
| `ci`       | CI configuration and scripts                     |
| `chore`    | Other changes that don't modify src or test      |
| `revert`   | Reverts a previous commit                        |

## Rules

- **subject**: lowercase, no period, imperative mood ("add" not "added")
- **scope**: optional, area of change (e.g., `auth`, `api`, `ui`)
- **body**: explain *what* and *why*, not *how*
- **breaking changes**: add `!` after type/scope and `BREAKING CHANGE:` footer

## Examples

```
feat(auth): add JWT token refresh mechanism
```

```
fix: resolve race condition in database connection pool
```

```
refactor(api)!: restructure endpoint naming convention

BREAKING CHANGE: all /v1/ endpoints are now under /v2/
```

```
feat(cart): add discount code validation

Validate discount codes against the promotions API before applying.
Expired or invalid codes now return a clear error message instead
of silently failing.

Closes #1234
```
