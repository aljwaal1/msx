# Playback repair 3.1.1

Date: 2026-11-07

## Reported faults and findings
- The BBC Learning English entry depended on an external merged MRSS feed. A fresh request returned zero video entries and a service warning.
- The old beIN live ID was no longer the current broadcast. The official channel's live page now identifies ekMxMIexsJ8, with live and playable-in-embed metadata. Crucially, the actual embedded player rejects playback on MSX with a publisher restriction. Metadata alone was insufficient.
- The first three Al Jazeera cards used the HLS JavaScript plugin, while a separate native-player Al Jazeera card already existed. The G-Guard user reported two-second playback followed by freezing/disconnection with the first three.
- Roya TV's general live-stream ticket endpoint was not accessible from the test environment. No guessed CDN URL, signed ticket, credential, or unauthorized restream is included. The verified official Roya News YouTube live broadcast is added, labelled specifically as Roya News.

## Changes
- First three Arabic Al Jazeera cards now use native video:HLS playback by default, at 540p for News and 480p for Now/Mubasher. Native 720p/1080p and an HLS 720p alternate remain in per-channel options.
- Disabled live resume-position restoration; an end-of-media trigger restarts the same broadcast instead of advancing to another channel. This is not a stall/network watchdog.
- Replaced the BBC feed entry in both learning and latest sections with a native 12-lesson MSX library. It is a curated snapshot, not an automatic feed.
- beIN opens a clear official-viewing/instructions page; it does not claim to play a publisher-blocked stream inside MSX. View through the television's YouTube application.
- Added Roya News (A1cZxijueg4) to the first news page. The publisher live metadata confirmed the official Roya News author, active broadcast and permitted embedding.
- Version 3.1.1 in menu/start/help.

## Verification
- All edited JSON parses; item IDs are unique; page geometry fits 12x6; explicit focus targets resolve.
- Each of the three native source URLs decoded 25 seconds of video using FFmpeg with exit 0 and no reported decode errors.
- Actual MSX web native playback: News advanced beyond 32 seconds, Now beyond 57 seconds and Mubasher beyond 37 seconds, all readyState 4 and no HTML media error.
- All twelve BBC video IDs passed publisher-author and oEmbed availability checks. Native BBC page one/page two and next-page navigation loaded without Media Not Found.
- Actual beIN embedded playback reproduced the publisher's external-site/application prohibition, so the candidate embedded fix was discarded.
- Roya News loaded its current official live-player title without the expired-video error.

## Limits
Physical G-Guard television playback is not available for testing here. The native-player change is a compatibility fix supported by web tests, not a promise that every television decoder/network will sustain it. BBC/Roya YouTube metadata and UI availability are verified, but sustained video playback on the user's television still requires a device test.
