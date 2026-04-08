---
title: Label (shadcn-vue + Reka UI)
description: >-
  Renders an accessible label associated with controls.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/label
  reka-doc: https://reka-ui.com/docs/components/label
  reka-api: https://reka-ui.com/docs/components/label#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add label
# or: npx shadcn-vue@latest add label
# or: yarn dlx shadcn-vue@latest add label
# or: bunx --bun shadcn-vue@latest add label
```

## Usage

```vue
<script setup lang="ts">
import { Label } from '@/components/ui/label'
</script>

<template>
  <Label for="email">Your email address</Label>
</template>
```

## Reka UI API reference

### Root

Contains the content for the label.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"label"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `for` | The id of the element the label is associated with. | `string` | No | - |
