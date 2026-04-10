## Color

Judicious use of color can enhance communication, evoke a brand, provide visual continuity, communicate status and feedback, and help people understand information.

The system defines colors that look good across backgrounds and appearance modes and that adapt automatically to vibrancy and accessibility settings — using them is the easiest way to feel native on the device. Custom colors can still be useful for expressing personality, and the guidance below applies to both system and custom palettes.

## Best Practices

**Don't use the same color to mean different things.** Apply color consistently, especially when it carries meaning such as status or interactivity. Reusing an interactive accent color for static text is confusing.

**Make sure your colors work in light, dark, and increased-contrast contexts.** Prefer system colors, which already define variants for each appearance. For custom colors, supply both light and dark variants and a high-contrast version of each. Provide both light and dark colors even if your app ships in a single appearance, to support Liquid Glass adaptivity.

**Test under varied lighting conditions.** Colors look darker and more muted in bright surroundings and brighter and more saturated in dim ones. In visionOS, surrounding physical objects can also influence how colors are perceived.

**Test on different devices.** True Tone displays on iPhone, iPad, and Mac shift the white point to match ambient lighting. Test tvOS apps on multiple HD and 4K TVs with different display settings. On macOS, switch color profiles (e.g., P3 vs. sRGB) in System Settings to preview how content looks in each.

**Account for how artwork and translucency affect nearby colors.** Background art may warrant adjustments to adjacent colors, and translucent surfaces (like toolbars) can shift the appearance of underlying content.

**Prefer system-provided color controls when letting people pick colors.** Built-in pickers feel consistent and let people share saved color sets across apps.

## Inclusive Color

**Don't rely on color alone to convey meaning.** Reinforce color cues with text labels, glyph shapes, or other indicators so people with color blindness or low vision can still understand the interface.

**Avoid color combinations that hurt perception.** Insufficient contrast makes text and icons blend into the background, and certain pairings are indistinguishable to people with color blindness.

**Consider cultural perceptions of color.** A color may carry very different connotations across cultures (for example, red signals danger in some contexts and good fortune in others). Make sure your palette communicates the meaning you intend.

## System Colors

**Don't hard-code system color values.** Documented values are reference only and may change between releases. Apply system colors through APIs instead.

iOS, iPadOS, macOS, and visionOS define *dynamic system colors* that match standard UI components and adapt to light and dark contexts automatically. These colors are defined semantically by purpose (background levels, foreground content like labels, links, and separators) rather than by appearance.

**Don't redefine the semantic meaning of dynamic system colors.** Use each color as intended — for example, don't repurpose a separator color as a text color, or a label color as a background — so your interface stays consistent when the platform's appearance changes.

## Liquid Glass Color

By default, Liquid Glass has no inherent color and inherits the colors of the content directly behind it. You can apply color to some Liquid Glass elements to give them a stained-glass appearance, which is useful for emphasizing a primary call to action — this is how the system styles prominent buttons. Symbols and text labels on Liquid Glass can also take color.

For smaller elements such as toolbars and tab bars, the system adapts Liquid Glass between a light and dark appearance based on the underlying content. By default, symbols and text on these surfaces use a monochromatic scheme — darker over light backgrounds and lighter over dark ones. Larger elements like sidebars use a more opaque Liquid Glass to maintain legibility over complex backgrounds.

**Apply color sparingly to Liquid Glass and to symbols or text on it.** Reserve color for elements that genuinely benefit from emphasis, such as status indicators or primary actions. To emphasize a primary action, color the background rather than the symbol or text — as the system does with prominent buttons like Done. Don't add color to multiple control backgrounds.

**Avoid similar colors in control labels when the app has a colorful background.** Too much color makes labels harder to read. Over rich or colorful content, prefer a monochromatic toolbar and tab bar appearance, or pick an accent color with strong visual differentiation. Over largely monochromatic content, a brand color can be an effective accent.

**Mind where color sits in the content layer.** Maintain sufficient contrast by avoiding overlap between similarly colored content and controls. Even if colorful content scrolls beneath controls intermittently, the resting state — such as the top of a scrolling view — should remain clearly legible.

## Color Management

A *color space* represents the colors in a *color model* like RGB or CMYK. Common color spaces (sometimes called *gamuts*) include sRGB and Display P3. A *color profile* describes the colors in a color space, often via mathematical formulas or lookup tables. Images embed a profile so devices can interpret and reproduce their colors correctly.

**Apply color profiles to your images.** Color profiles help your app's colors appear as intended across displays. sRGB produces accurate results on most screens.

**Use wide color to enrich the visual experience on compatible displays.** Wide color displays support the P3 color space, producing richer, more saturated colors than sRGB. Photos, videos, and visual indicators that use wide color feel more lifelike. When appropriate, use the Display P3 profile at 16 bits per channel and export images as PNG. You need a wide color display to design for wide color.

**Provide color-space–specific image and color variants when needed.** P3 colors and images generally render fine on sRGB displays, but very similar P3 colors can become indistinguishable on sRGB, and P3 gradients can occasionally clip. Use Xcode asset catalogs to ship separate variants for each color space when necessary.
