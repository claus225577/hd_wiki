---
title: "Apple WWDC 2026 — Generated Subtitles (On-Device Speech Recognition) in iOS 27 / iPadOS 27 / macOS 27 / tvOS 27 / visionOS 27"
type: source
source_type: company-keynote
publisher: Apple
published: 2026-06-08
ingested: 2026-06-11
url: https://www.apple.com/newsroom/2026/06/apple-unveils-next-generation-of-apple-intelligence-siri-ai-and-more/
secondary_urls:
  - https://techcrunch.com/2026/06/09/wwdc-2026-everything-announced-on-siri-ai-os-27-apple-intelligence-and-more/
  - https://appleinsider.com/articles/26/06/08/tvos-27-sneaks-out-with-redesigned-podcasts-app-ai-subtitle-generation
  - https://www.macrumors.com/2026/06/09/ios-27-overhauled-airpods-settings-menu/
tags: [apple, wwdc-2026, ios-27, ipados-27, macos-27, tvos-27, visionos-27, generated-subtitles, on-device-asr, accessibility, deaf, hard-of-hearing, captions, visual-substitution]
---

# Apple WWDC 2026 — Generated Subtitles (On-Device Speech Recognition)

## Metadata
- **Announcement:** WWDC 2026 keynote, Monday June 8, 2026 (10:00 a.m. PT). Confirmed and shipped as part of the iOS 27 / iPadOS 27 / macOS 27 / tvOS 27 / visionOS 27 release wave (developer betas live now; public release in fall 2026 with iOS 27 GA).
- **Pre-announcement:** Apple Newsroom accessibility preview on 19 May 2026 (Global Accessibility Awareness Day) flagged the feature; WWDC keynote is the implementation confirmation.
- **Feature:** Generated Subtitles — auto-transcribes any uncaptioned video using on-device speech recognition; subtitle overlay appears automatically when source has no captions.
- **Devices:** iPhone, iPad, Mac, Apple TV, Apple Vision Pro (essentially every active-OS device class Apple ships).
- **Languages at launch:** English only, U.S. and Canada.
- **Privacy posture:** All speech recognition runs **on-device**. Audio never leaves the device; subtitles are generated locally.
- **Content scope:** Personal video clips, content received from friends/family, streamed video. Auto-activates when no captions are present in the source.
- **Customization:** Appearance configurable from video playback menu or Settings.

## Key Points

### What Apple actually shipped
- **On-device automatic speech recognition as an OS-level service for video accessibility.** Generated Subtitles is a first-party feature, not a developer add-on — it Just Works for any uncaptioned video the system plays.
- **Cross-device parity in one release.** All five active Apple OS lines get the feature simultaneously, including tvOS (the AppleInsider June 8 piece confirmed tvOS 27 also ships subtitle generation with the same on-device privacy framing).
- **Sits above MfI hearing aids and Hearing Aid Mode.** Generated Subtitles is a parallel accessibility layer, not a hearing-aid feature — it competes with audio-pathway enhancement by providing a visual-substitution layer.

### Co-shipping WWDC accessibility features (same release wave)
- **Name Recognition expanded to 50+ languages globally** (was English-only; see [[apple-pre-wwdc-accessibility-may-2026.md]]).
- **Made for iPhone (MfI) hearing aids:** reliable cross-device handoff across iOS / iPadOS / macOS / visionOS; unified setup experience.
- **AirPods 3-band Custom EQ in iOS 27** (covered separately, see [[apple-wwdc-2026-airpods-custom-eq-jun-2026.md]]).
- **Vision Pro:** eye-tracking-driven power wheelchair control; on-device live captions (same Generated Subtitles substrate, applied to Vision Pro media).
- **FaceTime Sign Language API:** developer API for adding human interpreters to live FaceTime calls.

### What's distinctly new about this vs. prior captioning approaches
- **Privacy.** On-device ASR for personal videos means family content / clips received from friends / personal recordings never leave the device — historically the privacy problem with live captioning was cloud STT. Apple is the first mainstream consumer OS to ship private auto-captions at scale.
- **Coverage.** Not just live calls (Live Captions has existed) — this works on any video file the OS plays. Personal videos, social-shared clips, streamed media without source captions all become accessible.
- **Default-on UX.** Subtitles appear automatically; the user doesn't have to opt-in per video.

### What WWDC 2026 did NOT include
- No non-English support at launch (English U.S./Canada only). Apple says expansion later.
- No multi-speaker diarization shown in the demo (single subtitle stream).
- No documented API for third-party apps to consume the Generated Subtitles output (vs. roll their own ASR) — would be a meaningful developer-ecosystem signal if/when added.
- No integration with Made for iPhone hearing aids beyond the standard audio routing — captions appear on screen, do not flow into the hearing aid as text or audio.

## Why This Matters for Hearing AI

### The visual-substitution layer just shipped at platform scale
- For 30 years, hearing-aid AI has competed on a single axis: **how well the audio gets cleaned** (speech enhancement, beamforming, noise reduction, DNN-based SE, generative SE). Visual substitution — captions — has historically been a niche / venue-installed / app-side concern (Live Captioning glasses, ZipCaption, AVA, Cardzilla, niche browser plugins).
- Generated Subtitles is the first time the visual substitution layer ships on **a billion+ active devices**, default-on, on-device, cross-OS, with first-party UX investment.

### Strategy stack now has two layers
- The hearing-impaired wearer used to have an audio-only strategy stack: hearing aid + optional remote mic + Auracast.
- Post-iOS 27, the strategy stack is **audio + visual substitution**: hearing aid + Generated Subtitles on whatever screen the wearer is looking at + Auracast in venues + Live Captions for calls.
- This raises an existential design question for hearing-aid AI roadmaps: if captions are universally available everywhere the wearer is looking, what does the audio enhancement need to deliver that text doesn't?

### Where audio still wins (no-screen scenarios)
- Conversations with no screen present (in-person, restaurant, hallway, walking outside).
- Music and music quality (captions are a poor substitute for restored musical content).
- Spatial / immersive listening (captions don't preserve direction or rhythm of natural conversation).
- Listening effort minimization for cognitive-load-sensitive populations (reading captions has its own cognitive cost).

### Where the visual layer compresses audio's value
- Personal video / family memories / streaming content — large fraction of wearer's media consumption.
- Lecture, training, work meetings (especially remote video) — captions and audio enhancement now compete for the same accessibility budget.
- Catch-all for novel audio (clips received from friends, social media auto-play) — historically the worst case for audio enhancement, now mitigated by on-screen text.

### Strategic implications for hearing-aid OEMs
- **The accessibility surface area Apple owns expands again.** Apple now owns: the hearing test (Hearing Test in Hearing Health), the OTC hearing aid (AirPods Pro 2/3 Hearing Aid Mode), the EQ (Custom EQ), the captions (Generated Subtitles), the semantic alerts (Name Recognition), and the device class (MfI lifecycle).
- **Audio cleaning needs to defend its budget.** OEM R&D investment in DNN-SE, generative SE, on-chip silicon, fitting software — all of these need a story about value-over-captions in scenarios where the wearer has a screen.
- **Captions + hearing aid as a hybrid product is unbuilt.** No OEM today has shipped a tightly-integrated "captions on phone, sound on hearing aid, both context-aware" product. The first OEM that does — and that uses caption-side telemetry (which words the wearer's eye lingered on) to refine audio-side personalization — owns a new data flywheel.

## Carry-Forward Flags
- **When does Generated Subtitles expand beyond English U.S./Canada?** Apple usually targets first international rollout 3-9 months post-launch.
- **Will Apple ship a Generated Subtitles API for third-party apps?** Would dramatically expand the accessible-content footprint.
- **Will any major hearing-aid OEM (Sonova, Demant, GN, WSA) ship a paired-companion "captions ↔ aid" integration in 2026-2027?**
- **Multi-speaker diarization.** Single-stream subtitles are a stepping stone; multi-speaker captions are the meaningful next step for the dinner-table use case where hearing aids fail hardest.
- **Latency benchmarks.** Apple has not disclosed end-to-end latency for Generated Subtitles. Sub-200ms is the conversational threshold; pre-recorded video latency is less critical.

## Related Wiki Pages
- [[../wiki/entities/apple-hearing-features.md]] — Primary entity page. Add Generated Subtitles to the WWDC 2026 section.
- [[../wiki/concepts/companion-phone-speech-pipeline.md]] — On-device ASR on phone is the same substrate that powers captioning; Generated Subtitles extends the companion-phone pipeline above the audio layer into the visual layer.
- [[../wiki/concepts/on-device-ml-hearing-aids.md]] — On-device speech recognition as a platform capability sets the baseline that hearing aids must compete against.
- Live Captioning Smart Glasses (May 2026) — adjacent visual-substitution category at the wearable form factor; see [[../sources/live-captioning-smart-glasses-may-2026.md]].
- Adobe / Speechmatics on-device STT (April 2026) — vendor side of the same on-device ASR commodification trend; see [[../sources/adobe-speechmatics-on-device-stt-april-2026.md]].
- Microsoft Edge 148 on-device Web Speech API (June 2026) — browser side of the same trend; see [[../sources/microsoft-edge-148-on-device-speech-api-june-2026.md]].
