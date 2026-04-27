---
name: gh-release
description: GitHub release operations with gh, including list, view, create, upload assets, edit, and delete.
---

# gh Releases

Use these commands for GitHub release operations.

## List

```bash
gh release list
```

## View

```bash
gh release view <tag>
```

## Create

Create releases only when explicitly requested:

```bash
gh release create <tag> --notes "<release notes>"
```

Create a release with a title:

```bash
gh release create <tag> --title "<title>" --notes "<release notes>"
```

Create a draft release:

```bash
gh release create <tag> --draft --notes "<release notes>"
```

## Upload Assets

Upload assets only when explicitly requested:

```bash
gh release upload <tag> <file>
```

## Edit

Edit releases only when explicitly requested:

```bash
gh release edit <tag> --title "<title>" --notes "<release notes>"
```

## Delete

Delete releases only when explicitly requested:

```bash
gh release delete <tag>
```
