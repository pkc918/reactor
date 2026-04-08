---
title: Tabs (shadcn-vue + Reka UI)
description: >-
  A set of layered sections of content—known as tab panels—that are displayed one at a time.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/tabs
  reka-doc: https://reka-ui.com/docs/components/tabs
  reka-api: https://reka-ui.com/docs/components/tabs#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add tabs
# or: npx shadcn-vue@latest add tabs
# or: yarn dlx shadcn-vue@latest add tabs
# or: bunx --bun shadcn-vue@latest add tabs
```

## Usage

```vue
<script setup lang="ts">
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
</script>

<template>
  <Tabs default-value="account">
    <TabsList>
      <TabsTrigger value="account">
        Account
      </TabsTrigger>
      <TabsTrigger value="password">
        Password
      </TabsTrigger>
    </TabsList>
    <TabsContent value="account">
      Make changes to your account here.
    </TabsContent>
    <TabsContent value="password">
      Change your password here.
    </TabsContent>
  </Tabs>
</template>
```

## Reka UI API reference

### Root

Contains all the tabs component parts.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `activationMode` | Whether a tab is activated automatically (on focus) or manually (on click). | `"automatic" \| "manual"` | No | `"automatic"` |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the tab that should be active when initially rendered. Use when you do not need to control the state of the tabs | `string \| number` | No | - |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `modelValue` | The controlled value of the tab to activate. Can be bind as v-model. | `string \| number` | No | - |
| `orientation` | The orientation the tabs are laid out. Mainly so arrow navigation is done accordingly (left & right vs. up & down) | `"vertical" \| "horizontal"` | No | `"horizontal"` |
| `unmountOnHide` | When true, the element will be unmounted on closed state. | `boolean` | No | `true` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value changes | `[payload: StringOrNumber]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `string \| number` |

### List

Contains the triggers that are aligned along the edge of the active content.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `loop` | When true, keyboard navigation will loop from last tab to first, and vice versa. | `boolean` | No | `true` |

### Trigger

The button that activates its associated content.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the tab. | `boolean` | No | `false` |
| `value` | A unique value that associates the trigger with a content. | `string \| number` | Yes | - |

### Indicator

The indicator that highlights the current active tab.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

**Methods**

| Name | Description | Type |
| --- | --- | --- |
| `updateIndicatorStyle` |  | `() => void` |

### Content

Contains the content associated with each trigger.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `value` | A unique value that associates the content with a trigger. | `string \| number` | Yes | - |
