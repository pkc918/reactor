---
name: git
description: Git commit conventions, rebase-first workflow, and commands quick reference. Trigger on any git-related question — commits, branches, rebase, undo, conflicts, etc.
---

# Git Operations Skill

A comprehensive guide for Git operations, commit conventions, and rebase-first workflow management.

## How to use this skill

This skill is organized into three reference files. Read the relevant one based on the user's question:

### 1. [Commit Convention](references/commit-convention.md)
Read when the user needs help with commit messages, asks about commit formats, or is about to make a commit.

Covers:
- Conventional Commits format (`<type>(<scope>): <subject>`)
- Type table (feat, fix, docs, refactor, etc.)
- Rules: lowercase, imperative mood, no period, breaking changes
- Examples of well-formed commit messages

### 2. [Workflow](references/workflow.md)
Read when the user asks about branch strategy, rebase vs merge, PR workflow, or how to organize their Git work.

Covers:
- Branch naming: `<type>/<short-description>` in kebab-case
- Rebase-first workflow (prefer rebase over merge)
- Interactive rebase for cleaning up commits before PR
- When NOT to rebase (shared branches)
- PR merge strategies (squash merge / rebase merge)

### 3. [Commands Reference](references/commands.md)
Read when the user needs a specific Git command, asks "how do I..." for a Git operation, or needs help with a Git error.

Covers:
- Setup & config
- Daily workflow (stage, commit, sync, push)
- Viewing & inspecting (log, diff, blame)
- Undoing things (restore, reset, revert, reflog)
- Stashing
- Branching & merging
- Remote operations
- Tags
- Conflict resolution
- Cleanup & advanced (bisect, worktree, subtree, patches)
