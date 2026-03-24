---
name: git-log
description: View commit history and inspect changes
allowed-tools: Bash, Read, Grep
---

# Git Log

View commit history and inspect changes.

## Usage

`/log [options]`

## Common Commands

```bash
git log --oneline --graph         # compact history with branch graph
git log --since="2 weeks ago"     # recent history
git log -p <file>                 # full change history of a file
git show <commit>                 # show a specific commit
git blame <file>                  # who changed each line
```

## Diff

```bash
git diff                          # unstaged changes
git diff --staged                 # staged changes
git diff main..HEAD               # changes since branching from main
```

## Status

```bash
git status                        # working tree status
```
