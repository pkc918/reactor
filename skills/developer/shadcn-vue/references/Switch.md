---
title: Switch (shadcn-vue + Reka UI)
description: >-
  A control that allows the user to toggle between checked and not checked.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/switch
  reka-doc: https://reka-ui.com/docs/components/switch
  reka-api: https://reka-ui.com/docs/components/switch#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add switch
# or: npx shadcn-vue@latest add switch
# or: yarn dlx shadcn-vue@latest add switch
# or: bunx --bun shadcn-vue@latest add switch
```

## Usage

```vue
<script setup lang="ts">
import { Switch } from '@/components/ui/switch'
</script>

<template>
  <Switch />
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a switch. An `input` will also render when used within a `form` to ensure events propagate correctly.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The state of the switch when it is initially rendered. Use when you do not need to control its state. | `unknown` | No | - |
| `disabled` | When true, prevents the user from interacting with the switch. | `boolean` | No | - |
| `falseValue` | The value used when the switch is off. Defaults to false. | `unknown` | No | `(() => false) as unknown as undefined` |
| `id` |  | `string` | No | - |
| `modelValue` | The controlled state of the switch. Can be bind as v-model. | `unknown` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `trueValue` | The value used when the switch is on. Defaults to true. | `unknown` | No | `(() => true) as unknown as undefined` |
| `value` | The value given as data when submitted with a name. | `string` | No | `"on"` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value of the switch changes. | `[payload: unknown]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current value | `unknown` |
| `checked` | Whether the switch is checked | `boolean` |

### Thumb

The thumb that is used to visually indicate whether the switch is on or off.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
