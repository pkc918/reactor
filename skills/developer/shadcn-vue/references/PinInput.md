---
title: Pin Input (shadcn-vue + Reka UI)
description: >-
  Accessible pin input component with copy paste functionality.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/pin-input
  reka-doc: https://reka-ui.com/docs/components/pin-input
  reka-api: https://reka-ui.com/docs/components/pin-input#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add pin-input
# or: npx shadcn-vue@latest add pin-input
# or: yarn dlx shadcn-vue@latest add pin-input
# or: bunx --bun shadcn-vue@latest add pin-input
```

## Usage

```vue
<script setup lang="ts">
</script>

<template>
  <!-- No Usage code block in upstream pin-input.md -->
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a pin. An `input` will also render when used within a `form` to ensure events propagate correctly.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The default value of the pin inputs when it is initially rendered. Use when you do not need to control its checked state. | `string[]` | No | - |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with the pin input | `boolean` | No | - |
| `id` | Id of the element | `string` | No | - |
| `mask` | When true, pin inputs will be treated as password. | `boolean` | No | - |
| `modelValue` | The controlled checked state of the pin input. Can be binded as v-model. | `string[] \| null` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `otp` | When true, mobile devices will autodetect the OTP from messages or clipboard, and enable the autocomplete field. | `boolean` | No | - |
| `placeholder` | The placeholder character to use for empty pin-inputs. | `string` | No | `""` |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `type` | Input type for the inputs. | `"number" \| "text"` | No | `"text" as any` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `complete` |  | `[value: string[]]` |
| `update:modelValue` | Event handler called when the value changes. | `[value: string[]]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `string[]` |

### Input

Input field for Pin Input. You can add as many input as you like.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"input"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the pin input | `boolean` | No | - |
| `index` | Position of the value this input binds to. | `number` | Yes | - |
