---
title: Alert (shadcn-vue)
description: >-
  Displays a callout for user attention.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/alert
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add alert
# or: npx shadcn-vue@latest add alert
# or: yarn dlx shadcn-vue@latest add alert
# or: bunx --bun shadcn-vue@latest add alert
```

## Usage

```vue
<script setup lang="ts">
import { Alert, AlertDescription, AlertTitle } from '@/components/ui/alert'
</script>

<template>
  <Alert>
    <AlertTitle>Heads up!</AlertTitle>
    <AlertDescription>
      You can add components and dependencies to your app using the cli.
    </AlertDescription>
  </Alert>
</template>
```
