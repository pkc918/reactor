---
title: Navigation Menu (shadcn-vue + Reka UI)
description: >-
  A collection of links for navigating websites.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/navigation-menu
  reka-doc: https://reka-ui.com/docs/components/navigation-menu
  reka-api: https://reka-ui.com/docs/components/navigation-menu#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add navigation-menu
# or: npx shadcn-vue@latest add navigation-menu
# or: yarn dlx shadcn-vue@latest add navigation-menu
# or: bunx --bun shadcn-vue@latest add navigation-menu
```

## Usage

```vue
<script setup lang="ts">
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuIndicator,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  NavigationMenuViewport,
} from '@/components/ui/navigation-menu'
</script>

<template>
  <NavigationMenu>
    <NavigationMenuList>
      <NavigationMenuItem>
        <NavigationMenuTrigger>Item One</NavigationMenuTrigger>
        <NavigationMenuContent>
          <NavigationMenuLink>Link</NavigationMenuLink>
        </NavigationMenuContent>
      </NavigationMenuItem>
    </NavigationMenuList>
  </NavigationMenu>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a navigation menu.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"nav"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the menu item that should be active when initially rendered. Use when you do not need to control the value state. | `string` | No | - |
| `delayDuration` | The duration from when the pointer enters the trigger until the tooltip gets opened. | `number` | No | `200` |
| `dir` | The reading direction of the combobox when applicable. If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disableClickTrigger` | If true, menu cannot be open by click on trigger | `boolean` | No | `false` |
| `disableHoverTrigger` | If true, menu cannot be open by hover on trigger | `boolean` | No | `false` |
| `disablePointerLeaveClose` | If true, menu will not close during pointer leave event | `boolean` | No | - |
| `modelValue` | The controlled value of the menu item to activate. Can be used as v-model. | `string` | No | - |
| `orientation` | The orientation of the menu. | `"vertical" \| "horizontal"` | No | `"horizontal"` |
| `skipDelayDuration` | How much time a user has to enter another trigger without incurring a delay again. | `number` | No | `300` |
| `unmountOnHide` | When true, the element will be unmounted on closed state. | `boolean` | No | `true` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value changes. | `[value: string]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `string` |

### Sub

Signifies a submenu. Use it in place of the root part when nested to create a submenu.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the menu item that should be active when initially rendered. Use when you do not need to control the value state. | `string` | No | - |
| `modelValue` | The controlled value of the sub menu item to activate. Can be used as v-model. | `string` | No | - |
| `orientation` | The orientation of the menu. | `"vertical" \| "horizontal"` | No | `"horizontal"` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value changes. | `[value: string]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current input values | `string` |

### List

Contains the top level menu items.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"ul"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Item

A top level menu item, contains a link or trigger with content combination.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"li"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `value` | A unique value that associates the item with an active value when the navigation menu is controlled. This prop is managed automatically when uncontrolled. | `string` | No | - |

### Trigger

The button that toggles the content.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disabled` | When true, prevents the user from interacting with item | `boolean` | No | - |

### Content

Contains the content associated with each trigger.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `disableOutsidePointerEvents` | When true, hover/focus/click interactions will be disabled on elements outside the DismissableLayer. Users will need to click twice on outside elements to interact with them: once to close the DismissableLayer, and again to trigger the element. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `escapeKeyDown` | Event handler called when the escape key is down. Can be prevented. | `[event: KeyboardEvent]` |
| `focusOutside` | Event handler called when the focus moves outside of the DismissableLayer. Can be prevented. | `[event: FocusOutsideEvent]` |
| `interactOutside` | Event handler called when an interaction happens outside the DismissableLayer. Specifically, when a pointerdown event happens outside or focus moves outside of it. Can be prevented. | `[event: PointerDownOutsideEvent \| FocusOutsideEvent]` |
| `pointerDownOutside` | Event handler called when a pointerdown event happens outside of the DismissableLayer. Can be prevented. | `[event: PointerDownOutsideEvent]` |

### Link

A navigational link.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `active` | Used to identify the link as the currently active page. | `boolean` | No | - |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"a"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `select` | Event handler called when the user selects a link (via mouse or keyboard). Calling event.preventDefault in this handler will prevent the navigation menu from closing when selecting that link. | `[payload: CustomEvent<{ originalEvent: Event; }>]` |

### Indicator

An optional indicator element that renders below the list, is used to highlight the currently active trigger.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |

### Viewport

An optional viewport element that is used to render active content outside of the list.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `align` | Placement of the viewport for css variables (--reka-navigation-menu-viewport-left, --reka-navigation-menu-viewport-top). | `"start" \| "center" \| "end"` | No | `"center"` |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
