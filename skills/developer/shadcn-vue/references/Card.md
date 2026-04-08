---
title: Card (shadcn-vue)
description: >-
  Displays a card with header, content, and footer.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/card
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add card
# or: npx shadcn-vue@latest add card
# or: yarn dlx shadcn-vue@latest add card
# or: bunx --bun shadcn-vue@latest add card
```

## Usage

```vue
<script setup lang="ts">
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
</script>

<template>
  <Card>
    <CardHeader>
      <CardTitle>Card Title</CardTitle>
      <CardDescription>Card Description</CardDescription>
    </CardHeader>
    <CardContent>
      <p>Card Content</p>
    </CardContent>
    <CardFooter>
      <p>Card Footer</p>
    </CardFooter>
  </Card>
</template>
```
