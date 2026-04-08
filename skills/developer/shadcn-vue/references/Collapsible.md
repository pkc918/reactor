---
title: Collapsible (shadcn-vue + Reka UI)
description: >-
  An interactive component which expands/collapses a panel.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/collapsible
  reka-doc: https://reka-ui.com/docs/components/collapsible
  reka-api: https://reka-ui.com/docs/components/collapsible#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add collapsible
# or: npx shadcn-vue@latest add collapsible
# or: yarn dlx shadcn-vue@latest add collapsible
# or: bunx --bun shadcn-vue@latest add collapsible
```

## Usage

```vue
<script setup lang="ts">
import {
  Collapsible,
  CollapsibleContent,
  CollapsibleTrigger,
} from '@/components/ui/collapsible'
</script>

<template>
  <Collapsible>
    <CollapsibleTrigger>Can I use this in my project?</CollapsibleTrigger>
    <CollapsibleContent>
      Yes. Free to use for personal and commercial projects. No attribution
      required.
    </CollapsibleContent>
  </Collapsible>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a collapsible




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultOpen` | The open state of the collapsible when it is initially rendered.  Use when you do not need to control its open state. | `boolean` | No | `false` |
| `disabled` | When true, prevents the user from interacting with the collapsible. | `boolean` | No | - |
| `open` | The controlled open state of the collapsible. Can be binded with v-model. | `boolean` | No | - |
| `unmountOnHide` | When true, the element will be unmounted on closed state. | `boolean` | No | `true` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:open` | Event handler called when the open state of the collapsible changes. | `[value: boolean]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `open` | Current open state | `boolean` |

### Trigger

The button that toggles the collapsible

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Content

The component that contains the collapsible content.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `contentFound` |  | `[(void)?]` |
