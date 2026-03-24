# Git Tag

Create and manage tags for releases.

## Usage

`/tag [action] [name]`

## Create

```bash
git tag v1.0.0                        # lightweight tag
git tag -a v1.0.0 -m "Release 1.0.0" # annotated tag
```

## Push

```bash
git push origin v1.0.0                # push specific tag
git push origin --tags                # push all tags
```

## Delete

```bash
git tag -d v1.0.0                     # delete local tag
git push origin --delete v1.0.0       # delete remote tag
```
