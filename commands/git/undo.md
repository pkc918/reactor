# Git Undo

Undo changes at various stages.

## Usage

`/undo [action]`

## Unstage

```bash
git restore --staged <file>       # unstage, keep working tree changes
```

## Discard Working Changes

```bash
git restore <file>                # discard changes in working tree
```

## Undo Commits

```bash
git reset --soft HEAD~1           # undo commit, keep changes staged
git reset HEAD~1                  # undo commit, keep changes unstaged
git reset --hard HEAD~1           # undo commit, discard changes entirely
```

## Revert (Safe for Shared Branches)

```bash
git revert <commit>               # create a new commit that reverses a previous one
```

## Recover

```bash
git reflog                        # find previous HEAD positions
git checkout <reflog-hash>        # recover lost commit
```
