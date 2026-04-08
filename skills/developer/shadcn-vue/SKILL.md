---
name: shadcn-vue
description: >-
  shadcn-vue component docs in-repo: CLI install, Vue usage, Reka API when
  applicable. Use for shadcn-vue / Reka UI questions in Vue.
---

# shadcn-vue

Per-component reference files live under [`references/`](references/). Each file mirrors the [shadcn/vue docs](https://shadcn-vue.com/docs/components): **Installation** (pnpm / npx / yarn / bun), **Usage** (imports + template), and **`## Reka UI API reference`** only when [Reka UI](https://reka-ui.com/docs) documents that primitive.

## How to use this skill

1. **Identify the component** from the [shadcn/vue Components](https://shadcn-vue.com/docs/components) sidebar (first column); use the short **Summary** to tell similar items apart.
2. **Open the linked reference** (third column). Full official one-line description is in that file’s YAML `description`, same as the doc page.
3. **Follow that file** for Installation, Usage, and optional Reka API. Do not invent APIs; stub upstream pages may have an empty or placeholder Usage block.

## Component → summary → reference file

| Component (shadcn-vue) | Summary | Reference file |
| --- | --- | --- |
| Accordion | Expandable sections with headings | [Accordion.md](references/Accordion.md) |
| Alert | Inline callout for attention | [Alert.md](references/Alert.md) |
| Alert Dialog | Modal that needs explicit response | [AlertDialog.md](references/AlertDialog.md) |
| Aspect Ratio | Constrain content to a ratio | [AspectRatio.md](references/AspectRatio.md) |
| Avatar | User image + fallback | [Avatar.md](references/Avatar.md) |
| Badge | Small label / count chip | [Badge.md](references/Badge.md) |
| Breadcrumb | Hierarchy path links | [Breadcrumb.md](references/Breadcrumb.md) |
| Button | Primary clickable control | [Button.md](references/Button.md) |
| Button Group | Grouped related buttons | [ButtonGroup.md](references/ButtonGroup.md) |
| Calendar | Pick / edit a date | [Calendar.md](references/Calendar.md) |
| Card | Header + content + footer | [Card.md](references/Card.md) |
| Carousel | Swipeable slides (Embla) | [Carousel.md](references/Carousel.md) |
| Chart | Charts (Unovis) | [Chart.md](references/Chart.md) |
| Checkbox | Checked / unchecked | [Checkbox.md](references/Checkbox.md) |
| Collapsible | Show / hide a panel | [Collapsible.md](references/Collapsible.md) |
| Combobox | Autocomplete + list | [Combobox.md](references/Combobox.md) |
| Command | Command palette / menu | [Command.md](references/Command.md) |
| Context Menu | Right-click menu | [ContextMenu.md](references/ContextMenu.md) |
| Data Table | TanStack data grid | [DataTable.md](references/DataTable.md) |
| Date Picker | Dates, range, presets | [DatePicker.md](references/DatePicker.md) |
| Dialog | Modal overlay | [Dialog.md](references/Dialog.md) |
| Drawer | Mobile slide-over | [Drawer.md](references/Drawer.md) |
| Dropdown Menu | Menu from a button | [DropdownMenu.md](references/DropdownMenu.md) |
| Empty | Empty state UI | [Empty.md](references/Empty.md) |
| Field | Label + control + help | [Field.md](references/Field.md) |
| Form | VeeValidate + Zod | [Form.md](references/Form.md) |
| Hover Card | Preview on hover / focus | [HoverCard.md](references/HoverCard.md) |
| Input | Text field | [Input.md](references/Input.md) |
| Input Group | Input with add-ons | [InputGroup.md](references/InputGroup.md) |
| Input OTP | OTP / copy-paste codes | [InputOtp.md](references/InputOtp.md) |
| Item | Generic content row / block | [Item.md](references/Item.md) |
| Kbd | Keyboard key styling | [Kbd.md](references/Kbd.md) |
| Label | Form control label | [Label.md](references/Label.md) |
| Menubar | Desktop menu bar | [Menubar.md](references/Menubar.md) |
| Native Select | Styled native select | [NativeSelect.md](references/NativeSelect.md) |
| Navigation Menu | Site nav links | [NavigationMenu.md](references/NavigationMenu.md) |
| Number Field | Number + stepper | [NumberField.md](references/NumberField.md) |
| Pagination | Page links | [Pagination.md](references/Pagination.md) |
| Pin Input | PIN entry (see also Input OTP) | [PinInput.md](references/PinInput.md) |
| Popover | Anchored overlay content | [Popover.md](references/Popover.md) |
| Progress | Progress bar | [Progress.md](references/Progress.md) |
| Radio Group | Single choice radios | [RadioGroup.md](references/RadioGroup.md) |
| Range Calendar | Pick a date range | [RangeCalendar.md](references/RangeCalendar.md) |
| Resizable | Split / resize panes | [Resizable.md](references/Resizable.md) |
| Scroll Area | Styled scroll container | [ScrollArea.md](references/ScrollArea.md) |
| Select | Button-triggered listbox | [Select.md](references/Select.md) |
| Separator | Divider line / gap | [Separator.md](references/Separator.md) |
| Sheet | Side / bottom sheet | [Sheet.md](references/Sheet.md) |
| Sidebar | App sidebar shell | [Sidebar.md](references/Sidebar.md) |
| Skeleton | Loading placeholder | [Skeleton.md](references/Skeleton.md) |
| Slider | Value on a range | [Slider.md](references/Slider.md) |
| Sonner | Toast stack (opinionated) | [Sonner.md](references/Sonner.md) |
| Spinner | Loading indicator | [Spinner.md](references/Spinner.md) |
| Stepper | Multi-step progress | [Stepper.md](references/Stepper.md) |
| Switch | On / off toggle | [Switch.md](references/Switch.md) |
| Table | Responsive table | [Table.md](references/Table.md) |
| Tabs | Tab panels, one visible | [Tabs.md](references/Tabs.md) |
| Tags Input | Tags inside a field | [TagsInput.md](references/TagsInput.md) |
| Textarea | Multiline text | [Textarea.md](references/Textarea.md) |
| Toast | Temporary message | [Toast.md](references/Toast.md) |
| Toggle | Two-state button | [Toggle.md](references/Toggle.md) |
| Toggle Group | Multiple toggles | [ToggleGroup.md](references/ToggleGroup.md) |
| Tooltip | Hover / focus hint | [Tooltip.md](references/Tooltip.md) |
| Typography | Text / heading utilities | [Typography.md](references/Typography.md) |

## Regenerating references

To refresh all files from official sources, run from the repo root:

```bash
node scripts/generate-shadcn-vue-references.mjs
```

The Cursor command [`.cursor/commands/shadcn.md`](../../../.cursor/commands/shadcn.md) describes the intended shape of each reference when generating or editing by hand.
