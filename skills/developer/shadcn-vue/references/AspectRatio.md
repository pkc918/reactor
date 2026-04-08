---
title: Aspect Ratio (shadcn-vue + Reka UI)
description: >-
  Displays content within a desired ratio.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/aspect-ratio
  reka-doc: https://reka-ui.com/docs/components/aspect-ratio
  reka-api: https://reka-ui.com/docs/components/aspect-ratio#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add aspect-ratio
# or: npx shadcn-vue@latest add aspect-ratio
# or: yarn dlx shadcn-vue@latest add aspect-ratio
# or: bunx --bun shadcn-vue@latest add aspect-ratio
```

## Usage

```vue
<script lang="ts">
import { AspectRatio } from '@/components/ui/aspect-ratio'
</script>

<template>
  <AspectRatio :ratio="16 / 9">
    <img src="..." alt="Image" class="rounded-md object-cover">
  </AspectRatio>
</template>
```

## Reka UI API reference

### Root

Contains the content you want to constrain to a given ratio.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `ratio` | The desired ratio. Eg: 16/9 | `number` | No | `1` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `aspect` | Current aspect ratio (in %) | `number` |
