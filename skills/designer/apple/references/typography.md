## Typography

Typographic choices help you display legible text, convey an information hierarchy, communicate important content, and express your brand or style.

## Ensuring Legibility

**Use font sizes most people can read easily.** Text should be readable at typical viewing distances and in varied conditions. Stick to each platform's recommended default and minimum sizes — for both system and custom fonts — and bear in mind that weight affects legibility too. Push thin custom weights above the recommended sizes.

| Platform | Default size | Minimum size |
|---|---|---|
| iOS, iPadOS | 17 pt | 11 pt |
| macOS | 13 pt | 10 pt |
| tvOS | 29 pt | 23 pt |
| visionOS | 17 pt | 12 pt |
| watchOS | 16 pt | 12 pt |

**Test legibility in real contexts.** Game text in particular needs verification on every platform you ship on. If something is hard to read, increase the type size, raise contrast against the background, or switch to a typeface optimized for legibility — including the system fonts.

**Avoid light font weights in general.** With system fonts, prefer Regular, Medium, Semibold, or Bold. Ultralight, Thin, and Light tend to disappear, especially at small sizes.

## Conveying Hierarchy

**Use weight, size, and color to highlight important information.** Preserve the relative hierarchy and visual contrast of text elements when people change text sizes.

**Limit the number of typefaces.** Mixing too many typefaces muddles the hierarchy and makes the interface feel inconsistent.

**Prioritize the most important content during text-size changes.** When someone bumps up text size, they care most about the meaningful content — not every word on the screen. Tab titles in a window or transient hit-damage numbers in a game don't need to grow alongside the body text or character dialog.

## Using System Fonts

Apple ships two typeface families that cover a wide range of weights, sizes, styles, and languages.

- **San Francisco (SF)** — a sans serif family that includes SF Pro, SF Compact, SF Arabic, SF Armenian, SF Georgian, SF Hebrew, and SF Mono. Most variants also have rounded versions, useful for pairing text with soft or rounded UI.
- **New York (NY)** — a serif family designed to work both on its own and alongside the SF fonts.

The system provides SF and NY in *variable* font format, combining styles in one file and supporting interpolation between them. SF offers an unusually wide range of weights (Ultralight to Black) and several widths (including Condensed and Expanded). Because SF Symbols use matching weights, you can align symbols with adjacent text precisely at any size.

The system also defines *text styles* — preset combinations of weight, point size, and leading designed to compose into a typographic hierarchy. *Body* is tuned for comfortable multi-line reading; *headline* sets weight and size to distinguish a heading from its surroundings. Text styles also scale automatically when people change system text size or enable accessibility features such as Larger Text.

**Prefer the built-in text styles.** They give you a consistent way to express hierarchy through size and weight, and combined with system fonts they automatically support Dynamic Type and larger accessibility sizes.

**Modify text styles when necessary using symbolic traits.** Symbolic traits let you tweak aspects of a text style — for example, applying bold weight to introduce another level of hierarchy. You can also adjust leading: *loose leading* helps people track lines in long passages or wide columns, while *tight leading* helps text fit in tall-constrained areas like list rows. Avoid tight leading when you're displaying three or more lines.

**Adjust tracking in mockups when needed.** A running app dynamically adjusts tracking at every point size in variable system fonts. Mockups don't get this for free, so you may need to tune tracking by hand to match a real interface accurately.

## Using Custom Fonts

**Make sure custom fonts stay legible.** Test at typical viewing distances and conditions, and follow the recommended minimum sizes for each style and weight.

**Implement accessibility behaviors.** System fonts respond automatically to Dynamic Type and features such as Bold Text — custom fonts need to do the same explicitly. In Unity-based games, Apple's accessibility plug-in supports Dynamic Type; if it's not a fit, give players another way to adjust text size.

## Supporting Dynamic Type

Dynamic Type is a system feature on iOS, iPadOS, tvOS, visionOS, and watchOS that lets people choose a comfortable text size. Design accordingly:

**Make sure layouts adapt to every font size.** Verify that text and icons remain legible as sizes scale. Turn on Larger Accessibility Text Sizes on iPhone or iPad and confirm everything still reads comfortably.

**Scale meaningful interface icons with the font size.** When icons carry information, they should grow alongside text. SF Symbols handle this automatically.

**Minimize truncation as font size grows.** Aim to show roughly as much useful text at the largest accessibility size as at the largest standard size. Avoid truncating text in scrollable regions unless people can open a separate view to see the rest. Configure labels to use as many lines as needed.

**Adapt the layout at large font sizes.** In horizontally constrained contexts, inline glyphs, timestamps, and container edges can crowd text and force truncation. Stacking secondary items below the text and reducing the number of columns are both effective ways to keep things readable.

**Keep the information hierarchy consistent across font sizes.** Primary elements should stay near the top of the view even at very large sizes, so people don't lose track of them.
