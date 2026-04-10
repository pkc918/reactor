## Tab Views

A tab view presents multiple mutually exclusive panes of content in the same area, which people can switch between using a tabbed control.

## Best Practices

**Use a tab view to present closely related areas of content.** A tab view provides a strong visual sense of enclosure, so people expect each tab to hold content that is similar or related to the others.

**Make sure the controls within a pane affect content only in the same pane.** Panes are mutually exclusive, so each one should be fully self-contained.

**Provide a label for each tab that describes the contents of its pane.** A good label lets people predict what's inside before they click or tap. Generally use nouns or short noun phrases (a verb or short verb phrase can fit in some contexts), with title-style capitalization.

**Avoid using a pop-up button to switch between tabs.** A tabbed control selects in a single click and shows every choice on screen at once, while a pop-up button needs two clicks and hides options until opened. A pop-up button can be a reasonable fallback when there are too many panes to display as tabs.

**Avoid providing more than six tabs in a tab view.** More than six tabs become overwhelming and create layout problems. If you need that many, consider another approach — for example, presenting each option from a pop-up button menu.

## Anatomy

The tabbed control sits along the top edge of the content area. You can hide the control entirely, which suits an app that switches between panes programmatically.

When the tabbed control is hidden, the content area can be borderless, bezeled, or bordered with a line. A borderless view can be solid or transparent.

**In general, inset a tab view by leaving a margin of window-body area on all sides.** This produces a clean layout and leaves room for additional controls that aren't directly tied to the tab view's contents. Extending a tab view to the window edges is possible but unusual.
