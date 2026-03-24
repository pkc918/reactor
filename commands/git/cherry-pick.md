---
name: git-cherry-pick
description: Apply specific commits from another branch
allowed-tools: Bash, Read, Grep
---

# Git Cherry-Pick

Apply specific commits from another branch.

## Usage

`/cherry-pick <commit>`

## Commands

```bash
git cherry-pick <commit>              # apply a single commit
git cherry-pick <c1> <c2> <c3>       # apply multiple commits
git cherry-pick <start>..<end>        # apply a range of commits
git cherry-pick --no-commit <commit>  # apply changes without committing
```

## Abort

```bash
git cherry-pick --abort
```
