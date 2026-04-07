---
name: git-push
description: Upload commits to a remote and manage upstream
allowed-tools: Bash, Read, Grep
---

# Git Push

Upload local commits to a remote and set or update upstream tracking.

## Usage

`/push [options]`

## Basic

```bash
git push                              # push current branch to its upstream
git push <remote>                     # push to named remote (default upstream branch)
git push <remote> <refspec>           # e.g. git push origin main
git push -u origin <branch>           # push and set upstream (-u = --set-upstream)
```

## Force and lease

```bash
git push --force-with-lease           # overwrite remote only if nobody else pushed (preferred)
git push --force-with-lease origin <branch>
git push -f                           # hard force; can drop others' work — avoid on shared branches
git push --force                      # same as -f
```

Prefer `--force-with-lease` over `-f` / `--force` when rewriting history on a branch others might use.

## Tags and all refs

```bash
git push origin <tag>                 # push one tag
git push origin --tags                # push all local tags
git push --follow-tags                # push commits and annotated tags they point to
git push --all                        # push all branches (use with care)
```

## Delete remote branch or tag

```bash
git push origin --delete <branch>     # remove remote branch
git push origin :<branch>             # older refspec form, same effect
git push origin :refs/tags/<tag>      # delete remote tag
```

## Safety and debugging

```bash
git push --dry-run                    # show what would be pushed
git push -v                           # verbose
git push --no-verify                  # skip pre-push hook (use sparingly)
```

## When push is rejected

- **Non-fast-forward:** remote has commits you lack. Usually `git pull --rebase` (or merge), resolve, then push again.
- **Intentional rewrite:** after `git rebase` / amended commits on a published branch, use `--force-with-lease` if policy allows, not blind `-f`.
