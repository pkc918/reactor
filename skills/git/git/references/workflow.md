# Workflow Management

## Branch Strategy

Keep `main` stable. Do feature work on short-lived branches.

```
main          ← always deployable
├── feat/xxx  ← new features
├── fix/xxx   ← bug fixes
├── docs/xxx  ← documentation
└── chore/xxx ← maintenance
```

Branch naming: `<type>/<short-description>`, use kebab-case. Examples:
- `feat/user-authentication`
- `fix/login-timeout`
- `chore/upgrade-dependencies`

## Rebase-First Workflow

Prefer rebase over merge to keep history linear and readable.

### Sync with upstream (instead of `git merge main`):
```bash
git fetch origin
git rebase origin/main
```

### Interactive rebase to clean up before PR:
```bash
git rebase -i HEAD~<N>    # squash/reorder last N commits
git rebase -i origin/main # clean up all commits since branching
```

Common interactive rebase commands:
- `pick` — keep the commit as-is
- `reword` — change the commit message
- `squash` — meld into previous commit, combine messages
- `fixup` — meld into previous commit, discard this message
- `drop` — remove the commit entirely

### When NOT to rebase

Never rebase commits that have been pushed to a shared branch and others have based work on. Rebase rewrites history — if someone else has those commits, it will cause divergence.

### PR Merge Strategy

Use squash merge or rebase merge when merging PRs into main:
- **Squash merge**: all commits become one clean commit on main — good for small features/fixes
- **Rebase merge**: preserves the full (cleaned-up) commit history — good when individual commits tell a meaningful story

## Typical Feature Workflow

```bash
# 1. Start from latest main
git fetch origin
git checkout -b feat/my-feature origin/main

# 2. Work, commit often with conventional commits
git add -p
git commit -m "feat: add initial implementation"
git commit -m "test: add unit tests for feature"

# 3. Before PR, sync and clean up
git fetch origin
git rebase origin/main
git rebase -i origin/main   # squash fixup commits, reword if needed

# 4. Push (force-with-lease since we rebased)
git push --force-with-lease origin feat/my-feature

# 5. Create PR, get review, merge via squash or rebase merge

# 6. Clean up
git checkout main
git pull --rebase
git branch -d feat/my-feature
```
