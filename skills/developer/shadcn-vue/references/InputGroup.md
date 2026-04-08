---
title: Input Group (shadcn-vue)
description: >-
  Display additional information or actions to an input or textarea.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/input-group
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add input-group
# or: npx shadcn-vue@latest add input-group
# or: yarn dlx shadcn-vue@latest add input-group
# or: bunx --bun shadcn-vue@latest add input-group
```

## Usage

```vue
<script setup lang="ts">
import {
  InputGroup,
  InputGroupAddon,
  InputGroupButton,
  InputGroupInput,
  InputGroupText,
  InputGroupTextarea,
} from '@/components/ui/input-group'
</script>

<template>
  <InputGroup>
    <InputGroupInput placeholder="Search..." />
    <InputGroupAddon>
      <SearchIcon />
    </InputGroupAddon>
    <InputGroupAddon align="inline-end">
      <InputGroupButton>Search</InputGroupButton>
    </InputGroupAddon>
  </InputGroup>
</template>
```
