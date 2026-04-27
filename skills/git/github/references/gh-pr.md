---
name: gh-pr
description: GitHub pull request operations with gh, including list, view, create, checkout, review, comment, close, reopen, merge, diff, and checks.
---

# gh Pull Requests

Use these commands for GitHub pull request operations.

## List

```bash
gh pr list
gh pr list --state open
gh pr list --assignee @me
gh pr list --head <branch>
```

## View

View the current branch's pull request:

```bash
gh pr view
```

View a specific pull request:

```bash
gh pr view <id>
```

Open in browser:

```bash
gh pr view <id> --web
```

## Create

Create from the current branch:

```bash
gh pr create --fill
```

Create a draft pull request:

```bash
gh pr create --fill --draft
```

Create with explicit base branch:

```bash
gh pr create --fill --base <branch>
```

If the current branch has not been pushed, push only when the user asks:

```bash
git push -u origin <branch>
```

## Checkout

```bash
gh pr checkout <id>
```

## Comment

```bash
gh pr comment <id> --body "<message>"
```

## Review

Approve only when explicitly requested:

```bash
gh pr review <id> --approve
```

Request changes only when explicitly requested:

```bash
gh pr review <id> --request-changes --body "<message>"
```

Comment review only when explicitly requested:

```bash
gh pr review <id> --comment --body "<message>"
```

## Close And Reopen

Close only when explicitly requested:

```bash
gh pr close <id>
```

For example, "close PR 102399" maps to:

```bash
gh pr view 102399
gh pr close 102399
```

Reopen only when explicitly requested:

```bash
gh pr reopen <id>
```

## Merge

Merge only when explicitly requested:

```bash
gh pr merge <id>
```

Common merge options:

```bash
gh pr merge <id> --squash
gh pr merge <id> --rebase
gh pr merge <id> --delete-branch
```

## Diff And Checks

```bash
gh pr diff <id>
gh pr checks <id>
```

Use diff or checks commands before reviewing, summarizing, or debugging a pull request.
