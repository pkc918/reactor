## Dark Mode

Dark Mode is a systemwide appearance setting that uses a dark color palette to provide a comfortable viewing experience tailored for low-light environments.

On iOS, iPadOS, macOS, and tvOS, many people set Dark Mode as their default and expect every app and game to honor that choice. In Dark Mode the system applies a dark palette to all screens, views, menus, and controls, and may increase perceptual contrast so foreground content remains prominent against darker backgrounds.

## Best Practices

**Don't add an app-specific appearance toggle.** Forcing people to manage a separate setting fragments the experience and can make your app appear broken when it doesn't follow the systemwide choice.

**Make sure your app looks good in both appearances.** People may also choose Auto, which switches between light and dark as conditions change throughout the day — possibly while your app is running.

**Verify legibility in both modes.** Test with Increase Contrast and Reduce Transparency turned on, separately and together. Watch for places where dark text becomes hard to read against a dark background — even users with strong vision may struggle with low-contrast pairings.

**Use a permanently dark appearance only in rare cases.** A dark-only interface can be appropriate for immersive media experiences, where letting the UI recede helps people focus on the content.

## Dark Mode Colors

The Dark Mode palette pairs dimmer backgrounds with brighter foregrounds. These colors aren't simply inversions of their light counterparts — many are inverted, but some are not.

**Use colors that adapt to the current appearance.** Semantic system colors automatically respond to appearance changes. For custom colors, add a Color Set to your asset catalog in Xcode and provide both bright and dim variants. Avoid hard-coded values or non-adaptive colors.

**Aim for sufficient contrast in every appearance.** System colors generally produce healthy contrast ratios. Keep text-to-background contrast at 4.5:1 or higher; for custom colors — especially with small text — aim for 7:1 to meet accessibility guidance.

**Tone down white image backgrounds.** Slightly darken images that have white backgrounds so they don't glow against the surrounding Dark Mode interface.

### Icons and Images

The system relies on SF Symbols (which adapt automatically) and full-color imagery optimized for both appearances.

**Prefer SF Symbols.** Symbols look good in both modes when tinted with dynamic colors or used with vibrancy.

**Provide separate light and dark interface icons when needed.** A full-moon icon may need a subtle dark outline against a light background but no outline against a dark one; an oil-drop icon may need a thin border to stay visible on dark surfaces.

**Make sure full-color images and icons work in both appearances.** Reuse a single asset when it looks good both ways; otherwise, supply distinct light and dark variants and combine them in an asset catalog under one name.

### Text

The system uses vibrancy and increased contrast to keep text legible on darker backgrounds.

**Use system-provided label colors.** Primary, secondary, tertiary, and quaternary label colors all adapt to the current appearance automatically.

**Use system views for text fields and text views.** System controls render text well across backgrounds, adjusting for vibrancy as needed. Prefer them over drawing text yourself.
