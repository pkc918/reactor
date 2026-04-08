---
title: Date Picker (shadcn-vue + Reka UI)
description: >-
  A date picker component with range and presets.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/date-picker
  reka-doc: https://reka-ui.com/docs/components/date-picker
  reka-api: https://reka-ui.com/docs/components/date-picker#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add date-picker
# or: npx shadcn-vue@latest add date-picker
# or: yarn dlx shadcn-vue@latest add date-picker
# or: bunx --bun shadcn-vue@latest add date-picker
```

## Usage

```vue
<script setup lang="ts">
import { DateFormatter, getLocalTimeZone, today } from '@internationalized/date'
import { CalendarIcon } from 'lucide-vue-next'
import { ref } from 'vue'
import { Button } from '@/components/ui/button'
import { Calendar } from '@/components/ui/calendar'
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from '@/components/ui/popover'
import { cn } from '@/lib/utils'

const date = ref<Date>()
const defaultPlaceholder = today(getLocalTimeZone())
</script>

<template>
  <Popover>
    <PopoverTrigger as-child>
      <Button
        variant="outline"
        :class="cn(
          'w-[280px] justify-start text-left font-normal',
          !date && 'text-muted-foreground',
        )"
      >
        <CalendarIcon class="mr-2 h-4 w-4" />
        {{ date ? date.toDateString() : "Pick a date" }}
      </Button>
    </PopoverTrigger>
    <PopoverContent class="w-auto p-0">
      <Calendar
        v-model="date"
        :initial-focus="true"
        :default-placeholder="defaultPlaceholder"
        layout="month-and-year"
      />
    </PopoverContent>
  </Popover>
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a date picker




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `closeOnSelect` | Whether or not to close the popover on date select | `boolean` | No | `false` |
| `defaultOpen` | The open state of the popover when it is initially rendered. Use when you do not need to control its open state. | `boolean` | No | `false` |
| `defaultPlaceholder` | The default placeholder date | `DateValue` | No | - |
| `defaultValue` | The default value for the calendar | `DateValue` | No | - |
| `dir` | The reading direction of the date field when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | Whether or not the date field is disabled | `boolean` | No | `false` |
| `fixedWeeks` | Whether or not to always display 6 weeks in the calendar | `boolean` | No | `false` |
| `granularity` | The granularity to use for formatting times. Defaults to day if a CalendarDate is provided, otherwise defaults to minute. The field will render segments for each part of the date up to and including the specified granularity | `"day" \| "hour" \| "minute" \| "second"` | No | - |
| `hideTimeZone` | Whether or not to hide the time zone segment of the field | `boolean` | No | - |
| `hourCycle` | The hour cycle used for formatting times. Defaults to the local preference | `12 \| 24` | No | - |
| `id` | Id of the element | `string` | No | - |
| `isDateDisabled` | A function that returns whether or not a date is disabled | `Matcher` | No | - |
| `isDateUnavailable` | A function that returns whether or not a date is unavailable | `Matcher` | No | - |
| `locale` | The locale to use for formatting dates | `string` | No | - |
| `maxValue` | The maximum date that can be selected | `DateValue` | No | - |
| `minValue` | The minimum date that can be selected | `DateValue` | No | - |
| `modal` | The modality of the popover. When set to true, interaction with outside elements will be disabled and only popover content will be visible to screen readers. | `boolean` | No | `false` |
| `modelValue` | The controlled value of the field. Can be bound as v-model. | `DateValue \| null` | No | - |
| `name` | The name of the field. Submitted with its owning form as part of a name/value pair. | `string` | No | - |
| `numberOfMonths` | The number of months to display at once | `number` | No | `1` |
| `open` | The controlled open state of the popover. | `boolean` | No | - |
| `pagedNavigation` | This property causes the previous and next buttons to navigate by the number of months displayed at once, rather than one month | `boolean` | No | `false` |
| `placeholder` | The placeholder date, which is used to determine what month to display when no date is selected. This updates as the user navigates the calendar and can be used to programmatically control the calendar view | `DateValue` | No | - |
| `preventDeselect` | Whether or not to prevent the user from deselecting a date without selecting another date first | `boolean` | No | `false` |
| `readonly` | Whether or not the date field is readonly | `boolean` | No | `false` |
| `required` | When true, indicates that the user must set the value before the owning form can be submitted. | `boolean` | No | - |
| `step` | The stepping interval for the time fields. Defaults to 1. | `DateStep` | No | - |
| `weekdayFormat` | The format to use for the weekday strings provided via the weekdays slot prop | `"narrow" \| "short" \| "long"` | No | `"narrow"` |
| `weekStartsOn` | The day of the week to start the calendar on | `0 \| 1 \| 2 \| 3 \| 4 \| 5 \| 6` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called whenever the model value changes | `[date: DateValue]` |
| `update:open` | Event handler called when the open state of the submenu changes. | `[value: boolean]` |
| `update:placeholder` | Event handler called whenever the placeholder value changes | `[date: DateValue]` |

**Methods**

| Name | Description | Type |
| --- | --- | --- |
| `isDateDisabled` | A function that returns whether or not a date is disabled | `Matcher` |
| `isDateUnavailable` | A function that returns whether or not a date is unavailable | `Matcher` |

### Field

Contains the date picker date field segments and trigger




**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `segments` |  | `{ part: SegmentPart; value: string; }[]` |
| `modelValue` |  | `DateValue \| undefined` |

### Input

Contains the date picker date field segments

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `part` | The part of the date to render | `"day" \| "month" \| "year" \| "hour" \| "minute" \| "second" \| "dayPeriod" \| "literal" \| "timeZoneName"` | Yes | - |

### Trigger

The button that toggles the popover. By default, the `DatePickerContent` will position itself against the trigger.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Content

The component that pops out when the popover is open.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `align` | The preferred alignment against the trigger. May change when collisions occur. | `"start" \| "center" \| "end"` | No | - |
| `alignFlip` | Flip alignment when colliding with boundary. May only occur when prioritizePosition is true. | `boolean` | No | - |
| `alignOffset` | An offset in pixels from the start or end alignment options. | `number` | No | - |
| `arrowPadding` | The padding between the arrow and the edges of the content. If your content has border-radius, this will prevent it from overflowing the corners. | `number` | No | - |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `avoidCollisions` | When true, overrides the side and align preferences to prevent collisions with boundary edges. | `boolean` | No | - |
| `collisionBoundary` | The element used as the collision boundary. By default this is the viewport, though you can provide additional element(s) to be included in this check. | `Element \| (Element \| null)[] \| null` | No | - |
| `collisionPadding` | The distance in pixels from the boundary edges where collision detection should occur. Accepts a number (same for all sides), or a partial padding object, for example: { top: 20, left: 20 }. | `number \| Partial<Record<"top" \| "right" \| "bottom" \| "left", number>>` | No | - |
| `disableOutsidePointerEvents` | When true, hover/focus/click interactions will be disabled on elements outside the DismissableLayer. Users will need to click twice on outside elements to interact with them: once to close the DismissableLayer, and again to trigger the element. | `boolean` | No | - |
| `disableUpdateOnLayoutShift` | Whether to disable the update position for the content when the layout shifted. | `boolean` | No | - |
| `forceMount` | Used to force mounting when more control is needed. Useful when controlling animation with Vue animation libraries. | `boolean` | No | - |
| `hideShiftedArrow` | When true, hides the arrow when it cannot be centered to the reference element. | `boolean` | No | - |
| `hideWhenDetached` | Whether to hide the content when the trigger becomes fully occluded. | `boolean` | No | - |
| `portal` | Props to control the portal wrapped around the content. | `PopoverPortalProps` | No | - |
| `positionStrategy` | The type of CSS position property to use. | `"fixed" \| "absolute"` | No | - |
| `prioritizePosition` | Force content to be position within the viewport. Might overlap the reference element, which may not be desired. | `boolean` | No | - |
| `reference` | The custom element or virtual element that will be set as the reference to position the floating element. If provided, it will replace the default anchor element. | `ReferenceElement` | No | - |
| `side` | The preferred side of the trigger to render against when open. Will be reversed when collisions occur and avoidCollisions is enabled. | `"top" \| "right" \| "bottom" \| "left"` | No | - |
| `sideFlip` | Flip to the opposite side when colliding with boundary. | `boolean` | No | - |
| `sideOffset` | The distance in pixels from the trigger. | `number` | No | - |
| `sticky` | The sticky behavior on the align axis. partial will keep the content in the boundary as long as the trigger is at least partially in the boundary whilst "always" will keep the content in the boundary regardless. | `"partial" \| "always"` | No | - |
| `updatePositionStrategy` | Strategy to update the position of the floating element on every animation frame. | `"always" \| "optimized"` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `closeAutoFocus` | Event handler called when auto-focusing on close. Can be prevented. | `[event: Event]` |
| `escapeKeyDown` | Event handler called when the escape key is down. Can be prevented. | `[event: KeyboardEvent]` |
| `focusOutside` | Event handler called when the focus moves outside of the DismissableLayer. Can be prevented. | `[event: FocusOutsideEvent]` |
| `interactOutside` | Event handler called when an interaction happens outside the DismissableLayer. Specifically, when a pointerdown event happens outside or focus moves outside of it. Can be prevented. | `[event: PointerDownOutsideEvent \| FocusOutsideEvent]` |
| `openAutoFocus` | Event handler called when auto-focusing on open. Can be prevented. | `[event: Event]` |
| `pointerDownOutside` | Event handler called when a pointerdown event happens outside of the DismissableLayer. Can be prevented. | `[event: PointerDownOutsideEvent]` |

### Arrow

An optional arrow element to render alongside the popover. This can be used to help visually link the anchor with the `DatePickerContent`. Must be rendered inside `DatePickerContent`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `height` | The height of the arrow in pixels. | `number` | No | - |
| `rounded` | When true, render the rounded version of arrow. Do not work with as/asChild | `boolean` | No | - |
| `width` | The width of the arrow in pixels. | `number` | No | - |

### Close

The button that closes an open date picker.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Anchor

An optional element to position the `DatePickerContent` against. If this part is not used, the content will position alongside the `DatePickerTrigger`.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `reference` | The reference (or anchor) element that is being referred to for positioning. If not provided will use the current component as anchor. | `ReferenceElement` | No | - |

### Calendar

Contains all the parts of a calendar




**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `date` |  | `DateValue` |
| `grid` |  | `Grid<DateValue>[]` |
| `weekDays` |  | `string[]` |
| `weekStartsOn` |  | `0 \| 1 \| 2 \| 3 \| 4 \| 5 \| 6` |
| `locale` |  | `string` |
| `fixedWeeks` |  | `boolean` |

### Header

Contains the navigation buttons and the heading segments.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Prev Button

Calendar navigation button. It navigates the calendar one month/year/decade in the past based on the current calendar view.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `prevPage` | The function to be used for the prev page. Overwrites the prevPage function set on the CalendarRoot. | `((placeholder: DateValue) => DateValue)` | No | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `disabled` | Current disable state | `boolean` |

### Next Button

Calendar navigation button. It navigates the calendar one month/year/decade in the future based on the current calendar view.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `nextPage` | The function to be used for the next page. Overwrites the nextPage function set on the CalendarRoot. | `((placeholder: DateValue) => DateValue)` | No | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `disabled` | Current disable state | `boolean` |

### Heading

Heading for displaying the current month and year/




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `headingValue` | Current month and year | `string` |

### Grid

Container for wrapping the calendar grid.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Grid Head

Container for wrapping the grid head.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Grid Body

Container for wrapping the grid body.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Grid Row

Container for wrapping the grid row.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Head Cell

Container for wrapping the head cell. Used for displaying the week days.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Cell

Container for wrapping the calendar cells.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `date` | The date value for the cell | `DateValue` | Yes | - |

### Cell Trigger

Interactable container for displaying the cell dates. Clicking it selects the date.




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `day` | The date value provided to the cell trigger | `DateValue` | Yes | - |
| `month` | The month in which the cell is rendered | `DateValue` | Yes | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `dayValue` | Current day | `string` |
| `disabled` | Current disable state | `boolean` |
| `selected` | Current selected state | `boolean` |
| `today` | Current today state | `boolean` |
| `outsideView` | Current outside view state | `boolean` |
| `outsideVisibleView` | Current outside visible view state | `boolean` |
| `unavailable` | Current unavailable state | `boolean` |
