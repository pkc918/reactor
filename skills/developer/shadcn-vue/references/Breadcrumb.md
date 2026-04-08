---
title: Breadcrumb (shadcn-vue)
description: >-
  Displays the path to the current resource using a hierarchy of links.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/breadcrumb
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add breadcrumb
# or: npx shadcn-vue@latest add breadcrumb
# or: yarn dlx shadcn-vue@latest add breadcrumb
# or: bunx --bun shadcn-vue@latest add breadcrumb
```

## Usage

```vue
<script setup lang="ts">
import {
  Breadcrumb,
  BreadcrumbItem,
  BreadcrumbLink,
  BreadcrumbList,
  BreadcrumbPage,
  BreadcrumbSeparator,
} from '@/components/ui/breadcrumb'
</script>

<template>
  <Breadcrumb>
    <BreadcrumbList>
      <BreadcrumbItem>
        <BreadcrumbLink href="/">
          Home
        </BreadcrumbLink>
      </BreadcrumbItem>
      <BreadcrumbSeparator />
      <BreadcrumbItem>
        <BreadcrumbLink href="/components">
          Components
        </BreadcrumbLink>
      </BreadcrumbItem>
      <BreadcrumbSeparator />
      <BreadcrumbItem>
        <BreadcrumbPage>Breadcrumb</BreadcrumbPage>
      </BreadcrumbItem>
    </BreadcrumbList>
  </Breadcrumb>
</template>
```
