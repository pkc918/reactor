---
name: git-stash
description: Temporarily save uncommitted changes
allowed-tools: Bash, Read, Grep
---

# Git Stash

Temporarily save uncommitted changes.

## Usage

`/stash [action]`

## Commands

```bash
git stash                     # stash working changes
git stash -u                  # include untracked files
git stash list                # list all stashes
git stash pop                 # apply and remove latest stash
git stash apply stash@{N}    # apply specific stash, keep it
git stash drop stash@{N}     # remove specific stash
```
