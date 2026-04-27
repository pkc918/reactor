---
name: glab-issue
description: GitLab issue operations with glab, including list, view, create, comment, close, reopen, labels, and assignees.
---

# glab Issues

Use these commands for GitLab issue operations.

## List

```bash
glab issue list
glab issue list --state opened
glab issue list --assignee @me
glab issue list --label <label>
```

## View

```bash
glab issue view <id>
```

Open in browser:

```bash
glab issue view <id> --web
```

## Create

```bash
glab issue create --title "<title>" --description "<description>"
```

With labels or assignee:

```bash
glab issue create --title "<title>" --label <label> --assignee <username>
```

## Comment

```bash
glab issue note <id> --message "<message>"
```

## Close And Reopen

Close only when explicitly requested:

```bash
glab issue close <id>
```

Reopen only when explicitly requested:

```bash
glab issue reopen <id>
```

## Labels And Assignees

```bash
glab issue update <id> --label <label>
glab issue update <id> --unlabel <label>
glab issue update <id> --assignee <username>
```
