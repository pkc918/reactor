---
name: glab-mr
description: GitLab merge request operations with glab, including list, view, create, checkout, comment, approve, close, reopen, merge, diff, and changes.
---

# glab Merge Requests

Use these commands for GitLab merge request operations.

## List

```bash
glab mr list
glab mr list --state opened
glab mr list --assignee @me
glab mr list --source-branch <branch>
```

## View

View the current branch's merge request:

```bash
glab mr view
```

View a specific merge request:

```bash
glab mr view <id>
```

Open in browser:

```bash
glab mr view <id> --web
```

## Create

Create from the current branch:

```bash
glab mr create --fill
```

Create a draft merge request:

```bash
glab mr create --fill --draft
```

Create with explicit target branch:

```bash
glab mr create --fill --target-branch <branch>
```

If the current branch has not been pushed, push only when the user asks:

```bash
git push -u origin <branch>
```

## Checkout

```bash
glab mr checkout <id>
```

## Comment

```bash
glab mr note <id> --message "<message>"
```

## Approve

Approve only when explicitly requested:

```bash
glab mr approve <id>
```

Revoke approval only when explicitly requested:

```bash
glab mr revoke <id>
```

## Close And Reopen

Close only when explicitly requested:

```bash
glab mr close <id>
```

For example, "close the MR 102399" maps to:

```bash
glab mr view 102399
glab mr close 102399
```

Reopen only when explicitly requested:

```bash
glab mr reopen <id>
```

## Merge

Merge only when explicitly requested:

```bash
glab mr merge <id>
```

Common merge options:

```bash
glab mr merge <id> --squash
glab mr merge <id> --remove-source-branch
```

## Review And Diff

```bash
glab mr diff <id>
glab mr changes <id>
```

Use diff or changes commands before reviewing, summarizing, or modifying a merge request.
