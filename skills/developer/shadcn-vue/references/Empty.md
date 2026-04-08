---
title: Empty (shadcn-vue)
description: >-
  Use the Empty component to display an empty state.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/empty
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add empty
# or: npx shadcn-vue@latest add empty
# or: yarn dlx shadcn-vue@latest add empty
# or: bunx --bun shadcn-vue@latest add empty
```

## Usage

```vue
<script setup lang="ts">
import { FolderOpen } from 'lucide-vue-next'
import { Button } from '@/registry/default/ui/button'
import {
  Empty,
  EmptyContent,
  EmptyDescription,
  EmptyHeader,
  EmptyMedia,
  EmptyTitle,
} from '@/registry/default/ui/empty'
</script>

<template>
  <Empty>
    <EmptyHeader>
      <EmptyMedia variant="icon">
        <FolderOpen />
      </EmptyMedia>
    </EmptyHeader>
    <EmptyTitle>No data</EmptyTitle>
    <EmptyDescription>No data found</EmptyDescription>
    <EmptyContent>
      <Button>Add data</Button>
    </EmptyContent>
  </Empty>
</template>
```
