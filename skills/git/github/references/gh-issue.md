---
name: gh-issue
description: GitHub issue operations with gh, including list, view, create, comment, close, reopen, labels, and assignees.
---

# gh Issues

Use these commands for GitHub issue operations.

## List

```bash
gh issue list
gh issue list --state open
gh issue list --assignee @me
gh issue list --label <label>
```

## View

```bash
gh issue view <id>
```

Open in browser:

```bash
gh issue view <id> --web
```

## Create

```bash
gh issue create --title "<title>" --body "<body>"
```

With labels or assignee:

```bash
gh issue create --title "<title>" --label <label> --assignee <username>
```

## Comment

```bash
gh issue comment <id> --body "<message>"
```

## Close And Reopen

Close only when explicitly requested:

```bash
gh issue close <id>
```

Reopen only when explicitly requested:

```bash
gh issue reopen <id>
```

## Edit Labels And Assignees

```bash
gh issue edit <id> --add-label <label>
gh issue edit <id> --remove-label <label>
gh issue edit <id> --add-assignee <username>
gh issue edit <id> --remove-assignee <username>
```
