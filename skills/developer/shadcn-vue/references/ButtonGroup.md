---
title: Button Group (shadcn-vue)
description: >-
  A container that groups related buttons together with consistent styling.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/button-group
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add button-group
# or: npx shadcn-vue@latest add button-group
# or: yarn dlx shadcn-vue@latest add button-group
# or: bunx --bun shadcn-vue@latest add button-group
```

## Usage

```vue
<script setup lang="ts">
import {
  ButtonGroup,
  ButtonGroupSeparator,
  ButtonGroupText,
} from '@/components/ui/button-group'
</script>

<template>
  <ButtonGroup>
    <Button>Button 1</Button>
    <Button>Button 2</Button>
  </ButtonGroup>
</template>
```
