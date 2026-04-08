---
title: Pagination (shadcn-vue + Reka UI)
description: >-
  Pagination with page navigation, next and previous links.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/pagination
  reka-doc: https://reka-ui.com/docs/components/pagination
  reka-api: https://reka-ui.com/docs/components/pagination#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add pagination
# or: npx shadcn-vue@latest add pagination
# or: yarn dlx shadcn-vue@latest add pagination
# or: bunx --bun shadcn-vue@latest add pagination
```

## Usage

```vue
<script setup lang="ts">
import {
  Pagination,
  PaginationContent,
  PaginationEllipsis,
  PaginationItem,
  PaginationLink,
  PaginationNext,
  PaginationPrevious,
} from '@/components/ui/pagination'
</script>

<template>
  <Pagination>
    <PaginationContent>
      <PaginationItem>
        <PaginationPrevious href="#" />
      </PaginationItem>
      <PaginationItem>
        <PaginationLink href="#">
          1
        </PaginationLink>
      </PaginationItem>
      <PaginationItem>
        <PaginationLink href="#" is-active>
          2
        </PaginationLink>
      </PaginationItem>
      <PaginationItem>
        <PaginationLink href="#">
          3
        </PaginationLink>
      </PaginationItem>
      <PaginationItem>
        <PaginationEllipsis />
      </PaginationItem>
      <PaginationItem>
        <PaginationNext href="#" />
      </PaginationItem>
    </PaginationContent>
  </Pagination>
</template>
```

## Reka UI API reference

### Root

Contains all of the paginations parts.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"nav"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultPage` | The value of the page that should be active when initially rendered. Use when you do not need to control the value state. | `number` | No | `1` |
| `disabled` | When true, prevents the user from interacting with item | `boolean` | No | - |
| `itemsPerPage` | Number of items per page | `number` | Yes | - |
| `page` | The controlled value of the current page. Can be binded as v-model:page. | `number` | No | - |
| `showEdges` | When true, always show first page, last page, and ellipsis | `boolean` | No | `false` |
| `siblingCount` | Number of sibling should be shown around the current page | `number` | No | `2` |
| `total` | Number of items in your list | `number` | No | `0` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:page` | Event handler called when the page value changes | `[value: number]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `page` | Current page state | `number` |
| `pageCount` | Number of pages | `number` |

### List

Used to show the list of pages. It also makes pagination accessible to assistive technologies.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `items` | Pages item | `{ type: "ellipsis"; } \| { type: "page"; value: number; }` |

### Item

Used to render the button that changes the current page.

### Ellipsis

Placeholder element when the list is long, and only a small amount of `siblingCount` was set and `showEdges` was set to `true`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### First

Triggers that set the page value to 1

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Prev

Triggers that set the page value to the previous page

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Next

Triggers that set the page value to the next page

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Last

Triggers that set the page value to the last page

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
