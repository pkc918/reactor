---
title: Separator (shadcn-vue + Reka UI)
description: >-
  Visually or semantically separates content.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/separator
  reka-doc: https://reka-ui.com/docs/components/separator
  reka-api: https://reka-ui.com/docs/components/separator#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add separator
# or: npx shadcn-vue@latest add separator
# or: yarn dlx shadcn-vue@latest add separator
# or: bunx --bun shadcn-vue@latest add separator
```

## Usage

```vue
<script setup lang="ts">
import { Separator } from '@/components/ui/separator'
</script>

<template>
  <div>
    <div class="space-y-1">
      <h4 class="text-sm font-medium leading-none">
        Radix Primitives
      </h4>
      <p class="text-sm text-muted-foreground">
        An open-source UI component library.
      </p>
    </div>
    <Separator class="my-4" />
    <div class="flex h-5 items-center space-x-4 text-sm">
      <div>Blog</div>
      <Separator orientation="vertical" />
      <div>Docs</div>
      <Separator orientation="vertical" />
      <div>Source</div>
    </div>
  </div>
</template>
```

## Reka UI API reference

### Root

The separator.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `decorative` | Whether or not the component is purely decorative. When true, accessibility-related attributes are updated so that that the rendered element is removed from the accessibility tree. | `boolean` | No | - |
| `orientation` | Orientation of the component. Either vertical or horizontal. Defaults to horizontal. | `"vertical" \| "horizontal"` | No | `"horizontal"` |
