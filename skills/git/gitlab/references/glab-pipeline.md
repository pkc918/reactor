---
name: glab-pipeline
description: GitLab CI and pipeline operations with glab, including status, list, view, jobs, retry, cancel, and debugging flow.
---

# glab Pipelines

Use these commands for GitLab CI and pipeline operations.

## Status

Current branch CI status:

```bash
glab ci status
```

## List

```bash
glab pipeline list
glab pipeline list --branch <branch>
```

## View

```bash
glab pipeline view <id>
```

View the current pipeline in an interactive terminal UI:

```bash
glab pipeline ci view
```

## Jobs

```bash
glab ci list
glab ci view <job-id>
```

## Retry And Cancel

Retry only when explicitly requested:

```bash
glab pipeline retry <id>
```

Cancel only when explicitly requested:

```bash
glab pipeline cancel <id>
```

## Debugging Flow

For failing CI:

1. Check current branch status with `glab ci status`.
2. List recent pipelines with `glab pipeline list --branch <branch>`.
3. View the failing pipeline with `glab pipeline view <id>`.
4. Inspect failing jobs with `glab ci view <job-id>`.
