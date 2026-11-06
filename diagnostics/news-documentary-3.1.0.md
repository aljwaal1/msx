# Television 3.1.0 — news repair and documentaries

Date: 2026-11-06

## News
- Replaced expired YouTube live sessions for Al Jazeera Mubasher and France 24 Arabic/English.
- Arabic Al Jazeera streams now use the current URLs exposed by https://www.aljazeera.net/video/live.
- Added Al Jazeera Now separately from Al Jazeera News and Al Jazeera Mubasher, with its own AJA2 stream.
- Default HD playback is 720p; a visible 540p native television playback card remains available for Al Jazeera News.
- Al Jazeera 360 opens seven selected programmes from its official YouTube channel, not the external website or the full platform catalogue.

## Documentaries
- Added a documentary tile and sidebar entry, with ten home tiles on one screen.
- Eleven documentary choices: Al Jazeera Documentary live via its current official YouTube embed, Asharq Documentary, Asharq Discovery, and eight official programme libraries.
- Libraries: Nat Geo Abu Dhabi, Al Jazeera Documentary, DW Arabic, DW English, BBC Earth, ARTE, Free Documentary, and Timeline.
- Seventy-six films in these eight libraries; promotional clips under three minutes and failed/unconfirmed embeds were removed.
- Real Wild was excluded because all tested embeds were rejected.
- Nat Geo is explicitly a programme library; no unverified live stream is advertised.
- Libraries are curated snapshots, not a promise of automatic updates.

## Sources
- Al Jazeera: https://www.aljazeera.net/video/live
- Asharq: https://now.asharq.com/
- National Geographic: https://www.natgeotv.com/ae and https://www.youtube.com/@natgeoabudhabime
- AJ360: https://www.youtube.com/@aljazeera360
- Other libraries use their publishers' official public YouTube video pages and embedded players.

## Verification
- Configuration parses; IDs are unique; all page geometry stays within the native 12x6 grid; explicit page-focus targets and repository content targets resolve.
- Current fresh HTTP checks returned valid playlists and MPEG-TS segments for Al Jazeera News, Al Jazeera Now, Al Jazeera Mubasher, Asharq Documentary and Asharq Discovery.
- Earlier web MSX playback tests showed advancing video and readyState 4: Al Jazeera News 720p; Now 720p; Mubasher 480p; native News 540p; Asharq Documentary and Discovery 720p. France 24 Arabic replacement also played at 720p.
- News/documentary page controls and the four-column home layout were visually checked before publication.
- YouTube embed metadata checks were used to filter the libraries. All seven AJ360 programmes passed a fresh metadata/author check.

## Limits
- Physical G-Guard television playback has not been tested by the assistant.
- YouTube metadata/embed availability does not prove playback on the television. The documentary YouTube live player and programme embeds exposed valid titles/metadata but sustained video playback could not be confirmed in the cloud test.
- The final additional browser test of France 24 English was blocked by the browser usage/approval limit. Its public HLS playlist/segment was checked, but no claim of a completed visual playback test is made.
