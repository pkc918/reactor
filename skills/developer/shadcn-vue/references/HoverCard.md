---
title: Hover Card (shadcn-vue + Reka UI)
description: >-
  For sighted users to preview content available behind a link.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/hover-card
  reka-doc: https://reka-ui.com/docs/components/hover-card
  reka-api: https://reka-ui.com/docs/components/hover-card#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add hover-card
# or: npx shadcn-vue@latest add hover-card
# or: yarn dlx shadcn-vue@latest add hover-card
# or: bunx --bun shadcn-vue@latest add hover-card
```

## Usage

```vue
<script setup lang="ts">
import {
  HoverCard,
  HoverCardContent,
  HoverCardTrigger,
} from '@/components/ui/hover-card'
</script>

<template>
  <HoverCard>
    <HoverCardTrigger>Hover</HoverCardTrigger>
    <HoverCardContent>
      The Vue Framework – created and maintained by Evan You.
    </HoverCardContent>
  </HoverCard>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a hover card.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `closeDelay` | The duration from when the mouse leaves the trigger or content until the hover card closes. | `number` | No | `300` |
| `defaultOpen` | The open state of the hover card when it is initially rendered. Use when you do not need to control its open state. | `boolean` | No | `false` |
| `open` | The controlled open state of the hover card. Can be binded as v-model:open. | `boolean` | No | - |
| `openDelay` | The duration from when the mouse enters the trigger until the hover card opens. | `number` | No | `700` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:open` | Event handler called when the open state of the hover card changes. | `[value: boolean]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `open` | Current open state | `boolean` |

### Trigger

The link that opens the hover card when hovered.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"a"` |
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

The component that pops out when the hover card is open.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `align` | The preferred alignment against the trigger. May change when collisions occur. | `"start" \| "center" \| "end"` | No | - |
| `alignFlip` | Flip alignment when colliding with boundary. May only occur when prioritizePosition is true. | `boolean` | No | - |
| `alignOffset` | An offset in pixels from the start or end alignment options. | `number` | No | - |
| `arrowPadding` | The padding between the arrow and the edges of the content. If your content has border-radius, this will prevent it from overflowing the corners. | `number` | No | - |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `avoidCollisions` | When true, overrides the side and align preferences to prevent collisions with boundary edges. | `boolean` | No | - |
| `collisionBoundary` | The element used as the collision boundary. By default this is the viewport, though you can provide additional element(s) to be included in this check. | `Element \| (Element \| null)[] \| null` | No | - |
| `collisionPadding` | The distance in pixels from the boundary edges where collision detection should occur. Accepts a number (same for all sides), or a partial padding object, for example: { top: 20, left: 20 }. | `number \| Partial<Record<"top" \| "right" \| "bottom" \| "left", number>>` | No | - |
| `disableUpdateOnLayoutShift` | Whether to disable the update position for the content when the layout shifted. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `hideShiftedArrow` | When true, hides the arrow when it cannot be centered to the reference element. | `boolean` | No | - |
| `hideWhenDetached` | Whether to hide the content when the trigger becomes fully occluded. | `boolean` | No | - |
| `positionStrategy` | The type of CSS position property to use. | `"fixed" \| "absolute"` | No | - |
| `prioritizePosition` | Force content to be position within the viewport. Might overlap the reference element, which may not be desired. | `boolean` | No | - |
| `reference` | The custom element or virtual element that will be set as the reference to position the floating element. If provided, it will replace the default anchor element. | `ReferenceElement` | No | - |
| `side` | The preferred side of the trigger to render against when open. Will be reversed when collisions occur and avoidCollisions is enabled. | `"top" \| "right" \| "bottom" \| "left"` | No | - |
| `sideFlip` | Flip to the opposite side when colliding with boundary. | `boolean` | No | - |
| `sideOffset` | The distance in pixels from the trigger. | `number` | No | - |
| `sticky` | The sticky behavior on the align axis. partial will keep the content in the boundary as long as the trigger is at least partially in the boundary whilst "always" will keep the content in the boundary regardless. | `"partial" \| "always"` | No | - |
| `updatePositionStrategy` | Strategy to update the position of the floating element on every animation frame. | `"always" \| "optimized"` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `escapeKeyDown` | Event handler called when the escape key is down. Can be prevented. | `[event: KeyboardEvent]` |
| `focusOutside` | Event handler called when the focus moves outside of the DismissableLayer. Can be prevented. | `[event: FocusOutsideEvent]` |
| `interactOutside` | Event handler called when an interaction happens outside the DismissableLayer. Specifically, when a pointerdown event happens outside or focus moves outside of it. Can be prevented. | `[event: PointerDownOutsideEvent \| FocusOutsideEvent]` |
| `pointerDownOutside` | Event handler called when a pointerdown event happens outside of the DismissableLayer. Can be prevented. | `[event: PointerDownOutsideEvent]` |

### Arrow

An optional arrow element to render alongside the hover card. This can be used to help visually link the trigger with the `HoverCardContent`. Must be rendered inside `HoverCardContent`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"svg"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `height` | The height of the arrow in pixels. | `number` | No | `5` |
| `rounded` | When true, render the rounded version of arrow. Do not work with as/asChild | `boolean` | No | - |
| `width` | The width of the arrow in pixels. | `number` | No | `10` |
