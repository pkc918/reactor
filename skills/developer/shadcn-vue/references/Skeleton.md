---
title: Skeleton (shadcn-vue)
description: >-
  Use to show a placeholder while content is loading.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/skeleton
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add skeleton
# or: npx shadcn-vue@latest add skeleton
# or: yarn dlx shadcn-vue@latest add skeleton
# or: bunx --bun shadcn-vue@latest add skeleton
```

## Usage

```vue
<script setup lang="ts">
import { Skeleton } from '@/components/ui/skeleton'
</script>

<template>
  <Skeleton class="w-[100px] h-[20px] rounded-full" />
</template>
```
