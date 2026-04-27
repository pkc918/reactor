---
name: gh-actions
description: GitHub Actions operations with gh, including workflow runs, jobs, logs, reruns, cancellations, and debugging flow.
---

# gh Actions

Use these commands for GitHub Actions and workflow operations.

## Run List

```bash
gh run list
gh run list --branch <branch>
gh run list --workflow <workflow>
```

## Run View

```bash
gh run view <run-id>
```

View logs:

```bash
gh run view <run-id> --log
gh run view <run-id> --log-failed
```

## Jobs

```bash
gh run view <run-id> --json jobs
```

## Watch

```bash
gh run watch <run-id>
```

## Rerun And Cancel

Rerun only when explicitly requested:

```bash
gh run rerun <run-id>
```

Rerun failed jobs only when explicitly requested:

```bash
gh run rerun <run-id> --failed
```

Cancel only when explicitly requested:

```bash
gh run cancel <run-id>
```

## Workflow Dispatch

Trigger workflows only when explicitly requested:

```bash
gh workflow run <workflow>
```

With a branch:

```bash
gh workflow run <workflow> --ref <branch>
```

## Debugging Flow

For failing GitHub Actions:

1. List recent runs with `gh run list --branch <branch>`.
2. View the failing run with `gh run view <run-id>`.
3. Read failed logs with `gh run view <run-id> --log-failed`.
4. Use `gh pr checks <id>` when the failure is tied to a pull request.
