---
title: Sonner (shadcn-vue)
description: >-
  An opinionated toast component for Vue.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/sonner
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add sonner
# or: npx shadcn-vue@latest add sonner
# or: yarn dlx shadcn-vue@latest add sonner
# or: bunx --bun shadcn-vue@latest add sonner
```

## Usage

```vue
<script setup lang="ts">
import { toast } from 'vue-sonner'
import { Button } from '@/components/ui/button'
</script>

<template>
  <Button @click="() => toast('My first toast')">
    Give me a toast
  </Button>
</template>
```
