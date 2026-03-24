---
name: git-branch
description: Manage branches and switching
allowed-tools: Bash, Read, Grep
---

# Git Branch

Manage branches and switching.

## Usage

`/branch [action] [name]`

## Branch Management

```bash
git branch                    # list local branches
git branch -a                 # list all (including remote)
git branch -d <branch>        # delete merged branch
git branch -D <branch>        # force delete branch
git branch -m <old> <new>     # rename branch
```

## Switching

```bash
git checkout <branch>
git switch <branch>           # modern alternative
git checkout -b <branch> origin/main  # create and switch
```

## Naming Convention

Format: `<type>(<short-description>)`, use kebab-case.

```
feat(user-authentication)
fix(login-timeout)
chore(upgrade-dependencies)
docs(api-guide)
```

## Cleanup

```bash
# Delete all merged branches (except main)
git branch --merged | grep -v main | xargs git branch -d
```
