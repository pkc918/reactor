---
title: Slider (shadcn-vue + Reka UI)
description: >-
  An input where the user selects a value from within a given range.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/slider
  reka-doc: https://reka-ui.com/docs/components/slider
  reka-api: https://reka-ui.com/docs/components/slider#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add slider
# or: npx shadcn-vue@latest add slider
# or: yarn dlx shadcn-vue@latest add slider
# or: bunx --bun shadcn-vue@latest add slider
```

## Usage

```vue
<script setup lang="ts">
import { Slider } from '@/components/ui/slider'
</script>

<template>
  <Slider :default-value="[33]" :max="100" :step="1" />
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a slider. It will render an `input` for each thumb when used within a `form` to ensure events propagate correctly.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the slider when initially rendered. Use when you do not need to control the state of the slider. | `number[]` | No | `[0]` |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with the slider. | `boolean` | No | `false` |
| `inverted` | Whether the slider is visually inverted. | `boolean` | No | `false` |
| `max` | The maximum value for the range. | `number` | No | `100` |
| `min` | The minimum value for the range. | `number` | No | `0` |
| `minStepsBetweenThumbs` | The minimum permitted steps between multiple thumbs. | `number` | No | `0` |
| `modelValue` | The controlled value of the slider. Can be bind as v-model. | `number[] \| null` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `orientation` | The orientation of the slider. | `"vertical" \| "horizontal"` | No | `"horizontal"` |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `step` | The stepping interval. | `number` | No | `1` |
| `thumbAlignment` | The alignment of the slider thumb.  contain: thumbs will be contained within the bounds of the track. overflow: thumbs will not be bound by the track. No extra offset will be added. | `"contain" \| "overflow"` | No | `"contain"` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the slider value changes | `[payload: number[]]` |
| `valueCommit` | Event handler called when the value changes at the end of an interaction. Useful when you only need to capture a final value e.g. to update a backend service. | `[payload: number[]]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current slider values | `number[] \| null` |

### Track

The track that contains the `SliderRange`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Range

The range part. Must live inside `SliderTrack`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Thumb

A draggable thumb. You can render multiple thumbs.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
