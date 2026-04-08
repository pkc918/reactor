---
title: Badge (shadcn-vue)
description: >-
  Displays a badge or a component that looks like a badge.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/badge
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add badge
# or: npx shadcn-vue@latest add badge
# or: yarn dlx shadcn-vue@latest add badge
# or: bunx --bun shadcn-vue@latest add badge
```

## Usage

```vue
<script setup lang="ts">
import { Badge } from '@/components/ui/badge'
</script>

<template>
  <Badge variant="default | outline | secondary | destructive">
    Badge
  </Badge>
</template>
```
