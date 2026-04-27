---
name: gh-context
description: gh availability, authentication, repository remote, branch, working tree, and explicit repository checks.
---

# gh Context

Use these checks before repository-specific GitHub actions.

## Availability

```bash
gh --version
```

If `gh` is not installed, explain that GitHub API-backed operations require the GitHub CLI.

## Authentication

```bash
gh auth status
```

If authentication fails, ask the user to authenticate:

```bash
gh auth login
```

Never display, request, or store access tokens directly.

## Repository Context

```bash
git remote -v
git branch --show-current
git status --short
```

Use these checks to identify the GitHub remote, current branch, and uncommitted changes.

## Explicit Repository

When the current directory is not a GitHub repository, or multiple remotes make the target ambiguous, pass the repository explicitly:

```bash
gh pr list --repo <owner>/<repo>
gh issue list --repo <owner>/<repo>
```

## Remote Branch State

If an operation depends on the current branch existing on GitHub, check the upstream:

```bash
git status -sb
```

Push only when the user asks:

```bash
git push -u origin <branch>
```
