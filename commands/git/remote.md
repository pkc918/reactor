# Git Remote

Manage remote repositories.

## Usage

`/remote [action]`

## Commands

```bash
git remote -v                         # list remotes
git remote add <name> <url>           # add remote
git fetch --all --prune               # fetch all, clean stale refs
git push -u origin <branch>           # push and set upstream
git push --force-with-lease           # force push safely
git pull --rebase                     # pull with rebase
```
