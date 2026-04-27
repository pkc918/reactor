---
name: gitlab
description: GitLab repository workflows and glab CLI usage. Trigger when working with GitLab repos, merge requests, issues, pipelines, releases, or the glab command.
---

# GitLab Skill

Use this skill for GitLab repository tasks, especially when the user mentions GitLab, merge requests, issues, pipelines, releases, or `glab`.

Read the relevant reference based on the user's question:

| Reference | Read when |
|-----------|-----------|
| [glab-context](references/glab-context.md) | Before any repository-specific GitLab action. Covers `glab` availability, auth, repository remote detection, current branch, and working tree checks. |
| [glab-mr](references/glab-mr.md) | Working with GitLab merge requests: list, view, create, checkout, approve, comment, close, reopen, merge, diff, or changes. Examples: "close the MR 102399", "open a draft MR", "check out merge request 17", "merge this MR". |
| [glab-issue](references/glab-issue.md) | Working with GitLab issues: list, view, create, comment, close, reopen, labels, or assignees. |
| [glab-pipeline](references/glab-pipeline.md) | Checking GitLab CI, pipelines, jobs, traces, retries, cancellations, or branch pipeline status. |
| [glab-release](references/glab-release.md) | Listing, viewing, creating, uploading assets to, or deleting GitLab releases. |

## Command Composition

For a direct request such as "close the MR 102399":

1. Read `glab-context` to verify `glab` auth and repository context.
2. Read `glab-mr` to choose the MR close command.
3. Prefer viewing the target first when context is ambiguous: `glab mr view 102399`.
4. Run the requested action only if the user's instruction clearly authorizes it: `glab mr close 102399`.

## Operating Principles

- Prefer `glab` for GitLab API-backed tasks when it is available and authenticated.
- Check context before acting: repository remote, current branch, working tree status, and existing merge request state.
- Use non-interactive commands when possible.
- Never print, commit, or store access tokens.
- Do not push, merge, close issues, rerun pipelines, or create releases unless the user asks for that action.
- When `glab` is unavailable, fall back to plain `git` for repository operations and explain which GitLab-specific action could not be completed.
