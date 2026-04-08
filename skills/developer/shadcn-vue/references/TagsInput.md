---
title: Tags Input (shadcn-vue + Reka UI)
description: >-
  Tag inputs render tags inside an input, followed by an actual text input.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/tags-input
  reka-doc: https://reka-ui.com/docs/components/tags-input
  reka-api: https://reka-ui.com/docs/components/tags-input#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add tags-input
# or: npx shadcn-vue@latest add tags-input
# or: yarn dlx shadcn-vue@latest add tags-input
# or: bunx --bun shadcn-vue@latest add tags-input
```

## Usage

```vue
<script setup lang="ts">
</script>

<template>
  <!-- No Usage code block in upstream tags-input.md -->
</template>
```

## Reka UI API reference

### Root

Contains all the tags input component parts.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `addOnBlur` | When true allow adding tags blur input | `boolean` | No | - |
| `addOnPaste` | When true, allow adding tags on paste. Work in conjunction with delimiter prop. | `boolean` | No | - |
| `addOnTab` | When true allow adding tags on tab keydown | `boolean` | No | - |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `convertValue` | Convert the input value to the desired type. Mandatory when using objects as values and using TagsInputInput | `((value: string) => AcceptableInputValue)` | No | - |
| `defaultValue` | The value of the tags that should be added. Use when you do not need to control the state of the tags input | `AcceptableInputValue[]` | No | `[]` |
| `delimiter` | The character or regular expression to trigger the addition of a new tag. Also used to split tags for @paste event | `string \| RegExp` | No | `","` |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with the tags input. | `boolean` | No | - |
| `displayValue` | Display the value of the tag. Useful when you want to apply modifications to the value like adding a suffix or when using object as values | `((value: AcceptableInputValue) => string)` | No | `value.toString()` |
| `duplicate` | When true, allow duplicated tags. | `boolean` | No | - |
| `id` |  | `string` | No | - |
| `max` | Maximum number of tags. | `number` | No | `0` |
| `modelValue` | The controlled value of the tags input. Can be bind as v-model. | `AcceptableInputValue[] \| null` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `addTag` | Event handler called when tag is added | `[payload: AcceptableInputValue]` |
| `invalid` | Event handler called when the value is invalid | `[payload: AcceptableInputValue]` |
| `removeTag` | Event handler called when tag is removed | `[payload: AcceptableInputValue]` |
| `update:modelValue` | Event handler called when the value changes | `[payload: AcceptableInputValue[]]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `string \| number \| bigint \| Record<string, any>` |

### Item

The component that contains the tag.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the tags input. | `boolean` | No | - |
| `value` | Value associated with the tags | `string \| number \| bigint \| Record<string, any>` | Yes | - |

### ItemText

The textual part of the tag. Important for accessibility.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### ItemDelete

The button that delete the associate tag.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Input

The input element for the tags input.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"input"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `autoFocus` | Focus on element when mounted. | `boolean` | No | - |
| `maxLength` | Maximum number of character allowed. | `number` | No | - |
| `placeholder` | The placeholder character to use for empty tags input. | `string` | No | - |

### Clear

The button that remove all tags.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
