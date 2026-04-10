## Materials

A material is a visual effect that creates a sense of depth, layering, and hierarchy between foreground and background elements.

Materials separate foreground elements (text, controls) from background elements (content, solid colors). By letting color from behind bleed through to the front, a material reinforces hierarchy and helps people stay oriented. Apple platforms ship two kinds: **Liquid Glass**, a dynamic material that unifies the design language across platforms and lets controls and navigation float above content without hiding it; and **standard materials**, which create visual structure within the content layer itself.

## Liquid Glass

Liquid Glass forms a distinct functional layer for controls and navigation — tab bars, sidebars, and the like — that floats above the content layer. The result is a clear separation between functional elements and content, with content scrolling and peeking through from below to give the interface a sense of depth and motion while keeping controls legible.

**Don't apply Liquid Glass in the content layer.** Mixing it into content blurs the hierarchy and adds unnecessary complexity. Use standard materials for content-layer elements such as app backgrounds. The exception is a transient interactive element inside content (such as text selection handles) that briefly takes on a Liquid Glass appearance to emphasize interactivity.

**Use Liquid Glass effects sparingly.** System components from system frameworks pick up the material automatically. When you apply it to a custom control, restrain yourself: overuse distracts from the underlying content the material is meant to highlight. Reserve it for the most important functional elements.

**Only use the clear Liquid Glass variant over visually rich backgrounds.** Liquid Glass has two variants — **regular** and **clear** — and their appearance can shift in response to user display preferences and accessibility settings such as Reduce Transparency or Increase Contrast.

- **Regular** blurs and tunes the luminosity of background content to keep foreground text and elements legible. Scroll-edge effects further blur and reduce opacity at the edges of scrolling content. Most system components use this variant. Choose it when the background could otherwise hurt legibility, or when the component holds significant text — alerts, sidebars, popovers.
- **Clear** is highly translucent. Use it when you want media (photos, video) to remain prominent behind floating components, for a more immersive feel.

For optimal contrast and legibility with clear Liquid Glass, decide whether to add a dimming layer:

- Over bright underlying content, consider a dark dimming layer at about 35% opacity.
- Over sufficiently dark content — or with standard AVKit media playback controls that already supply their own dimming — no extra dimming is needed.

## Standard Materials

Use standard materials and effects (blur, vibrancy, and related techniques) to give the content layer beneath Liquid Glass a sense of structure.

**Choose materials and effects by semantic meaning, not by their apparent color.** System settings can change a material's appearance and behavior, so pick the one whose intended purpose matches your use case.

**Use vibrant colors on top of materials to keep content legible.** System-defined vibrant colors stay readable across contexts without becoming too dark, bright, saturated, or low-contrast. Use them whenever you place text or icons on a material.

**Weigh contrast against visual separation when combining materials with blur and vibrancy.**

- Thicker, more opaque materials provide better contrast for text and fine details.
- Thinner, more translucent materials preserve context by keeping the underlying content visible.
