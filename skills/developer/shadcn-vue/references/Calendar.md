---
title: Calendar (shadcn-vue + Reka UI)
description: >-
  A date field component that allows users to enter and edit date.
component: true
links:
  shadcn-vue: https://shadcn-vue.com/docs/components/calendar
  reka-doc: https://reka-ui.com/docs/components/calendar
  reka-api: https://reka-ui.com/docs/components/calendar#api-reference
---

## Installation

```bash
pnpm dlx shadcn-vue@latest add calendar
# or: npx shadcn-vue@latest add calendar
# or: yarn dlx shadcn-vue@latest add calendar
# or: bunx --bun shadcn-vue@latest add calendar
```

## Usage

```vue
<script setup lang="ts">
import { Calendar } from '@/components/ui/calendar'
</script>

<template>
  <Calendar />
</template>
```

## Reka UI API reference

### Root

Contains all the parts of a calendar




**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"div"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `calendarLabel` | The accessible label for the calendar | `string` | No | - |
| `defaultPlaceholder` | The default placeholder date | `DateValue` | No | - |
| `defaultValue` | The default value for the calendar | `DateValue` | No | - |
| `dir` | The reading direction of the calendar when applicable.  If omitted, inherits globally from ConfigProvider or assumes LTR (left-to-right) reading mode. | `"ltr" \| "rtl"` | No | - |
| `disabled` | Whether the calendar is disabled | `boolean` | No | `false` |
| `disableDaysOutsideCurrentView` | Whether or not to disable days outside the current view. | `boolean` | No | `false` |
| `fixedWeeks` | Whether or not to always display 6 weeks in the calendar | `boolean` | No | `false` |
| `initialFocus` | If true, the calendar will focus the selected day, today, or the first day of the month depending on what is visible when the calendar is mounted | `boolean` | No | `false` |
| `isDateDisabled` | A function that returns whether or not a date is disabled | `Matcher` | No | - |
| `isDateUnavailable` | A function that returns whether or not a date is unavailable | `Matcher` | No | - |
| `locale` | The locale to use for formatting dates | `string` | No | - |
| `maxValue` | The maximum date that can be selected | `DateValue` | No | - |
| `minValue` | The minimum date that can be selected | `DateValue` | No | - |
| `modelValue` | The controlled selected date value of the calendar. Can be bound as v-model. | `DateValue \| DateValue[]` | No | - |
| `multiple` | Whether multiple dates can be selected | `boolean` | No | `false` |
| `nextPage` | A function that returns the next page of the calendar. It receives the current placeholder as an argument inside the component. | `((placeholder: DateValue) => DateValue)` | No | - |
| `numberOfMonths` | The number of months to display at once | `number` | No | `1` |
| `pagedNavigation` | This property causes the previous and next buttons to navigate by the number of months displayed at once, rather than one month | `boolean` | No | `false` |
| `placeholder` | The placeholder date, which is used to determine what month to display when no date is selected | `DateValue` | No | - |
| `preventDeselect` | Whether or not to prevent the user from deselecting a date without selecting another date first | `boolean` | No | `false` |
| `prevPage` | A function that returns the previous page of the calendar. It receives the current placeholder as an argument inside the component. | `((placeholder: DateValue) => DateValue)` | No | - |
| `readonly` | Whether the calendar is readonly | `boolean` | No | `false` |
| `weekdayFormat` | The format to use for the weekday strings provided via the weekdays slot prop | `"narrow" \| "short" \| "long"` | No | `"narrow"` |
| `weekStartsOn` | The day of the week to start the calendar on | `0 \| 1 \| 2 \| 3 \| 4 \| 5 \| 6` | No | - |

**Events**

| Name | Description | Type |
| --- | --- | --- |
| `update:modelValue` | Event handler called whenever the model value changes | `[date: DateValue]` |
| `update:placeholder` | Event handler called whenever the placeholder value changes | `[date: DateValue]` |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `date` | The current date of the placeholder | `DateValue` |
| `grid` | The grid of dates | `Grid<DateValue>[]` |
| `weekDays` | The days of the week | `string[]` |
| `weekStartsOn` | The start of the week | `0 \| 1 \| 2 \| 3 \| 4 \| 5 \| 6` |
| `locale` | The calendar locale | `string` |
| `fixedWeeks` | Whether or not to always display 6 weeks in the calendar | `boolean` |
| `modelValue` | The current date of the calendar | `DateValue \| DateValue[] \| undefined` |

**Methods**

| Name | Description | Type |
| --- | --- | --- |
| `isDateDisabled` | A function that returns whether or not a date is disabled | `Matcher` |
| `isDateUnavailable` | A function that returns whether or not a date is unavailable | `Matcher` |

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
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
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
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"button"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |
| `nextPage` | The function to be used for the next page. Overwrites the nextPage function set on the CalendarRoot. | `((placeholder: DateValue) => DateValue)` | No | - |

**Slots**

| Name | Description | Type |
| --- | --- | --- |
| `disabled` | Current disable state | `boolean` |

### Heading

Heading for displaying the current month and year




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
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"table"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Grid Head

Container for wrapping the grid head.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"thead"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Grid Body

Container for wrapping the grid body.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"tbody"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Grid Row

Container for wrapping the grid row.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"tr"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Head Cell

Container for wrapping the head cell. Used for displaying the week days.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"th"` |
| `asChild` | Change the default rendered element for the one passed as a child, merging their props and behavior. Read our Composition guide for more details. | `boolean` | No | - |

### Cell

Container for wrapping the calendar cells.

**Props**

| Name | Description | Type | Required | Default |
| --- | --- | --- | --- | --- |
| `as` | The element or component this component should render as. Can be overwritten by asChild. | `AsTag \| Component` | No | `"td"` |
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
