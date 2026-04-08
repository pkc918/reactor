---
title: Toggle Group (shadcn-vue + Reka UI)
description: >-
  A set of two-state buttons that can be toggled on or off.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/toggle-group
  reka-doc: https://reka-ui.com/docs/components/toggle-group
  reka-api: https://reka-ui.com/docs/components/toggle-group#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add toggle-group
# or: npx shadcn-vue@latest add toggle-group
# or: yarn dlx shadcn-vue@latest add toggle-group
# or: bunx --bun shadcn-vue@latest add toggle-group
```

## Usage

```vue
<script setup lang="ts">
import { ToggleGroup, ToggleGroupItem } from '@/components/ui/toggle-group'
</script>

<template>
  <ToggleGroup type="multiple">
    <ToggleGroupItem value="a">
      A
    </ToggleGroupItem>
    <ToggleGroupItem value="b">
      B
    </ToggleGroupItem>
    <ToggleGroupItem value="c">
      C
    </ToggleGroupItem>
  </ToggleGroup>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a toggle group.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The default active value of the item(s). Use when you do not need to control the state of the item(s). | `AcceptableValue \| AcceptableValue[]` | No | - |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with the toggle group and all its items. | `boolean` | No | `false` |
| `loop` | When loop and rovingFocus is true, keyboard navigation will loop from last item to first, and vice versa. | `boolean` | No | `true` |
| `modelValue` | The controlled value of the active item(s). Use this when you need to control the state of the items. Can be binded with v-model | `AcceptableValue \| AcceptableValue[]` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `orientation` | The orientation of the component, which determines how focus moves: horizontal for left/right arrows and vertical for up/down arrows. | `"vertical" \| "horizontal"` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `rovingFocus` | When false, navigating through the items using arrow keys will be disabled. | `boolean` | No | `true` |
| `type` | Determines whether a "single" or "multiple" items can be selected at a time. This prop will overwrite the inferred type from modelValue and defaultValue. | `"single" \| "multiple"` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value of the toggle changes. | `[payload: AcceptableValue \| AcceptableValue[]]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current toggle values | `AcceptableValue \| AcceptableValue[] \| undefined` |

### Item

An item in the group.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the toggle. | `boolean` | No | - |
| `value` | A string value for the toggle group item. All items within a toggle group should use a unique value. | `AcceptableValue` | Yes | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current value | `boolean` |
| `state` | Current state | `"on" \| "off"` |
| `pressed` | Current pressed state | `boolean` |
| `disabled` | Current disabled state | `boolean` |
