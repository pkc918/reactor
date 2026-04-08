---
title: Input OTP (shadcn-vue)
description: >-
  Accessible one-time password component with copy paste functionality.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/input-otp
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add input-otp
# or: npx shadcn-vue@latest add input-otp
# or: yarn dlx shadcn-vue@latest add input-otp
# or: bunx --bun shadcn-vue@latest add input-otp
```

## Usage

```vue
<script setup lang="ts">
import {
  InputOTP,
  InputOTPGroup,
  InputOTPSeparator,
  InputOTPSlot,
} from '@/components/ui/input-otp'
</script>

<template>
  <InputOTP v-model="value" :maxlength="6">
    <InputOTPGroup>
      <InputOTPSlot :index="0" />
      <InputOTPSlot :index="1" />
      <InputOTPSlot :index="2" />
    </InputOTPGroup>
    <InputOTPSeparator />
    <InputOTPGroup>
      <InputOTPSlot :index="3" />
      <InputOTPSlot :index="4" />
      <InputOTPSlot :index="5" />
    </InputOTPGroup>
  </InputOTP>
</template>
```
