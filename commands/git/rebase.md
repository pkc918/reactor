# Git Rebase

Rebase current branch onto another. Preferred over merge for keeping linear history.

## Usage

`/rebase [target]`

## Sync with Upstream

```bash
git fetch origin
git rebase origin/main
```

## Interactive Rebase

```bash
git rebase -i HEAD~<N>        # squash/reorder last N commits
git rebase -i origin/main     # clean up all commits since branching
```

Commands:
- `pick` — keep the commit as-is
- `reword` — change the commit message
- `squash` — meld into previous commit, combine messages
- `fixup` — meld into previous commit, discard this message
- `drop` — remove the commit entirely

## After Rebase

```bash
git push --force-with-lease   # safer than --force
```

## Abort

```bash
git rebase --abort
```

## When NOT to Rebase

Never rebase commits that have been pushed to a shared branch and others have based work on. Rebase rewrites history — if someone else has those commits, it will cause divergence.
