---
name: glab-release
description: GitLab release operations with glab, including list, view, create, upload assets, and delete.
---

# glab Releases

Use these commands for GitLab release operations.

## List

```bash
glab release list
```

## View

```bash
glab release view <tag>
```

## Create

Create releases only when explicitly requested:

```bash
glab release create <tag> --notes "<release notes>"
```

Create a release with a title:

```bash
glab release create <tag> --name "<title>" --notes "<release notes>"
```

## Upload Assets

Upload assets only when explicitly requested:

```bash
glab release upload <tag> <file>
```

## Delete

Delete releases only when explicitly requested:

```bash
glab release delete <tag>
```
