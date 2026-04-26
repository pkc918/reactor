# Reactor

Reactor for AI coding agents — plugins, skills, and marketplace bits for Codex, Claude Code, and friends. Like JARVIS: wire it in and your agent runs with real power.

## Marketplace support

Reactor exposes the same plugin catalog through agent-specific marketplace entrypoints:

- `.codex-plugin/marketplace.json` for Codex
- `.claude-plugin/marketplace.json` for Claude Code

Each plugin keeps agent-specific manifests beside shared plugin resources:

```text
plugins/<name>/
  .codex-plugin/plugin.json
  .claude-plugin/plugin.json
  skills -> ../../skills/<group>
  commands -> ../../commands/<group>
  config -> ../../config/<group>
```

When the Claude and Codex plugin schemas match, the Codex manifest can symlink to the Claude manifest to avoid duplicating metadata. If either agent needs different fields later, replace the symlink with a dedicated manifest for that agent while keeping shared resources in `skills/`, `commands/`, `agents/`, and `config/`.
