---
title: Radio Group (shadcn-vue + Reka UI)
description: >-
  A set of checkable buttons—known as radio buttons—where no more than one of the buttons can be checked at a time.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/radio-group
  reka-doc: https://reka-ui.com/docs/components/radio-group
  reka-api: https://reka-ui.com/docs/components/radio-group#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add radio-group
# or: npx shadcn-vue@latest add radio-group
# or: yarn dlx shadcn-vue@latest add radio-group
# or: bunx --bun shadcn-vue@latest add radio-group
```

## Usage

```vue
<script setup lang="ts">
import { Label } from '@/components/ui/label'
import { RadioGroup, RadioGroupItem } from '@/components/ui/radio-group'
</script>

<template>
  <RadioGroup default-value="comfortable">
    <div class="flex items-center space-x-2">
      <RadioGroupItem id="r1" value="default" />
      <Label for="r1">Default</Label>
    </div>
    <div class="flex items-center space-x-2">
      <RadioGroupItem id="r2" value="comfortable" />
      <Label for="r2">Comfortable</Label>
    </div>
    <div class="flex items-center space-x-2">
      <RadioGroupItem id="r3" value="compact" />
      <Label for="r3">Compact</Label>
    </div>
  </RadioGroup>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a radio group.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the radio item that should be checked when initially rendered. Use when you do not need to control the state of the radio items. | `AcceptableValue` | No | - |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with radio items. | `boolean` | No | `false` |
| `loop` | When true, keyboard navigation will loop from last item to first, and vice versa. | `boolean` | No | `true` |
| `modelValue` | The controlled value of the radio item to check. Can be binded as v-model. | `AcceptableValue` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `orientation` | The orientation of the component. | `"vertical" \| "horizontal"` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | `false` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the radio group value changes | `[payload: AcceptableValue]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `null \| string \| number \| bigint \| Record<string, any>` |

### Item

An item in the group that can be checked. An `input` will also render when used within a `form` to ensure events propagate correctly.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the radio item. | `boolean` | No | `false` |
| `id` |  | `string` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `value` | The value given as data when submitted with a name. | `AcceptableValue` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `select` | Event handler called when the user selects a link (via mouse or keyboard). Calling event.preventDefault in this handler will prevent the navigation menu from closing when selecting that link. | `[event: SelectEvent]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `checked` | Current checked state | `boolean` |
| `required` | Required state | `boolean` |
| `disabled` | Disabled state | `boolean` |

### Indicator

Renders when the radio item is in a checked state. You can style this element directly, or you can use it as a wrapper to put an icon into, or both.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
