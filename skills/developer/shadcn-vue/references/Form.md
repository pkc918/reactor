---
title: Form (shadcn-vue)
description: >-
  Building forms with VeeValidate and Zod.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/form
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add form
# or: npx shadcn-vue@latest add form
# or: yarn dlx shadcn-vue@latest add form
# or: bunx --bun shadcn-vue@latest add form
```

## Usage

```vue
<script setup lang="ts">
import {
  FormControl,
  FormDescription,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from '@/components/ui/form'
</script>

<template>
  <FormField v-slot="{ componentField }" name="username">
    <FormItem>
      <FormLabel>Username</FormLabel>
      <FormControl>
        <Input placeholder="shadcn" v-bind="componentField" />
      </FormControl>
      <FormDescription>
        This is your public display name.
      </FormDescription>
      <FormMessage />
    </FormItem>
  </FormField>
</template>
```
