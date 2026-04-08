---
title: Select (shadcn-vue + Reka UI)
description: >-
  Displays a list of options for the user to pick from—triggered by a button.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/select
  reka-doc: https://reka-ui.com/docs/components/select
  reka-api: https://reka-ui.com/docs/components/select#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add select
# or: npx shadcn-vue@latest add select
# or: yarn dlx shadcn-vue@latest add select
# or: bunx --bun shadcn-vue@latest add select
```

## Usage

```vue
<script setup lang="ts">
import {
  Select,
  SelectContent,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from '@/components/ui/select'
</script>

<template>
  <Select>
    <SelectTrigger>
      <SelectValue placeholder="Select a fruit" />
    </SelectTrigger>
    <SelectContent>
      <SelectItem value="apple">
        Apple
      </SelectItem>
      <SelectItem value="banana">
        Banana
      </SelectItem>
      <SelectItem value="blueberry">
        Blueberry
      </SelectItem>
      <SelectItem value="grapes">
        Grapes
      </SelectItem>
      <SelectItem value="pineapple">
        Pineapple
      </SelectItem>
    </SelectContent>
  </Select>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a Select




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `autocomplete` | Native html input autocomplete attribute. | `string` | No | - |
| `by` | Use this to compare objects by a particular field, or pass your own comparison function for complete control over how objects are compared. | `string \| ((a: AcceptableValue, b: AcceptableValue) => boolean)` | No | - |
| `defaultOpen` | The open state of the select when it is initially rendered. Use when you do not need to control its open state. | `boolean` | No | - |
| `defaultValue` | The value of the select when initially rendered. Use when you do not need to control the state of the Select | `AcceptableValue \| AcceptableValue[]` | No | - |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | When true, prevents the user from interacting with Select | `boolean` | No | - |
| `modelValue` | The controlled value of the Select. Can be bind as v-model. | `AcceptableValue \| AcceptableValue[]` | No | - |
| `multiple` | Whether multiple options can be selected or not. | `boolean` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `open` | The controlled open state of the Select. Can be bind as v-model:open. | `boolean` | No | - |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value changes. | `[value: AcceptableValue]` |
| `update:open` | Event handler called when the open state of the context menu changes. | `[value: boolean]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `AcceptableValue \| AcceptableValue[] \| undefined` |
| `open` | Current open state | `boolean` |

### Trigger

The button that toggles the Select The `SelectContent` will position itself by aligning over the trigger.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` |  | `boolean` | No | - |
| `reference` | The reference (or anchor) element that is being referred to for positioning. If not provided will use the current component as anchor. | `ReferenceElement` | No | - |

### Value

The part that reflects the selected value. By default the selected item's text will be rendered. if you require more control, you can instead control the select and pass your own `children`. It should not be styled to ensure correct positioning. An optional `placeholder` prop is also available for when the select has no value.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `placeholder` | The content that will be rendered inside the SelectValue when no value or defaultValue is set. | `string` | No | `""` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `selectedLabel` |  | `string[]` |
| `modelValue` |  | `AcceptableValue \| AcceptableValue[] \| undefined` |

### Icon

A small icon often displayed next to the value as a visual affordance for the fact it can be open. By default renders ▼ but you can use your own icon via `asChild` or use `children`.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the item. | `boolean` | No | - |
| `textValue` | Optional text used for typeahead purposes. By default the typeahead behavior will use the .textContent of the SelectItemText part. Use this when the content is complex, or you have non-textual content inside. | `string` | No | - |
| `value` | The value given as data when submitted with a name. | `AcceptableValue` | Yes | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `select` | Event handler called when the selecting item.  It can be prevented by calling event.preventDefault. | `[event: SelectEvent<AcceptableValue>]` |

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

The component that pops out when the select is open.




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
| `bodyLock` | The document.body will be lock, and scrolling will be disabled. | `boolean` | No | - |
| `collisionBoundary` | The element used as the collision boundary. By default this is the viewport, though you can provide additional element(s) to be included in this check. | `Element \| (Element \| null)[] \| null` | No | - |
| `collisionPadding` | The distance in pixels from the boundary edges where collision detection should occur. Accepts a number (same for all sides), or a partial padding object, for example: { top: 20, left: 20 }. | `number \| Partial<Record<"top" \| "right" \| "bottom" \| "left", number>>` | No | - |
| `disableOutsidePointerEvents` | When true, hover/focus/click interactions will be disabled on elements outside the DismissableLayer. Users will need to click twice on outside elements to interact with them: once to close the DismissableLayer, and again to trigger the element. | `boolean` | No | - |
| `disableUpdateOnLayoutShift` | Whether to disable the update position for the content when the layout shifted. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `hideShiftedArrow` | When true, hides the arrow when it cannot be centered to the reference element. | `boolean` | No | - |
| `hideWhenDetached` | Whether to hide the content when the trigger becomes fully occluded. | `boolean` | No | - |
| `position` | The positioning mode to use item-aligned (default) - behaves similarly to a native MacOS menu by positioning content relative to the active item.  popper - positions content in the same way as our other primitives, for example Popover or DropdownMenu. | `"popper" \| "item-aligned"` | No | - |
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
| `closeAutoFocus` | Event handler called when auto-focusing on close. Can be prevented. | `[event: Event]` |
| `escapeKeyDown` | Event handler called when the escape key is down. Can be prevented. | `[event: KeyboardEvent]` |
| `pointerDownOutside` | Event handler called when a pointerdown event happens outside of the DismissableLayer. Can be prevented. | `[event: PointerDownOutsideEvent]` |

### Viewport

The scrolling viewport that contains all of the items.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `nonce` | Will add nonce attribute to the style tag which can be used by Content Security Policy.  If omitted, inherits globally from ConfigProvider. | `string` | No | - |

### Item

The component that contains the select items.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with the item. | `boolean` | No | - |
| `textValue` | Optional text used for typeahead purposes. By default the typeahead behavior will use the .textContent of the SelectItemText part. Use this when the content is complex, or you have non-textual content inside. | `string` | No | - |
| `value` | The value given as data when submitted with a name. | `AcceptableValue` | Yes | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `select` | Event handler called when the selecting item.  It can be prevented by calling event.preventDefault. | `[event: SelectEvent<AcceptableValue>]` |

### ItemText

The textual part of the item. It should only contain the text you want to see in the trigger when that item is selected. It should not be styled to ensure correct positioning.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### ItemIndicator

Renders when the item is selected. You can style this element directly, or you can use it as a wrapper to put an icon into, or both.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### ScrollUpButton

An optional button used as an affordance to show the viewport overflow as well as functionally enable scrolling upwards.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### ScrollDownButton

An optional button used as an affordance to show the viewport overflow as well as functionally enable scrolling downwards.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Group

Used to group multiple items. use in conjunction with `SelectLabel` to ensure good accessibility via automatic labelling.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Label

Used to render the label of a group. It won't be focusable using arrow keys.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `for` |  | `string` | No | - |

### Separator

Used to visually separate items in the Select

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Arrow

An optional arrow element to render alongside the content. This can be used to help visually link the trigger with the `SelectContent`. Must be rendered inside `SelectContent`. Only available when `position` is set to `popper`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"svg"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `height` | The height of the arrow in pixels. | `number` | No | `5` |
| `rounded` | When true, render the rounded version of arrow. Do not work with as/asChild | `boolean` | No | - |
| `width` | The width of the arrow in pixels. | `number` | No | `10` |
