---
title: Carousel (shadcn-vue)
description: >-
  A carousel with motion and swipe built using Embla.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/carousel
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add carousel
# or: npx shadcn-vue@latest add carousel
# or: yarn dlx shadcn-vue@latest add carousel
# or: bunx --bun shadcn-vue@latest add carousel
```

## Usage

```vue
<script setup lang="ts">
import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from '@/components/ui/carousel'
</script>

<template>
  <Carousel>
    <CarouselContent>
      <CarouselItem>...</CarouselItem>
      <CarouselItem>...</CarouselItem>
      <CarouselItem>...</CarouselItem>
    </CarouselContent>
    <CarouselPrevious />
    <CarouselNext />
  </Carousel>
</template>
```
