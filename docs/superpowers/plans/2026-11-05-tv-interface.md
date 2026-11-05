# Modern television interface implementation plan

Goal: Implement the approved interface review for تلفزيون خصوصي in native Media Station X.

Architecture: Keep the existing JSON launcher, playback sources and official links. Use explicit native pages, a small repeated navigation bar, and lightweight code-native SVG artwork exported to PNG for older television browsers.

## Constraints
- Keep all nine sections and existing playback actions, including automatic Jordan quality and the light Al Jazeera fallback.
- Light gray content surface with navy header/footer for legible native white indicators.
- News, sports and children lead the home grid. Keep navigation flat and remote-friendly.
- No Android APIs, additional device, new account or runtime web framework.

## Tasks
- [ ] Build consistent artwork without baked-in episode titles.
- [ ] Replace oversized return cards with compact home/page controls; show readable page numbers.
- [ ] Open the home grid directly and return to the launching category using documented focus separators.
- [ ] Simplify help labels and preserve every help action and quality option.
- [ ] Validate content/action preservation and page geometry, then test startup, every section, next/previous, home focus restoration and playback in the web MSX runtime.
- [ ] Publish atomically against the recorded GitHub head after verification.

## Review focus
- Returning from a late category must select that category rather than the first tile.
- Small sections must not be dominated by a return tile.
- News page two must be reachable with an explicit visible button.
- Arabic titles must occur once and remain clear over every image.
- Visual work must not alter or remove playback URLs.

## Rulings
- Use isolated Git objects and a preview branch instead of editing main during construction.
- Use real browser interaction plus structural/action checks, rather than tests mirroring cosmetic JSON values.
- Keep MBC removed and keep Al Jazeera 360 labelled as a platform that opens externally.
