---
title: Native Select (shadcn-vue)
description: >-
  A styled native HTML select element with consistent design system integration.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/native-select
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add native-select
# or: npx shadcn-vue@latest add native-select
# or: yarn dlx shadcn-vue@latest add native-select
# or: bunx --bun shadcn-vue@latest add native-select
```

## Usage

```vue
<script setup lang="ts">
import {
  NativeSelect,
  NativeSelectOptGroup,
  NativeSelectOption,
} from '@/components/ui/native-select'
</script>

<template>
  <NativeSelect>
    <NativeSelectOption value="">
      Select a fruit
    </NativeSelectOption>
    <NativeSelectOption value="apple">
      Apple
    </NativeSelectOption>
    <NativeSelectOption value="banana">
      Banana
    </NativeSelectOption>
    <NativeSelectOption value="blueberry">
      Blueberry
    </NativeSelectOption>
    <NativeSelectOption value="grapes" disabled>
      Grapes
    </NativeSelectOption>
    <NativeSelectOption value="pineapple">
      Pineapple
    </NativeSelectOption>
  </NativeSelect>
</template>
```
