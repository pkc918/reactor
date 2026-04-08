---
title: Field (shadcn-vue)
description: >-
  Combine labels, controls, and help text to compose accessible form fields and grouped inputs.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/field
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add field
# or: npx shadcn-vue@latest add field
# or: yarn dlx shadcn-vue@latest add field
# or: bunx --bun shadcn-vue@latest add field
```

## Usage

```vue
<script setup lang="ts">
import {
  Field,
  FieldContent,
  FieldDescription,
  FieldError,
  FieldGroup,
  FieldLabel,
  FieldLegend,
  FieldSeparator,
  FieldSet,
  FieldTitle,
} from '@/components/ui/field'
</script>

<template>
  <FieldSet>
    <FieldLegend>Profile</FieldLegend>
    <FieldDescription>This appears on invoices and emails.</FieldDescription>
    <FieldGroup>
      <Field>
        <FieldLabel for="name">
          Full name
        </FieldLabel>
        <Input id="name" autocomplete="off" placeholder="Evil Rabbit" />
        <FieldDescription>This appears on invoices and emails.</FieldDescription>
      </Field>
      <Field>
        <FieldLabel for="username">
          Username
        </FieldLabel>
        <Input id="username" autocomplete="off" aria-invalid />
        <FieldError>Choose another username.</FieldError>
      </Field>
      <Field orientation="horizontal">
        <Switch id="newsletter" />
        <FieldLabel for="newsletter">
          Subscribe to the newsletter
        </FieldLabel>
      </Field>
    </FieldGroup>
  </FieldSet>
</template>
```
