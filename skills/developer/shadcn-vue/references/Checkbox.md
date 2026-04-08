---
title: Checkbox (shadcn-vue + Reka UI)
description: >-
  A control that allows the user to toggle between checked and not checked.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/checkbox
  reka-doc: https://reka-ui.com/docs/components/checkbox
  reka-api: https://reka-ui.com/docs/components/checkbox#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add checkbox
# or: npx shadcn-vue@latest add checkbox
# or: yarn dlx shadcn-vue@latest add checkbox
# or: bunx --bun shadcn-vue@latest add checkbox
```

## Usage

```vue
<script setup lang="ts">
import { Checkbox } from '@/components/ui/checkbox'
</script>

<template>
  <Checkbox />
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a checkbox. An `input` will also render when used within a `form` to ensure events propagate correctly.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the checkbox when it is initially rendered. Use when you do not need to control its value. | `unknown` | No | - |
| `disabled` | When true, prevents the user from interacting with the checkbox | `boolean` | No | - |
| `falseValue` | The value used when the checkbox is unchecked. Defaults to false. | `unknown` | No | `(() => false) as unknown as undefined` |
| `id` | Id of the element | `string` | No | - |
| `modelValue` | The controlled value of the checkbox. Can be binded with v-model. | `unknown` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `trueValue` | The value used when the checkbox is checked. Defaults to true. | `unknown` | No | `(() => true) as unknown as undefined` |
| `value` | The value given as data when submitted with a name. | `AcceptableValue` | No | `"on"` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value of the checkbox changes. | `[value: unknown]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current value | `unknown` |
| `state` | Current state | `false \| true \| "indeterminate"` |

### Indicator

Renders when the checkbox is in a checked or indeterminate state. You can style this element directly, or you can use it as a wrapper to put an icon into, or both.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |

### Group Root

Wrapper around `CheckboxRoot` to support array of `modelValue`




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the checkbox when it is initially rendered. Use when you do not need to control its value. | `AcceptableValue[]` | No | - |
| `dir` | The direction of navigation between items. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with the checkboxes | `boolean` | No | - |
| `loop` | Whether keyboard navigation should loop around | `boolean` | No | - |
| `modelValue` | The controlled value of the checkbox. Can be binded with v-model. | `AcceptableValue[]` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `orientation` | The orientation of the group. Mainly so arrow navigation is done accordingly (left & right vs. up & down) | `"vertical" \| "horizontal"` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `rovingFocus` | When false, navigating through the items using arrow keys will be disabled. | `boolean` | No | `true` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value of the checkbox changes. | `[value: AcceptableValue[]]` |
