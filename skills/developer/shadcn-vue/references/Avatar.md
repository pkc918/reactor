---
title: Avatar (shadcn-vue + Reka UI)
description: >-
  An image element with a fallback for representing the user.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/avatar
  reka-doc: https://reka-ui.com/docs/components/avatar
  reka-api: https://reka-ui.com/docs/components/avatar#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add avatar
# or: npx shadcn-vue@latest add avatar
# or: yarn dlx shadcn-vue@latest add avatar
# or: bunx --bun shadcn-vue@latest add avatar
```

## Usage

```vue
<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from '@/components/ui/avatar'
</script>

<template>
  <Avatar>
    <AvatarImage src="https://github.com/shadcn.png" />
    <AvatarFallback>CN</AvatarFallback>
  </Avatar>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of an avatar

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Image

The image to render. By default it will only render when it has loaded. You can use the `@loadingStatusChange` handler if you need more control.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"img"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `crossOrigin` |  | `"" \| "anonymous" \| "use-credentials"` | No | - |
| `referrerPolicy` |  | `"" \| "no-referrer" \| "no-referrer-when-downgrade" \| "origin" \| "origin-when-cross-origin" \| "same-origin" \| "strict-origin" \| "strict-origin-when-cross-origin" \| "unsafe-url"` | No | - |
| `src` |  | `string` | Yes | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `loadingStatusChange` | A callback providing information about the loading status of the image.  This is useful in case you want to control more precisely what to render as the image is loading. | `[value: ImageLoadingStatus]` |

### Fallback

An element that renders when the image hasn't loaded. This means whilst it's loading, or if there was an error. If you notice a flash during loading, you can provide a `delayMs` prop to delay its rendering so it only renders for those with slower connections. For more control, use the `@loadingStatusChange` emit on `AvatarImage`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"span"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `delayMs` | Useful for delaying rendering so it only appears for those with slower connections. | `number` | No | - |
