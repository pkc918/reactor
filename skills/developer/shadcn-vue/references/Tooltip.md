---
title: Tooltip (shadcn-vue + Reka UI)
description: >-
  A popup that displays information related to an element when the element receives keyboard focus or the mouse hovers over it.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/tooltip
  reka-doc: https://reka-ui.com/docs/components/tooltip
  reka-api: https://reka-ui.com/docs/components/tooltip#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add tooltip
# or: npx shadcn-vue@latest add tooltip
# or: yarn dlx shadcn-vue@latest add tooltip
# or: bunx --bun shadcn-vue@latest add tooltip
```

## Usage

```vue
<script setup lang="ts">
import {
  Tooltip,
  TooltipContent,
  TooltipProvider,
  TooltipTrigger,
} from '@/components/ui/tooltip'
</script>

<template>
  <TooltipProvider>
    <Tooltip>
      <TooltipTrigger>Hover</TooltipTrigger>
      <TooltipContent>
        <p>Add to library</p>
      </TooltipContent>
    </Tooltip>
  </TooltipProvider>
</template>
```

## Reka UI API reference

### Provider

Wraps your app to provide global functionality to your tooltips.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `content` | Default settings that will be used by all tooltip components. | `TooltipContentProps` | No | - |
| `delayDuration` | The duration from when the pointer enters the trigger until the tooltip gets opened. | `number` | No | `700` |
| `disableClosingTrigger` | When true, clicking on trigger will not close the content. | `boolean` | No | - |
| `disabled` | When true, disable tooltip | `boolean` | No | - |
| `disableHoverableContent` | When true, trying to hover the content will result in the tooltip closing as the pointer leaves the trigger. | `boolean` | No | `false` |
| `ignoreNonKeyboardFocus` | Prevent the tooltip from opening if the focus did not come from the keyboard by matching against the :focus-visible selector. This is useful if you want to avoid opening it when switching browser tabs or closing a dialog. | `boolean` | No | `false` |
| `skipDelayDuration` | How much time a user has to enter another trigger without incurring a delay again. | `number` | No | `300` |

### Root

Contains all the parts of a tooltip.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `defaultOpen` | The open state of the tooltip when it is initially rendered. Use when you do not need to control its open state. | `boolean` | No | `false` |
| `delayDuration` | Override the duration given to the Provider to customise the open delay for a specific tooltip. | `number` | No | - |
| `disableClosingTrigger` | When true, clicking on trigger will not close the content. | `boolean` | No | - |
| `disabled` | When true, disable tooltip | `boolean` | No | - |
| `disableHoverableContent` | Prevents Tooltip.Content from remaining open when hovering. Disabling this has accessibility consequences. Inherits from Tooltip.Provider. | `boolean` | No | - |
| `ignoreNonKeyboardFocus` | Prevent the tooltip from opening if the focus did not come from the keyboard by matching against the :focus-visible selector. This is useful if you want to avoid opening it when switching browser tabs or closing a dialog. | `boolean` | No | - |
| `open` | The controlled open state of the tooltip. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:open` | Event handler called when the open state of the tooltip changes. | `[value: boolean]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `open` | Current open state | `boolean` |

### Trigger

The button that toggles the tooltip. By default, the `TooltipContent` will position itself against the trigger.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `reference` | The reference (or anchor) element that is being referred to for positioning. If not provided will use the current component as anchor. | `ReferenceElement` | No | - |

### Portal

When used, portals the content part into the `body`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `defer` | Defer the resolving of a Teleport target until other parts of the application have mounted (requires Vue 3.5.0+) reference | `boolean` | No | - |
| `disabled` | Disable teleport and render the component inline reference | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `to` | Vue native teleport component prop :to reference | `string \| HTMLElement` | No | - |

### Content

The component that pops out when the tooltip is open.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `align` | The preferred alignment against the trigger. May change when collisions occur. | `"start" \| "center" \| "end"` | No | - |
| `alignOffset` | An offset in pixels from the start or end alignment options. | `number` | No | - |
| `ariaLabel` | By default, screenreaders will announce the content inside the component. If this is not descriptive enough, or you have content that cannot be announced, use aria-label as a more descriptive label. | `string` | No | - |
| `arrowPadding` | The padding between the arrow and the edges of the content. If your content has border-radius, this will prevent it from overflowing the corners. | `number` | No | - |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `avoidCollisions` | When true, overrides the side and align preferences to prevent collisions with boundary edges. | `boolean` | No | - |
| `collisionBoundary` | The element used as the collision boundary. By default this is the viewport, though you can provide additional element(s) to be included in this check. | `Element \| (Element \| null)[] \| null` | No | - |
| `collisionPadding` | The distance in pixels from the boundary edges where collision detection should occur. Accepts a number (same for all sides), or a partial padding object, for example: { top: 20, left: 20 }. | `number \| Partial<Record<"top" \| "right" \| "bottom" \| "left", number>>` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `hideWhenDetached` | Whether to hide the content when the trigger becomes fully occluded. | `boolean` | No | - |
| `positionStrategy` | The type of CSS position property to use. | `"fixed" \| "absolute"` | No | - |
| `side` | The preferred side of the trigger to render against when open. Will be reversed when collisions occur and avoidCollisions is enabled. | `"top" \| "right" \| "bottom" \| "left"` | No | - |
| `sideOffset` | The distance in pixels from the trigger. | `number` | No | - |
| `sticky` | The sticky behavior on the align axis. partial will keep the content in the boundary as long as the trigger is at least partially in the boundary whilst "always" will keep the content in the boundary regardless. | `"partial" \| "always"` | No | - |
| `updatePositionStrategy` | Strategy to update the position of the floating element on every animation frame. | `"always" \| "optimized"` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `escapeKeyDown` | Event handler called when focus moves to the destructive action after opening. It can be prevented by calling event.preventDefault | `[event: KeyboardEvent]` |
| `pointerDownOutside` | Event handler called when a pointer event occurs outside the bounds of the component. It can be prevented by calling event.preventDefault. | `[event: Event]` |

### Arrow

An optional arrow element to render alongside the tooltip. This can be used to help visually link the trigger with the `TooltipContent`. Must be rendered inside `TooltipContent`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"svg"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `height` | The height of the arrow in pixels. | `number` | No | `5` |
| `width` | The width of the arrow in pixels. | `number` | No | `10` |
