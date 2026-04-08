---
title: Progress (shadcn-vue + Reka UI)
description: >-
  Displays an indicator showing the completion progress of a task, typically displayed as a progress bar.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/progress
  reka-doc: https://reka-ui.com/docs/components/progress
  reka-api: https://reka-ui.com/docs/components/progress#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add progress
# or: npx shadcn-vue@latest add progress
# or: yarn dlx shadcn-vue@latest add progress
# or: bunx --bun shadcn-vue@latest add progress
```

## Usage

```vue
<script setup lang="ts">
import { Progress } from '@/components/ui/progress'
</script>

<template>
  <Progress :model-value="33" />
</template>
```

## Reka UI API reference

### Root

Contains all of the progress parts.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `getValueLabel` | A function to get the accessible label text in a human-readable format. If not provided, the value label will be read as the numeric value as a percentage of the max value. | `((value: number \| null, max: number) => string)` | No | `isNumber(value) ? `${Math.round((value / max) \* DEFAULT\_MAX)}%` : undefined` |
| `getValueText` | A function to get the accessible value text representing the current value in a human-readable format. | `((value: number \| null, max: number) => string)` | No | - |
| `max` | The maximum progress value. | `number` | No | `DEFAULT_MAX` |
| `modelValue` | The progress value. Can be bind as v-model. | `number \| null` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:max` | Event handler called when the max value changes | `[value: number]` |
| `update:modelValue` | Event handler called when the progress value changes | `[value: string[]]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `number \| null \| undefined` |

**Methods**

| Name | Description | Type |
| --- | --- | --- |
| `getValueLabel` | A function to get the accessible label text in a human-readable format. If not provided, the value label will be read as the numeric value as a percentage of the max value. | `(value: number \| null \| undefined, max: number) => string \| undefined` |

### Indicator

Used to show the progress visually. It also makes progress accessible to assistive technologies.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
