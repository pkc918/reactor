## Labels

A label is a static piece of text that people can read and often copy, but not edit.

Labels display text throughout the interface — in buttons, menu items, and views — helping people understand the current context and what they can do next.

The term *label* refers to uneditable text that can appear in various places. For example:

- Within a button, a label generally conveys what the button does, such as Edit, Cancel, or Send.
- Within many lists, a label can describe each item, often accompanied by a symbol or an image.
- Within a view, a label might provide additional context by introducing a control or describing a common action or task that people can perform in the view.

## Best Practices

**Use a label to display a small amount of text that people don't need to edit.** If you need to let people edit a small amount of text, use a text field. If you need to display a large amount of text, and optionally let people edit it, use a text view.

**Prefer system fonts.** A label can display plain or styled text, and it supports Dynamic Type (where available) by default. If you adjust the style of a label or use custom fonts, make sure the text remains legible.

**Use system-provided label colors to communicate relative importance.** The system defines four label colors that vary in appearance to help you give text different levels of visual importance.

| System color      | Example usage                                  | iOS, iPadOS, tvOS, visionOS | macOS                   |
|-------------------|------------------------------------------------|-----------------------------|-------------------------|
| Label             | Primary information                            | `label`                     | `labelColor`            |
| Secondary label   | A subheading or supplemental text              | `secondaryLabel`            | `secondaryLabelColor`   |
| Tertiary label    | Text that describes an unavailable item or behavior | `tertiaryLabel`        | `tertiaryLabelColor`    |
| Quaternary label  | Watermark text                                 | `quaternaryLabel`           | `quaternaryLabelColor`  |

**Make useful label text selectable.** If a label contains useful information — like an error message, a location, or an IP address — consider letting people select and copy it for pasting elsewhere.
