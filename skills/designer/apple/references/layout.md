## Layout

A consistent layout that adapts across contexts feels approachable and helps people enjoy your apps and games on every device they use.

Layout grounds people the moment they open your app. Familiar relationships between controls and content make features discoverable and let your app feel native to the platform. Apple ships templates, guides, and other resources to help you target every Apple platform with a consistent foundation.

## Best Practices

**Group related items so people can find what they need.** Use negative space, background shapes, color, materials, or separator lines to signal relationships and divide information into clear regions — but keep content and controls visually distinct from one another.

**Give essential information enough room.** People want to see the most important content immediately, so don't let secondary details crowd it. Push less critical information to other parts of the window or to a separate view.

**Let content fill the screen or window.** Backgrounds and full-screen artwork should reach every edge of the display, and scrollable layouts should run all the way to the device edges. Because controls and chrome (sidebars, tab bars) float above content rather than sitting in-line with it, plan the layout with that overlap in mind. When content doesn't fill the full window, use a background extension view so the area beneath sidebars and inspectors looks intentional.

## Visual Hierarchy

**Distinguish controls from content.** Use Liquid Glass to give controls a consistent, recognizable appearance across iOS, iPadOS, and macOS, and rely on a scroll-edge effect — rather than a solid background — to mark the transition between content and controls.

**Place items to communicate importance.** People scan in reading order (top to bottom, leading to trailing), so put the most important elements toward the top and leading side. Reading order varies by language, so design with right-to-left layouts in mind too.

**Align components to make scanning easier.** Alignment makes the interface feel orderly, helps people track content as they scroll, and — combined with indentation — communicates hierarchy.

**Use progressive disclosure to hint at hidden content.** When a collection is too large to show at once, give people a cue that more is available. Depending on the platform, that might mean a page indicator, a partially revealed item, or an interactive affordance.

**Give controls breathing room and group them logically.** Crowding makes controls hard to distinguish and hurts usability; clear spacing and grouping make their purpose obvious.

## Adaptability

Every interface needs to handle changes in device and system context. iOS, iPadOS, tvOS, and visionOS expose a set of *traits* that describe these variations. SwiftUI and Auto Layout let your UI respond to traits and context changes automatically; without them, you need another mechanism.

Common variations to plan for:

- Different screen sizes, resolutions, and color spaces
- Portrait and landscape orientation
- System features such as Dynamic Island and camera controls
- External displays, Display Zoom, and resizable windows on iPad
- Dynamic Type text-size changes
- Locale-driven differences such as layout direction, formatting, font, and text length

**Adapt gracefully while remaining recognizably consistent.** People expect your interface to keep working — and feeling familiar — when they rotate the device, resize a window, attach a display, or move between devices. Respect system safe areas, margins, and guides, and use layout modifiers to fine-tune placement.

**Be ready for text-size changes.** Support Dynamic Type so the interface responds when people choose a different text size on iOS, iPadOS, tvOS, visionOS, and watchOS.

**Preview on multiple devices, orientations, locales, and text sizes.** Start by exercising the largest and smallest layouts to flush out problems quickly. Real devices are best for things like wide-gamut color, but Xcode Simulator is good for catching clipping and layout issues — for example, verifying that a landscape iOS app looks right rotated in either direction.

**Scale artwork — don't reshape it — when displays change.** If a different aspect ratio would crop, letterbox, or pillarbox your art, scale to keep important content visible rather than altering the aspect ratio. In visionOS, the system handles z-axis scaling for windows automatically.

## Guides and Safe Areas

A *layout guide* is a rectangular region you use to position, align, and space content. The system provides predefined guides for standard margins and for limiting text width to a comfortable reading measure, and you can define your own.

A *safe area* is the portion of a view not covered by toolbars, tab bars, or other window-level views. Safe areas are essential for steering content clear of interactive and display features such as Dynamic Island on iPhone or the camera housing on certain Macs.

**Respect each platform's display and system features.** Apps that ignore them feel out of place and can be harder to use. Beyond avoiding hardware features, safe areas also adjust as bars and other interactive components change size, repositioning your content automatically.
