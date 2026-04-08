---
title: Toggle (shadcn-vue + Reka UI)
description: >-
  A two-state button that can be either on or off.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/toggle
  reka-doc: https://reka-ui.com/docs/components/toggle
  reka-api: https://reka-ui.com/docs/components/toggle#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add toggle
# or: npx shadcn-vue@latest add toggle
# or: yarn dlx shadcn-vue@latest add toggle
# or: bunx --bun shadcn-vue@latest add toggle
```

## Usage

```vue
<script setup lang="ts">
import { Toggle } from '@/components/ui/toggle'
</script>

<template>
  <Toggle>Toggle</Toggle>
</template>
```

## Reka UI API reference

### Root

The toggle.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The pressed state of the toggle when it is initially rendered. Use when you do not need to control its open state. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the toggle. | `boolean` | No | `false` |
| `modelValue` | The controlled pressed state of the toggle. Can be bind as v-model. | `boolean \| null` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value of the toggle changes. | `[value: boolean]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current value | `boolean` |
| `state` | Current state | `"on" \| "off"` |
| `pressed` | Current pressed state | `boolean` |
| `disabled` | Current disabled state | `boolean` |
