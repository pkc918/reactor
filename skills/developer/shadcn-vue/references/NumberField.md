---
title: Number Field (shadcn-vue + Reka UI)
description: >-
  A number field allows a user to enter a number and increment or decrement the value using stepper buttons.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/number-field
  reka-doc: https://reka-ui.com/docs/components/number-field
  reka-api: https://reka-ui.com/docs/components/number-field#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add number-field
# or: npx shadcn-vue@latest add number-field
# or: yarn dlx shadcn-vue@latest add number-field
# or: bunx --bun shadcn-vue@latest add number-field
```

## Usage

```vue
<script setup lang="ts">
import {
  NumberField,
  NumberFieldContent,
  NumberFieldDecrement,
  NumberFieldIncrement,
  NumberFieldInput,
} from '@/components/ui/number-field'
</script>

<template>
  <NumberField :default-value="18" :min="0">
    <NumberFieldContent>
      <NumberFieldDecrement />
      <NumberFieldInput />
      <NumberFieldIncrement />
    </NumberFieldContent>
  </NumberField>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a number field. An `input` will also render when used within a `form` to ensure events propagate correctly.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` |  | `number` | No | - |
| `disabled` | When true, prevents the user from interacting with the Number Field. | `boolean` | No | - |
| `disableWheelChange` | When true, prevents the value from changing on wheel scroll. | `boolean` | No | - |
| `focusOnChange` | When true, the input will be focused when the value changes. | `boolean` | No | `true` |
| `formatOptions` | Formatting options for the value displayed in the number field. This also affects what characters are allowed to be typed by the user. | `NumberFormatOptions` | No | - |
| `id` | Id of the element | `string` | No | - |
| `invertWheelChange` | When true, inverts the direction of the wheel change. | `boolean` | No | - |
| `locale` | The locale to use for formatting and currencies | `string` | No | - |
| `max` | The largest value allowed for the input. | `number` | No | - |
| `min` | The smallest value allowed for the input. | `number` | No | - |
| `modelValue` |  | `number \| null` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `readonly` | When true, the Number Field is read-only. | `boolean` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `step` | The amount that the input value changes with each increment or decrement "tick". | `number` | No | `1` |
| `stepSnapping` | When false, prevents the value from snapping to the nearest increment of the step value | `boolean` | No | `true` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value changes. | `[val: number]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` |  | `number \| undefined` |
| `textValue` |  | `string` |
| `readonly` |  | `boolean` |

### Input

Input

The input component that renders the text value based on value and format options.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"input"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Increment

The button that increases the value.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` |  | `boolean` | No | - |

### Decrement

The button that decreases the value.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` |  | `boolean` | No | - |
