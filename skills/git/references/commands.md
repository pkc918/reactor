# Git Commands Reference

## Table of Contents

- [Setup & Config](#setup--config)
- [Daily Workflow](#daily-workflow)
- [Viewing & Inspecting](#viewing--inspecting)
- [Undoing Things](#undoing-things)
- [Stashing](#stashing)
- [Branching & Merging](#branching--merging)
- [Remote Operations](#remote-operations)
- [Tags](#tags)
- [Conflict Resolution](#conflict-resolution)
- [Cleanup](#cleanup)
- [Advanced](#advanced)

## Setup & Config

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --global pull.rebase true          # default to rebase on pull
git config --global rerere.enabled true       # remember conflict resolutions
```

## Daily Workflow

```bash
# Start new work
git checkout -b feat/my-feature origin/main

# Stage changes
git add <file>                # stage specific file
git add -p                    # stage interactively, hunk by hunk

# Commit
git commit -m "feat: add new feature"

# Sync with upstream
git fetch origin
git rebase origin/main

# Push
git push origin feat/my-feature
git push --force-with-lease   # after rebase (safer than --force)
```

## Viewing & Inspecting

```bash
git status                    # working tree status
git log --oneline --graph     # compact history with branch graph
git log --since="2 weeks ago" # recent history
git diff                      # unstaged changes
git diff --staged             # staged changes
git diff main..HEAD           # changes since branching from main
git show <commit>             # show a specific commit
git blame <file>              # who changed each line
git log -p <file>             # full change history of a file
```

## Undoing Things

```bash
# Unstage a file (keep changes in working tree)
git restore --staged <file>

# Discard working tree changes
git restore <file>

# Undo last commit, keep changes staged
git reset --soft HEAD~1

# Undo last commit, keep changes unstaged
git reset HEAD~1

# Undo last commit, discard changes entirely
git reset --hard HEAD~1

# Create a new commit that reverses a previous one (safe for shared branches)
git revert <commit>

# Recover lost commits / find previous HEAD positions
git reflog
```

## Stashing

```bash
git stash                     # stash working changes
git stash -u                  # include untracked files
git stash list                # list all stashes
git stash pop                 # apply and remove latest stash
git stash apply stash@{N}    # apply specific stash, keep it
git stash drop stash@{N}     # remove specific stash
```

## Branching & Merging

```bash
# Branch management
git branch                    # list local branches
git branch -a                 # list all branches (including remote)
git branch -d <branch>        # delete merged branch
git branch -D <branch>        # force delete branch
git branch -m <old> <new>     # rename branch

# Switching
git checkout <branch>
git switch <branch>           # modern alternative

# Cherry-pick a commit from another branch
git cherry-pick <commit>

# Rebase current branch onto main
git rebase origin/main

# Abort a rebase in progress
git rebase --abort
```

## Remote Operations

```bash
git remote -v                         # list remotes
git remote add <name> <url>           # add remote
git fetch --all --prune               # fetch all remotes, clean stale refs
git push -u origin <branch>           # push and set upstream
git push --force-with-lease           # force push safely (rejects if remote changed)
git pull --rebase                     # pull with rebase instead of merge
```

## Tags

```bash
git tag v1.0.0                        # lightweight tag
git tag -a v1.0.0 -m "Release 1.0.0" # annotated tag
git push origin v1.0.0                # push specific tag
git push origin --tags                # push all tags
git tag -d v1.0.0                     # delete local tag
git push origin --delete v1.0.0       # delete remote tag
```

## Conflict Resolution

When a rebase or merge hits conflicts:

```bash
# 1. See which files conflict
git status

# 2. Edit conflicting files — look for conflict markers:
#    <<<<<<< HEAD
#    (your changes)
#    =======
#    (incoming changes)
#    >>>>>>> branch-name

# 3. After resolving, stage the fixed files
git add <resolved-file>

# 4. Continue
git rebase --continue   # if rebasing
git merge --continue    # if merging

# Or abort if things go wrong
git rebase --abort
git merge --abort
```

## Cleanup

```bash
git gc                                # garbage collect, optimize repo
git prune                             # remove unreachable objects
git clean -fd                         # remove untracked files and directories
git clean -fdn                        # dry run — show what would be removed
git branch --merged | grep -v main | xargs git branch -d  # delete merged branches
```

## Advanced

### Bisect — find which commit introduced a bug
```bash
git bisect start
git bisect bad                        # current commit is bad
git bisect good <commit>              # known good commit
# git will checkout middle commits for you to test
git bisect reset                      # done
```

### Worktrees — work on multiple branches simultaneously
```bash
git worktree add ../feat-branch feat/my-feature
git worktree remove ../feat-branch
```

### Subtree — include another repo as a subdirectory
```bash
git subtree add --prefix=lib/foo <repo-url> main --squash
```

### Patches
```bash
git format-patch HEAD~3               # create patch files for last 3 commits
git am < patch-file.patch             # apply a patch
```
