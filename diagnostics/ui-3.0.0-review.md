# تلفزيون خصوصي — واجهة 3.0.0

## Changes
- Consistent lightweight PNG artwork, with editable SVG sources in assets/ui3/source.
- Native remote navigation; home grid opens directly, compact Home controls return to the launching category.
- Explicit news Next/Previous buttons and page count; media remains enumerated independently of navigation controls.
- Light background, navy headings, white card labels and native focus border.
- Smaller, clearer help and a separate channel availability page.
- Existing playback and quality options preserved; MBC remains absent. Al Jazeera 360 remains explicitly on-demand/external.

## Verification — 2026-11-05
- All 12 JSON documents parsed; page geometry in 12×6 bounds; item IDs unique.
- 49 video/audio/link actions match the previous sections, including nested quality options.
- Web MSX 0.1.167: startup enters the home grid; arrows change selection.
- All nine section screens and the new source-information screen loaded.
- News Next and Previous moved between both pages.
- Home returned from news and sports and selected the corresponding home tile.
- Jordan Sports played at 1920×1080 with readyState 4 and no HTML media error; Escape returned to its selected card.

## Limits
Testing used the web MSX runtime, not the physical G-Guard television. Native Back/red-key support depends on the television/runtime; the visible Home control is the tested route. No claim is made that every external stream plays on every device. Playback sources and retry behavior were not changed in this interface revision.
