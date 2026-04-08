---
title: Stepper (shadcn-vue + Reka UI)
description: >-
  A set of steps that are used to indicate progress through a multi-step process.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/stepper
  reka-doc: https://reka-ui.com/docs/components/stepper
  reka-api: https://reka-ui.com/docs/components/stepper#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add stepper
# or: npx shadcn-vue@latest add stepper
# or: yarn dlx shadcn-vue@latest add stepper
# or: bunx --bun shadcn-vue@latest add stepper
```

## Usage

```vue
<script setup lang="ts">
import {
  Stepper,
  StepperDescription,
  StepperIndicator,
  StepperItem,
  StepperSeparator,
  StepperTitle,
  StepperTrigger,
} from '@/components/ui/stepper'
</script>

<template>
  <Stepper>
    <StepperItem :step="1">
      <StepperTrigger>
        <StepperIndicator>1</StepperIndicator>
        <StepperTitle>Step 1</StepperTitle>
        <StepperDescription>This is the first step</StepperDescription>
      </StepperTrigger>
      <StepperSeparator />
    </StepperItem>
    <StepperItem :step="2">
      <StepperTrigger>
        <StepperIndicator>2</StepperIndicator>
        <StepperTitle>Step 2</StepperTitle>
        <StepperDescription>This is the second step</StepperDescription>
      </StepperTrigger>
    </StepperItem>
  </Stepper>
</template>
```

## Reka UI API reference

### Root

Contains all the stepper component parts.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `defaultValue` | The value of the step that should be active when initially rendered. Use when you do not need to control the state of the steps. | `number` | No | `1` |
| `dir` | The reading direction of the combobox when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `linear` | Whether or not the steps must be completed in order. | `boolean` | No | `true` |
| `modelValue` | The controlled value of the step to activate. Can be bound as v-model. | `number` | No | - |
| `orientation` | The orientation the steps are laid out. Mainly so arrow navigation is done accordingly (left & right vs. up & down). | `"vertical" \| "horizontal"` | No | `"horizontal"` |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called when the value changes | `[payload: number]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `modelValue` | Current step | `number \| undefined` |
| `totalSteps` | Total number of steps | `number` |
| `isNextDisabled` | Whether or not the next step is disabled | `boolean` |
| `isPrevDisabled` | Whether or not the previous step is disabled | `boolean` |
| `isFirstStep` | Whether or not the first step is active | `boolean` |
| `isLastStep` | Whether or not the last step is active | `boolean` |
| `goToStep` | Go to a specific step | `(step: number): void` |
| `nextStep` | Go to the next step | `(): void` |
| `prevStep` | Go to the previous step | `(): void` |
| `hasNext` | Whether or not there is a next step | `(): boolean` |
| `hasPrev` | Whether or not there is a previous step | `(): boolean` |

**Methods**

| Name | Description | Type |
| --- | --- | --- |
| `goToStep` |  | `(step: number) => void` |
| `nextStep` |  | `() => void` |
| `prevStep` |  | `() => void` |
| `hasNext` |  | `() => boolean` |
| `hasPrev` |  | `() => boolean` |

### Item

The step item component.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `completed` | Shows whether the step is completed. | `boolean` | No | `false` |
| `disabled` | When true, prevents the user from interacting with the step. | `boolean` | No | `false` |
| `step` | A unique value that associates the stepper item with an index | `number` | Yes | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `state` | The current state of the stepper item | `"active" \| "completed" \| "inactive"` |

### Trigger

The trigger that toggles the step.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Indicator

The indicator for the step.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `step` | Current step | `number` |

### Title

An accessible title to be announced when the stepper trigger is focused.

If you want to hide the title, wrap it inside our Visually Hidden utility like this `<VisuallyHidden asChild>`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"h4"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Description

An optional accessible description to be announced when the stepper trigger is focused.

If you want to hide the description, wrap it inside our Visually Hidden utility like this `<VisuallyHidden asChild>`. If you want to remove the description entirely, remove this part and pass `aria-describedby="undefined"` to `StepperTrigger`.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `completed` | Shows whether the step is completed. | `boolean` | No | `false` |
| `disabled` | When true, prevents the user from interacting with the step. | `boolean` | No | `false` |
| `step` | A unique value that associates the stepper item with an index | `number` | Yes | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `state` | The current state of the stepper item | `"active" \| "completed" \| "inactive"` |
