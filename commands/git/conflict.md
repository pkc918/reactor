---
name: git-conflict
description: Resolve merge or rebase conflicts
allowed-tools: Bash, Read, Grep
---

# Git Conflict Resolution

Resolve merge or rebase conflicts.

## Usage

`/conflict`

## Steps

```bash
# 1. See which files conflict
git status

# 2. Edit conflicting files — look for markers:
#    <<<<<<< HEAD
#    (your changes)
#    =======
#    (incoming changes)
#    >>>>>>> branch-name

# 3. Stage resolved files
git add <resolved-file>

# 4. Continue
git rebase --continue         # if rebasing
git merge --continue          # if merging
```

## Abort

```bash
git rebase --abort
git merge --abort
```
