## Motion

Beautiful, fluid motion brings the interface to life — conveying status, giving feedback and instruction, and enriching the visual experience of an app or game.

Many system components animate automatically, so adopting them gives you consistent, familiar behavior for free. System-level motion can also adapt to accessibility settings and input methods — widgets react with more tactile emphasis to direct touch, for instance, and more subtly to a trackpad. The guidance below applies when you design custom motion.

## Best Practices

**Use motion with a purpose.** Animation should support the experience, not steal the spotlight. Gratuitous or excessive motion distracts people and can even cause physical discomfort.

**Treat motion as optional.** Some people can't or don't want to experience animation, so never rely on it as the sole way to communicate something important. Pair visual cues with alternatives — sound, haptics, text — so everyone can follow along.

## Providing Feedback

**Make feedback motion realistic and aligned with people's gestures.** In non-game apps, accurate motion reinforces how the interface works; incongruous feedback is disorienting. If someone pulls a view down from the top to reveal it, they'll expect to push it back up to dismiss it — not swipe it away sideways.

**Keep feedback animations brief and precise.** Short, tightly scoped animation feels lightweight and often communicates more effectively than something showy. A crisp hit effect in a game registers instantly without pulling players out of the action; when someone taps a panorama in visionOS Photos, it expands smoothly into place so the transition reads without delay.

**Avoid adding motion to frequent UI interactions.** Standard system components already animate subtly. Layering extra custom motion onto something people do dozens of times forces them to sit through it over and over.

**Let people cancel motion.** Don't force people to wait out an animation before they can act — especially when they'll encounter it repeatedly.

**Consider animated symbols where it fits.** SF Symbols 5 and later support animations for both system and custom symbols, which can be a lightweight way to add motion where it reinforces meaning.

## Leveraging Platform Capabilities

**Ship great default motion on every platform you support.** Most games feel smooth at a steady 30–60 fps; use each device's graphics capabilities so the defaults are good enough that people don't need to tweak anything to enjoy the experience.

**Let players customize the visual experience.** Expose settings that trade fidelity for performance or battery life — for example, a power mode toggle the system can switch on when external power is connected.
