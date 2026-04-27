---
name: glab-context
description: glab availability, authentication, repository remote, branch, working tree, and explicit repository checks.
---

# glab Context

Use these checks before repository-specific GitLab actions.

## Availability

```bash
glab --version
```

If `glab` is not installed, explain that GitLab API-backed operations require the GitLab CLI.

## Authentication

```bash
glab auth status
```

If authentication fails, ask the user to authenticate:

```bash
glab auth login
```

Never display, request, or store access tokens directly.

## Repository Context

```bash
git remote -v
git branch --show-current
git status --short
```

Use these checks to identify the GitLab remote, current branch, and uncommitted changes.

## Explicit Repository

When the current directory is not a GitLab repository, or multiple remotes make the target ambiguous, pass the repository explicitly when supported:

```bash
glab mr list --repo <owner>/<repo>
glab issue list --repo <owner>/<repo>
```

## Remote Branch State

If an operation depends on the current branch existing on GitLab, check the upstream:

```bash
git status -sb
```

Push only when the user asks:

```bash
git push -u origin <branch>
```
