# Changelog

## 1.0.1 — 2026-10-24

- Fixed false `SUS inject` flags caused by volume and media keys (for example `VK174`).
- Injected input is now checked only while the game window is in the foreground.
- Key-up events are no longer counted, so one injected key press is not treated as two events.
- A single injected event no longer raises a SUS flag; at least three events are required, with a repeated action or a longer burst.
- System keys (media, browser, PrintScreen, NumLock, ScrollLock, Sleep) are ignored by the input check.

## 1.0.0 — 2026-10-23

Initial public release.

- Automatic run timer, splits, PB comparison and results screen.
- Seed control: set, randomise, save and mark seeds as Extras.
- Version-aware spawn points for Granny and Grandpa.
- Native game crosshair tint plus custom cross/circle crosshair.
- Custom death sound (WAV, MP3, OGG, AIFF) with Test button and cooldown.
- Playhouse and wire/chain splits for game versions 1.0–1.8+.
- Local anti-cheat: synthetic input, autoclickers, macros, time-scale changes, pickup distance and hand reach.
- Debug overlay log filter: show all logs or anti-cheat warnings only.
- Post-processing toggles, FPS limiter, experimental 5–15 FPS mode and keystrokes overlay.
- Quality-of-life options: skip wake-up cutscene, mouse side-button swap, quick restart, go-to-menu bind and copy results.
- Russian, English and Portuguese UI.
