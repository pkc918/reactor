# Reactor

**English** | [中文](README_ZH.md)

**Reactor** is named after Iron Man's arc reactor. It is not a single tool, but the core energy source that keeps an **AI Agent** running. For one-person companies and indie builders, Reactor is the **AI agent reactor** for building products: it turns **PM, product development, maintenance, design, release, and marketing** workflows into reusable **plugins, skills, commands, rules, agents, and MCP/LSP configuration** that Codex, Claude Code, and other AI coding agents can install and use on demand.

## Quick Start

### Codex Installation

Use [codex-marketplace](https://www.codex-marketplace.com/docs) to install plugins from this GitHub repository.

<details>
<summary>Install all Codex plugins</summary>

```bash
npx codex-marketplace add pkc918/reactor --plugins --global
```

</details>

<details>
<summary>Install into the current project only</summary>

```bash
npx codex-marketplace add pkc918/reactor --plugins --project
```

</details>

<details>
<summary>Install a single Codex plugin</summary>

```bash
npx codex-marketplace add pkc918/reactor/plugins/git --plugin --global
npx codex-marketplace add pkc918/reactor/plugins/developer --plugin --global
npx codex-marketplace add pkc918/reactor/plugins/designer --plugin --global
```

</details>

Restart Codex, or open a new Codex session after installation.

### Claude Code Installation

<details>
<summary>Install the full Claude Code marketplace from GitHub</summary>

```bash
/plugin marketplace add pkc918/reactor
```

</details>

<details>
<summary>Install specific Claude Code plugins</summary>

```bash
/plugin install pkc918/reactor/plugins/git
/plugin install pkc918/reactor/plugins/developer
/plugin install pkc918/reactor/plugins/designer
```

</details>

<details>
<summary>Install plugins from a local checkout</summary>

```bash
/plugin install ./plugins/git
/plugin install ./plugins/developer
/plugin install ./plugins/designer
```

</details>

## Features

### Plugins

| Plugin | Path | Capabilities |
|--------|------|--------------|
| `git` | [`plugins/git`](plugins/git) | Git workflows, GitHub `gh`, GitLab `glab`, and command references for commit / branch / rebase / conflict workflows |
| `developer` | [`plugins/developer`](plugins/developer) | Go backend guidance, project structure, shadcn-vue component references, MCP / LSP / hooks configuration |
| `designer` | [`plugins/designer`](plugins/designer) | Apple Design style, layout, color, motion, and component design principles |

### Skills

| Skill | Plugin | Path | Use case |
|-------|--------|------|----------|
| `git` | `git` | [`skills/git/git`](skills/git/git) | Git commit, branch, rebase, stash, undo, conflict, remote, and tag workflows |
| `github` | `git` | [`skills/git/github`](skills/git/github) | GitHub repositories, pull requests, issues, Actions, releases, and `gh` CLI command composition |
| `gitlab` | `git` | [`skills/git/gitlab`](skills/git/gitlab) | GitLab repositories, merge requests, issues, pipelines, releases, and `glab` CLI command composition |
| `golang` | `developer` | [`skills/developer/golang`](skills/developer/golang) | Go conventions, Effective Go, error handling, concurrency, testing, and module management |
| `backend` | `developer` | [`skills/developer/backend`](skills/developer/backend) | Go backend project structure, layer responsibilities, naming, and module organization |
| `shadcn-vue` | `developer` | [`skills/developer/shadcn-vue`](skills/developer/shadcn-vue) | shadcn-vue / Reka UI component installation, usage, and API references |
| `apple design` | `designer` | [`skills/designer/apple`](skills/designer/apple) | Apple-style UI design, hierarchy, layout, color, typography, motion, and component principles |

## Project Structure

```text
.
├── .codex-plugin/           # Codex marketplace entrypoint
├── .claude-plugin/          # Claude Code marketplace entrypoint
├── agents/                  # Agent role definitions, such as frontend / backend / cr / designer
├── commands/                # Slash-command style docs, such as git-commit and git-rebase
├── config/                  # MCP, LSP, and hooks configuration
├── plugins/                 # Publishable plugins, each with its own manifest
│   ├── git/
│   ├── developer/
│   └── designer/
├── rules/                   # Coding conventions, such as Go rules
├── scripts/                 # Generation scripts and maintenance tools
└── skills/                  # AI Agent Skills and references
    ├── git/
    ├── developer/
    └── designer/
```

## License

This project is licensed under [Apache-2.0](LICENSE).
