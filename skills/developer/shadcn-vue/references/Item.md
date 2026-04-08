---
title: Item (shadcn-vue)
description: >-
  A versatile component that you can use to display any content.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/item
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add item
# or: npx shadcn-vue@latest add item
# or: yarn dlx shadcn-vue@latest add item
# or: bunx --bun shadcn-vue@latest add item
```

## Usage

```vue
<script setup lang="ts">
import {
  Item,
  ItemContent,
  ItemDescription,
  ItemFooter,
  ItemHeader,
  ItemMedia,
  ItemTitle,
} from '@/components/ui/item'
</script>

<template>
  <Item>
    <ItemHeader>Item Header</ItemHeader>
    <ItemMedia />
    <ItemContent>
      <ItemTitle>Item</ItemTitle>
      <ItemDescription>Item</ItemDescription>
    </ItemContent>
    <ItemFooter>Item Footer</ItemFooter>
  </Item>
</template>
```
