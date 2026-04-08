---
title: Textarea (shadcn-vue)
description: >-
  Displays a form textarea or a component that looks like a textarea.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/textarea
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add textarea
# or: npx shadcn-vue@latest add textarea
# or: yarn dlx shadcn-vue@latest add textarea
# or: bunx --bun shadcn-vue@latest add textarea
```

## Usage

```vue
<script setup lang="ts">
import { Textarea } from '@/components/ui/textarea'
</script>

<template>
  <Textarea placeholder="Type your message here." />
</template>
```
