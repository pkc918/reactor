---
title: Toast (shadcn-vue + Reka UI)
description: >-
  A succinct message that is displayed temporarily.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/toast
  reka-doc: https://reka-ui.com/docs/components/toast
  reka-api: https://reka-ui.com/docs/components/toast#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add toast
# or: npx shadcn-vue@latest add toast
# or: yarn dlx shadcn-vue@latest add toast
# or: bunx --bun shadcn-vue@latest add toast
```

## Usage

```vue
<script setup lang="ts">
</script>

<template>
  <!-- No Usage code block in upstream toast.md -->
</template>
```

## Reka UI API reference

### Provider

The provider that wraps your toasts and toast viewport. It usually wraps the application.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `disableSwipe` | Whether to disable the ability to swipe to close the toast. | `boolean` | No | - |
| `duration` | Time in milliseconds that each toast should remain visible for. | `number` | No | `5000` |
| `label` | An author-localized label for each toast. Used to help screen reader users associate the interruption with a toast. | `string` | No | `"Notification"` |
| `swipeDirection` | Direction of pointer swipe that should close the toast. | `"right" \| "left" \| "up" \| "down"` | No | `"right"` |
| `swipeThreshold` | Distance in pixels that the swipe must pass before a close is triggered. | `number` | No | `50` |

### Viewport

The fixed area where toasts appear. Users can jump to the viewport by pressing a hotkey. It is up to you to ensure the discoverability of the hotkey for keyboard users.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"ol"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `hotkey` | The keys to use as the keyboard shortcut that will move focus to the toast viewport. | `string[]` | No | `["F8"]` |
| `label` | An author-localized label for the toast viewport to provide context for screen reader users when navigating page landmarks. The available {hotkey} placeholder will be replaced for you. Alternatively, you can pass in a custom function to generate the label. | `string \| ((hotkey: string) => string)` | No | `"Notifications ({hotkey})"` |

### Root

The toast that automatically closes. It should not be held open to [acquire a user response](/docs/components/toast#action).




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"li"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultOpen` | The open state of the dialog when it is initially rendered. Use when you do not need to control its open state. | `boolean` | No | `true` |
| `duration` | Time in milliseconds that toast should remain visible for. Overrides value given to ToastProvider. | `number` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `open` | The controlled open state of the dialog. Can be bind as v-model:open. | `boolean` | No | - |
| `type` | Control the sensitivity of the toast for accessibility purposes. For toasts that are the result of a user action, choose foreground. Toasts generated from background tasks should use background. | `"foreground" \| "background"` | No | `"foreground"` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `escapeKeyDown` | Event handler called when the escape key is down. It can be prevented by calling event.preventDefault. | `[event: KeyboardEvent]` |
| `pause` | Event handler called when the dismiss timer is paused. This occurs when the pointer is moved over the viewport, the viewport is focused or when the window is blurred. | `[]` |
| `resume` | Event handler called when the dismiss timer is resumed. This occurs when the pointer is moved away from the viewport, the viewport is blurred or when the window is focused. | `[]` |
| `swipeCancel` | Event handler called when swipe interaction is cancelled. It can be prevented by calling event.preventDefault. | `[event: SwipeEvent]` |
| `swipeEnd` | Event handler called at the end of a swipe interaction. It can be prevented by calling event.preventDefault. | `[event: SwipeEvent]` |
| `swipeMove` | Event handler called during a swipe interaction. It can be prevented by calling event.preventDefault. | `[event: SwipeEvent]` |
| `swipeStart` | Event handler called when starting a swipe interaction. It can be prevented by calling event.preventDefault. | `[event: SwipeEvent]` |
| `update:open` | Event handler called when the open state changes | `[value: boolean]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `open` | Current open state | `boolean` |
| `remaining` | Remaining time (in ms) | `number` |
| `duration` | Total time the toast will remain visible for (in ms) | `number` |

### Portal

When used, portals the content part into the `body`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `defer` | Defer the resolving of a Teleport target until other parts of the application have mounted (requires Vue 3.5.0+) reference | `boolean` | No | - |
| `disabled` | Disable teleport and render the component inline reference | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `to` | Vue native teleport component prop :to reference | `string \| HTMLElement` | No | - |

### Title

An optional title for the toast

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Description

The toast message.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Action

An action that is safe to ignore to ensure users are not expected to complete tasks with unexpected side effects as a result of a [time limit](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-required-behaviors.html).

When obtaining a user response is necessary, portal an ["AlertDialog"](/docs/components/alert-dialog) styled as a toast into the viewport instead.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `altText` | A short description for an alternate way to carry out the action. For screen reader users who will not be able to navigate to the button easily/quickly. | `string` | Yes | - |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Close

A button that allows users to dismiss the toast before its duration has elapsed.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
