---
title: Resizable (shadcn-vue + Reka UI)
description: >-
  Accessible resizable panel groups and layouts with keyboard support.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/resizable
  reka-doc: https://reka-ui.com/docs/components/splitter
  reka-api: https://reka-ui.com/docs/components/splitter#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add resizable
# or: npx shadcn-vue@latest add resizable
# or: yarn dlx shadcn-vue@latest add resizable
# or: bunx --bun shadcn-vue@latest add resizable
```

## Usage

```vue
<script setup lang="ts">
import {
  ResizableHandle,
  ResizablePanel,
  ResizablePanelGroup,
} from '@/components/ui/resizable'
</script>

<template>
  <ResizablePanelGroup direction="horizontal">
    <ResizablePanel>One</ResizablePanel>
    <ResizableHandle />
    <ResizablePanel>Two</ResizablePanel>
  </ResizablePanelGroup>
</template>
```

## Reka UI API reference

### Group

Contains all the parts of a Splitter.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `autoSaveId` | Unique id used to auto-save group arrangement via localStorage. | `string \| null` | No | `null` |
| `direction` | The group orientation of splitter. | `"vertical" \| "horizontal"` | Yes | - |
| `id` | Group id; falls back to useId when not provided. | `string \| null` | No | - |
| `keyboardResizeBy` | Step size when arrow key was pressed. | `number \| null` | No | `10` |
| `storage` | Custom storage API; defaults to localStorage | `PanelGroupStorage` | No | `defaultStorage` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `layout` | Event handler called when group layout changes | `[val: number[]]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `layout` | Current size of layout | `number[]` |

### Panel

A collapsible section.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `collapsedSize` | The size of panel when it is collapsed; interpreted using sizeUnit. | `number` | No | - |
| `collapsible` | Should panel collapse when resized beyond its minSize. When true, it will be collapsed to collapsedSize. | `boolean` | No | - |
| `defaultSize` | Initial size of panel, interpreted using sizeUnit (percent by default). | `number` | No | - |
| `id` | Panel id (unique within group); falls back to useId when not provided | `string` | No | - |
| `maxSize` | The maximum allowable size of panel, interpreted using sizeUnit; defaults to 100 (percent). | `number` | No | - |
| `minSize` | The minimum allowable size of panel, interpreted using sizeUnit; defaults to 10 (percent). | `number` | No | - |
| `order` | The order of panel within group; required for groups with conditionally rendered panels | `number` | No | - |
| `sizeUnit` | Unit used for sizing values; % by default, or px for fixed sizing. | `"%" \| "px"` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `collapse` | Event handler called when panel is collapsed. | `[]` |
| `expand` | Event handler called when panel is expanded. | `[]` |
| `resize` | Event handler called when panel is resized; size parameter is a numeric value between 1-100. | `[size: number, prevSize: number]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `isCollapsed` | Is the panel collapsed | `boolean` |
| `isExpanded` | Is the panel expanded | `boolean` |
| `collapse` | If panel is collapsible, collapse it fully. | `(): void` |
| `expand` | If panel is currently collapsed, expand it to its most recent size. | `(): void` |
| `resize` | Resize panel to the specified percentage (1 - 100). | `(size: number): void` |

**Methods**

| Name | Description | Type |
| --- | --- | --- |
| `collapse` | If panel is collapsible, collapse it fully. | `() => void` |
| `expand` | If panel is currently collapsed, expand it to its most recent size. | `() => void` |
| `getSize` | Gets the current size of the panel (in the panel's sizeUnit: percentage for '%', pixels for 'px'). | `() => number` |
| `resize` | Resize panel to the specified size (in the panel's sizeUnit: percentage for '%', pixels for 'px'). | `(size: number) => void` |

### Resize Handle

Handle that use for resizing.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | Disable drag handle | `boolean` | No | - |
| `hitAreaMargins` | Allow this much margin when determining resizable handle hit detection | `PointerHitAreaMargins` | No | - |
| `id` | Resize handle id (unique within group); falls back to useId when not provided | `string` | No | - |
| `nonce` | Will add nonce attribute to the style tag which can be used by Content Security Policy.  If omitted, inherits globally from ConfigProvider. | `string` | No | - |
| `tabindex` | Tabindex for the handle | `number` | No | `0` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `dragging` | Event handler called when dragging the handler. | `[isDragging: boolean]` |
