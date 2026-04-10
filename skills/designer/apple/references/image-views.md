## Image Views

An image view displays a single image — or, in some cases, an animated sequence of images — on a transparent or opaque background.

Within an image view, the image can be stretched, scaled, sized to fit, or pinned to a specific location. Image views are typically not interactive.

## Best Practices

**Use an image view when the view's only job is to display an image.** If you need an image to be interactive, configure a system-provided button to show the image rather than wiring button behaviors into an image view.

**Prefer a symbol or interface icon over an image view for icon-sized art.** SF Symbols offers a large library of vector-based images that render in any color or opacity. An interface icon (sometimes called a glyph or template image) is typically a bitmap whose non-transparent pixels accept tinting. Both can pick up the user's chosen accent color.

## Content

An image view can hold rich image data in formats such as PNG, JPEG, and PDF.

**Be careful when overlaying text on an image.** Stacking text on imagery can hurt both the readability of the text and the clarity of the image. Make sure the text contrasts strongly with the image, and consider giving the text its own shadow or background to help it stand out.

**Use a consistent size for every frame of an animated sequence.** When images are pre-scaled to fit the view, the system avoids runtime scaling entirely. When scaling is unavoidable, performance is best if every frame shares the same size and shape.
