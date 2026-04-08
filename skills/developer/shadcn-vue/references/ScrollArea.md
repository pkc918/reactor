---
title: Scroll Area (shadcn-vue + Reka UI)
description: >-
  Augments native scroll functionality for custom, cross-browser styling.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/scroll-area
  reka-doc: https://reka-ui.com/docs/components/scroll-area
  reka-api: https://reka-ui.com/docs/components/scroll-area#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add scroll-area
# or: npx shadcn-vue@latest add scroll-area
# or: yarn dlx shadcn-vue@latest add scroll-area
# or: bunx --bun shadcn-vue@latest add scroll-area
```

## Usage

```vue
<script setup lang="ts">
import { ScrollArea } from '@/components/ui/scroll-area'
</script>

<template>
  <ScrollArea class="h-[200px] w-[350px] rounded-md border p-4">
    Jokester began sneaking into the castle in the middle of the night and leaving
    jokes all over the place: under the king's pillow, in his soup, even in the
    royal toilet. The king was furious, but he couldn't seem to stop Jokester. And
    then one day, the king tripped over one of Jokester's whoopee cushions and
    fell into the moat. He was so embarrassed that he decided to make Jokester the
    official court jester.
  </ScrollArea>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a scroll area.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `scrollHideDelay` | If type is set to either scroll or hover, this prop determines the length of time, in milliseconds,  before the scrollbars are hidden after the user stops interacting with scrollbars. | `number` | No | `600` |
| `type` | Describes the nature of scrollbar visibility, similar to how the scrollbar preferences in MacOS control visibility of native scrollbars. auto - means that scrollbars are visible when content is overflowing on the corresponding orientation.  always - means that scrollbars are always visible regardless of whether the content is overflowing. scroll - means that scrollbars are visible when the user is scrolling along its corresponding orientation. hover - when the user is scrolling along its corresponding orientation and when the user is hovering over the scroll area. glimpse - a hybrid approach that briefly shows scrollbars when the user enters the scroll area, then hides them until further interaction. | `"scroll" \| "always" \| "hover" \| "auto" \| "glimpse"` | No | `"hover"` |

**Methods**

| Name | Description | Type |
| --- | --- | --- |
| `scrollTop` | Scroll viewport to top | `() => void` |
| `scrollTopLeft` | Scroll viewport to top-left | `() => void` |

### Viewport

The viewport area of the scroll area.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `nonce` | Will add nonce attribute to the style tag which can be used by Content Security Policy.  If omitted, inherits globally from ConfigProvider. | `string` | No | - |

### Scrollbar

The vertical scrollbar. Add a second `Scrollbar` with an `orientation` prop to enable horizontal scrolling.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `orientation` | The orientation of the scrollbar | `"vertical" \| "horizontal"` | No | `"vertical"` |

### Thumb

The thumb to be used in `ScrollAreaScrollbar`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Corner

The corner where both vertical and horizontal scrollbars meet.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
