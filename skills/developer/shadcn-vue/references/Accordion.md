---
title: Accordion (shadcn-vue + Reka UI)
description: >-
  A vertically stacked set of interactive headings that each reveal a section of content.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/accordion
  reka-doc: https://reka-ui.com/docs/components/accordion
  reka-api: https://reka-ui.com/docs/components/accordion#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add accordion
# or: npx shadcn-vue@latest add accordion
# or: yarn dlx shadcn-vue@latest add accordion
# or: bunx --bun shadcn-vue@latest add accordion
```

## Usage

```vue
<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from '@/components/ui/accordion'
</script>

<template>
  <Accordion type="single" collapsible>
    <AccordionItem value="item-1">
      <AccordionTrigger>Is it accessible?</AccordionTrigger>
      <AccordionContent>
        Yes. It adheres to the WAI-ARIA design pattern.
      </AccordionContent>
    </AccordionItem>
  </Accordion>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of an Accordion




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `collapsible` | When type is "single", allows closing content when clicking trigger for an open item. When type is "multiple", this prop has no effect. | `boolean` | No | `false` |
| `defaultValue` | The default active value of the item(s). Use when you do not need to control the state of the item(s). | `string \| string[]` | No | - |
| `dir` | The reading direction of the accordion when applicable. If omitted, assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with the accordion and all its items | `boolean` | No | `false` |
| `modelValue` | The controlled value of the active item(s). Use this when you need to control the state of the items. Can be binded with v-model | `string \| string[]` | No | - |
| `orientation` | The orientation of the accordion. | `"vertical" \| "horizontal"` | No | `"vertical"` |
| `type` | Determines whether a "single" or "multiple" items can be selected at a time. This prop will overwrite the inferred type from modelValue and defaultValue. | `"single" \| "multiple"` | No | - |
| `unmountOnHide` | When true, the element will be unmounted on closed state. | `boolean` | No | `true` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the expanded state of an item changes | `[value: string \| string[]]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current active value | `AcceptableValue \| AcceptableValue[] \| undefined` |

### Item

Contains all the parts of a collapsible section.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | Whether or not an accordion item is disabled from user interaction. When true, prevents the user from interacting with the item. | `boolean` | No | - |
| `unmountOnHide` | When true, the element will be unmounted on closed state. | `boolean` | No | - |
| `value` | A string value for the accordion item. All items within an accordion should use a unique value. | `string` | Yes | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `open` | Current open state | `boolean` |

### Header

Wraps an `AccordionTrigger`. Use the `asChild` prop to update it to the appropriate heading level for your page.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"h3"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Trigger

Toggles the collapsed state of its associated item. It should be nested inside of an `AccordionHeader`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Content

Contains the collapsible content for an item.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
