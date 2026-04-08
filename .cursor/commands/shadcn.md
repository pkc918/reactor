# Generate shadcn-vue component skill (reference)

When this command runs, **generate or refresh** a project skill reference for one or more [shadcn/vue](https://shadcn-vue.com/docs) components.

**Sources**

1. **shadcn-vue** — `https://shadcn-vue.com/docs/components/<slug>`  
   Use **Installation** and **Usage** (and the short **one-line intro** under the component title, if present).  
   The docs page often shows **one** package manager per tab; you must still emit **all** supported CLIs in the generated file (see **Installation — all package managers** below).
2. **Reka UI** — only if it exists: `https://reka-ui.com/docs/components/<slug>#api-reference`  
   Optional LLM-friendly source: `https://reka-ui.com/docs/components/<slug>.md` (same slug; skip if 404).

## Inputs

- **`<slug>`** — URL segment (e.g. `accordion`, `alert-dialog`).
- **Component display name** — PascalCase for `title` and filename (e.g. `Accordion`, `Alert`).

Infer `<slug>` from the user’s component name when omitted.

## Output location (this repo)

- **Path:** `skills/developer/shadcn-vue/references/<ComponentName>.md`  
- **Filename spelling** must be correct (e.g. `Accordion.md`, not `Accrodion.md`).

Only update `skills/developer/shadcn-vue/SKILL.md` if the user explicitly asks.

## Installation — all package managers

In **`## Installation`**, always include **every** install style the shadcn-vue CLI documents (typically **pnpm**, **npm**, **yarn**, **bun**). Do **not** output only the tab visible in a fetched HTML snapshot.

Use **one** `bash` fenced block: first line the primary command (use **`pnpm dlx`** as the main line unless the official page explicitly standardizes on another), then `# or:` comment lines for the other managers. Replace `<slug>` with the component slug:

```bash
pnpm dlx shadcn-vue@latest add <slug>
# or: npx shadcn-vue@latest add <slug>
# or: yarn dlx shadcn-vue@latest add <slug>
# or: bunx --bun shadcn-vue@latest add <slug>
```

If the fetched shadcn-vue **Installation** section uses different wording for any manager (e.g. `npx` flags), align that line with the live docs but **still list all four** variants in the same block.

## Frontmatter (YAML)

- **`title`:** `<ComponentName> (shadcn-vue + Reka UI)` when Reka has an API page; otherwise `<ComponentName> (shadcn-vue)`.
- **`description`:** **Only** the component’s **tagline / subtitle** from the shadcn-vue doc page (the brief line under the heading, e.g. “Displays a callout for user attention.”). **Do not** expand with shadcn-vs-Reka explanations, “when to use” bullets, or extra sentences.
- **`component: true`**
- **`links`:** include `shadcn-vue` always. Add `reka-doc` / `reka-api` **only** when the Reka page exists (not 404).

Example when Reka exists:

```yaml
---
title: Accordion (shadcn-vue + Reka UI)
description: >-
  A vertically stacked set of interactive headings that each reveal a section of content.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/accordion
  reka-doc: https://reka-ui.com/docs/components/accordion
  reka-api: https://reka-ui.com/docs/components/accordion#api-reference
---
```

Example when Reka does **not** exist (no `api-reference`):

```yaml
---
title: Alert (shadcn-vue)
description: >-
  Displays a callout for user attention.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/alert
---
```

## Body — when Reka has **no** `api-reference` (missing or 404)

Include **nothing else** beyond frontmatter and these two sections, in this order:

1. **`## Installation`** — follow **Installation — all package managers** above (always **four** variants in one `bash` block, not a single tab).
2. **`## Usage`** — copy the **Usage** block from shadcn-vue (imports + template).

**Do not** add: “What this is”, Reka disclaimers, extended demos, source maps, official links lists, accessibility tables, or any subsection not copied from Installation/Usage.

## Body — when Reka **has** `api-reference`

After the same **`## Installation`** and **`## Usage`** (shadcn-vue only, as above), add **`## Reka UI API reference`** with the content from Reka’s API Reference (tables/sections as in the source). **Do not** add optional extras unless the user asks: no separate “What this is”, anatomy section, cheat sheets, pattern dumps, a11y tables, source-map tables, or “Official documentation” link lists.

## Rules

- **`## Installation`:** must include **pnpm, npm, yarn, and bun** (or every variant the official shadcn-vue install UI lists, if it ever adds more)—never only one command.
- **Do not invent** props or events; only what appears in the fetched docs (or project-generated `components/ui/<slug>` if the user points you there).
- **Normalize** code fences (`vue`, `bash`, `yaml`).
- **Many components:** one file per slug; do not merge unrelated components.

## Quick URL template

| Piece | URL |
|--------|-----|
| shadcn-vue | `https://shadcn-vue.com/docs/components/<slug>` |
| Reka API | `https://reka-ui.com/docs/components/<slug>#api-reference` |

**Example:** [Accordion — shadcn/vue](https://shadcn-vue.com/docs/components/accordion) + [Reka Accordion API](https://reka-ui.com/docs/components/accordion#api-reference). **Alert** has no Reka page → frontmatter + Installation + Usage only.
