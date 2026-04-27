---
name: github
description: GitHub repository workflows and gh CLI usage. Trigger when working with GitHub repos, pull requests, issues, Actions, releases, or the gh command.
---

# GitHub Skill

Use this skill for GitHub repository tasks, especially when the user mentions GitHub, pull requests, issues, Actions, releases, or `gh`.

Read the relevant reference based on the user's question:

| Reference | Read when |
|-----------|-----------|
| [gh-context](references/gh-context.md) | Before any repository-specific GitHub action. Covers `gh` availability, auth, repository remote detection, current branch, and working tree checks. |
| [gh-pr](references/gh-pr.md) | Working with GitHub pull requests: list, view, create, checkout, review, comment, close, reopen, merge, diff, or checks. Examples: "close PR 102399", "open a draft PR", "check out pull request 17", "merge this PR". |
| [gh-issue](references/gh-issue.md) | Working with GitHub issues: list, view, create, comment, close, reopen, labels, or assignees. |
| [gh-actions](references/gh-actions.md) | Checking GitHub Actions, workflow runs, jobs, logs, reruns, cancellations, or branch check status. |
| [gh-release](references/gh-release.md) | Listing, viewing, creating, uploading assets to, or deleting GitHub releases. |

## Command Composition

For a direct request such as "close PR 102399":

1. Read `gh-context` to verify `gh` auth and repository context.
2. Read `gh-pr` to choose the PR close command.
3. Prefer viewing the target first when context is ambiguous: `gh pr view 102399`.
4. Run the requested action only if the user's instruction clearly authorizes it: `gh pr close 102399`.

## Operating Principles

- Prefer `gh` for GitHub API-backed tasks when it is available and authenticated.
- Check context before acting: repository remote, current branch, working tree status, and existing pull request state.
- Use non-interactive commands when possible.
- Never print, commit, or store access tokens.
- Do not push, merge, close issues, rerun workflows, or create releases unless the user asks for that action.
- When `gh` is unavailable, fall back to plain `git` for repository operations and explain which GitHub-specific action could not be completed.
