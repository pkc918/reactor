# Git Clean

Remove untracked files and optimize repository.

## Usage

`/clean [action]`

## Remove Untracked Files

```bash
git clean -fdn                        # dry run — show what would be removed
git clean -fd                         # remove untracked files and directories
```

## Garbage Collection

```bash
git gc                                # optimize repo
git prune                             # remove unreachable objects
```

## Clear Cache

```bash
git clean -fdx                        # remove untracked + ignored files
```
