---
title: Sheet (shadcn-vue + Reka UI)
description: >-
  Extends the Dialog component to display content that complements the main content of the screen.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/sheet
  reka-doc: https://reka-ui.com/docs/components/dialog
  reka-api: https://reka-ui.com/docs/components/dialog#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add sheet
# or: npx shadcn-vue@latest add sheet
# or: yarn dlx shadcn-vue@latest add sheet
# or: bunx --bun shadcn-vue@latest add sheet
```

## Usage

```vue
<script setup lang="ts">
import {
  Sheet,
  SheetContent,
  SheetDescription,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from '@/components/ui/sheet'
</script>

<template>
  <Sheet>
    <SheetTrigger>Open</SheetTrigger>
    <SheetContent>
      <SheetHeader>
        <SheetTitle>Are you absolutely sure?</SheetTitle>
        <SheetDescription>
          This action cannot be undone. This will permanently delete your account
          and remove your data from our servers.
        </SheetDescription>
      </SheetHeader>
    </SheetContent>
  </Sheet>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a dialog




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `defaultOpen` | The open state of the dialog when it is initially rendered. Use when you do not need to control its open state. | `boolean` | No | `false` |
| `modal` | The modality of the dialog When set to true,  interaction with outside elements will be disabled and only dialog content will be visible to screen readers. | `boolean` | No | `true` |
| `open` | The controlled open state of the dialog. Can be binded as v-model:open. | `boolean` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:open` | Event handler called when the open state of the dialog changes. | `[value: boolean]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `open` | Current open state | `boolean` |
| `close` | Close the dialog | `(): void` |

### Trigger

The button that opens the dialog

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Portal

When used, portals your overlay and content parts into the `body`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `defer` | Defer the resolving of a Teleport target until other parts of the application have mounted (requires Vue 3.5.0+) reference | `boolean` | No | - |
| `disabled` | Disable teleport and render the component inline reference | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `to` | Vue native teleport component prop :to reference | `string \| HTMLElement` | No | - |

### Overlay

A layer that covers the inert portion of the view when the dialog is open.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |

### Content

Contains content to be rendered in the open dialog




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
| `closeAutoFocus` | Event handler called when auto-focusing on close. Can be prevented. | `[event: Event]` |
| `escapeKeyDown` | Event handler called when the escape key is down. Can be prevented. | `[event: KeyboardEvent]` |
| `focusOutside` | Event handler called when the focus moves outside of the DismissableLayer. Can be prevented. | `[event: FocusOutsideEvent]` |
| `interactOutside` | Event handler called when an interaction happens outside the DismissableLayer. Specifically, when a pointerdown event happens outside or focus moves outside of it. Can be prevented. | `[event: PointerDownOutsideEvent \| FocusOutsideEvent]` |
| `openAutoFocus` | Event handler called when auto-focusing on open. Can be prevented. | `[event: Event]` |
| `pointerDownOutside` | Event handler called when a pointerdown event happens outside of the DismissableLayer. Can be prevented. | `[event: PointerDownOutsideEvent]` |

### Close

The button that closes the dialog

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Title

An accessible title to be announced when the dialog is opened.

If you want to hide the title, wrap it inside our Visually Hidden utility like this `<VisuallyHidden asChild>`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"h2"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Description

An optional accessible description to be announced when the dialog is opened.

If you want to hide the description, wrap it inside our Visually Hidden utility like this `<VisuallyHidden asChild>`. If you want to remove the description entirely, remove this part and pass `:aria-describedby="undefined"` to `DialogContent`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"p"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
