---
title: Visual Substitution for Hearing Accessibility
type: concept
created: 2026-06-11
updated: 2026-06-11
sources: [apple-wwdc-2026-generated-subtitles-jun-2026.md, apple-wwdc-2026-name-recognition-mfi-confirmation-jun-2026.md, live-captioning-smart-glasses-may-2026.md, adobe-speechmatics-on-device-stt-april-2026.md, microsoft-edge-148-on-device-speech-api-june-2026.md]
related: [companion-phone-speech-pipeline.md, on-device-ml-hearing-aids.md, communication-accessibility-metric.md, auracast-bluetooth-le-audio.md, ../entities/apple-hearing-features.md]
tags: [accessibility, captions, subtitles, asr, on-device, visual-substitution, deaf, hard-of-hearing, hearing-aid-strategy]
---

# Visual Substitution for Hearing Accessibility

The set of accessibility approaches that **substitute visual text for auditory speech** rather than enhancing the audio pathway. Includes live captions, generated subtitles, smart-glasses caption overlays, FaceTime sign-language inserts, and ambient semantic alerts (e.g., name spotting → on-screen notification).

Historically a niche category — venue-installed CART, third-party apps (Ava, Cardzilla, Live Transcribe), or smart-glasses startups. As of **June 2026** it has crossed into mainstream consumer OS surface area at platform scale.

## Why This Matters

For 30 years, hearing-aid AI has competed on a single axis: **how well the audio gets cleaned** — beamforming, noise reduction, DNN-SE, generative SE. Visual substitution was treated as either (a) a complement for severe loss only, or (b) a venue-installed accommodation. Neither competed for the same budget as audio-pathway enhancement.

That assumption broke in 2026.

### June 2026 inflection
- **Apple WWDC 2026 (8 Jun)** shipped Generated Subtitles — on-device ASR auto-captioning any uncaptioned video — across iPhone, iPad, Mac, Apple TV, Vision Pro. Default-on. Private (no audio leaves device). English U.S./Canada at launch; expansion expected. See [[../../sources/apple-wwdc-2026-generated-subtitles-jun-2026.md]].
- **Apple Name Recognition** extended to 50+ languages on-device — ambient semantic alerting for HoH users. See [[../../sources/apple-wwdc-2026-name-recognition-mfi-confirmation-jun-2026.md]].
- **Microsoft Edge 148** (2 Jun) shipped experimental on-device Web Speech API — same on-device-ASR substrate, browser side. See [[../../sources/microsoft-edge-148-on-device-speech-api-june-2026.md]].
- **Live-captioning smart glasses** (Wired review, May 2026) named a clear category leader — see [[../../sources/live-captioning-smart-glasses-may-2026.md]].
- **Adobe + Speechmatics on-device STT** (April 2026) packaged for production deployment.

The common thread: on-device ASR is now commodity, available on the phone, browser, glasses, and OS-level apps. The visual-substitution layer for hearing accessibility just got a platform substrate.

## The Two-Layer Strategy Stack

A hearing-impaired wearer in 2024 had a one-axis strategy stack: hearing aid + optional remote mic + Auracast in venues.

A hearing-impaired wearer in late 2026 (after iOS 27 GA, Edge 148 on-device ASR rollout, smart-glasses caption maturation) has a two-axis strategy stack:

| Scenario | Audio path | Visual path |
|---|---|---|
| Watching personal video (phone/Mac/TV) | Hearing aid + media | Generated Subtitles |
| Streaming uncaptioned content | Hearing aid + media | Generated Subtitles |
| Video call / FaceTime | Hearing aid + call | Live Captions / FaceTime Sign Language |
| Browser-based teleaudiology session | Hearing aid + browser audio | Edge on-device ASR captions |
| Face-to-face conversation, screen present | Hearing aid in noise | Smart-glasses captions (where available) |
| Face-to-face conversation, no screen | Hearing aid + Auracast in venue | (no visual path) |
| Music | Hearing aid + content | (poor visual substitute) |
| Walking outside / sport | Hearing aid + environment | (no visual path) |
| Spatial awareness / safety alerts | Hearing aid + environment | (poor visual substitute) |

## Where Audio Still Wins
- **No-screen scenarios** (in-person without phone visible, restaurant, hallway, walking outdoors).
- **Music** (captions are a poor substitute for restored musical content).
- **Spatial / immersive listening** (captions don't preserve direction or rhythm).
- **Listening effort minimization** for cognitive-load-sensitive populations (reading captions has its own cognitive cost — see [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md]] and the broader Pichora-Fuller FUEL framework).
- **Safety / environmental awareness** (cars, sirens, alarms).

## Where Visual Substitution Compresses Audio's Value
- **Personal video / family memories / streaming content** — large fraction of wearer's media consumption.
- **Lecture, training, work meetings** (especially remote video).
- **Catch-all for novel audio** (clips received from friends, social media auto-play) — historically the worst case for audio enhancement.
- **Multilingual content** (captions + translation captions are easier than retraining audio enhancement per language).

## Strategic Implications for Hearing-Aid OEMs

### The audio-pathway budget has to defend itself
- OEM R&D investment in DNN-SE, generative SE, on-chip silicon, fitting software — all of these need a story about value-over-captions in scenarios where the wearer has a screen.
- Premium AI features (Phonak Sphere Infinio's DEEPSONIC chip, ReSound Vivia's DNN, Oticon Intent's 4D sensor fusion) need to articulate why their incremental improvement is worth the cost when the wearer can fall back to free OS captions for screen-mediated content.

### Hybrid product opportunity is unbuilt
- No OEM today has shipped a tightly-integrated "captions on phone, sound on hearing aid, both context-aware" product.
- The first OEM that does — and that uses caption-side telemetry (which words the wearer's eye lingered on, which captions the wearer scrolled back to reread) to refine audio-side personalization — owns a new data flywheel.
- Cross-references [[closed-loop-data-flywheel.md]] and [[continual-learning-hearing-ai.md]].

### Apple owns more of the accessibility surface area each release
- Apple now owns: the hearing test (Hearing Test in Hearing Health), the OTC hearing aid (AirPods Pro 2/3 Hearing Aid Mode), the EQ (Custom EQ), the captions (Generated Subtitles), the semantic alerts (Name Recognition), the device class (MfI lifecycle).
- Each of those started as an OEM-side feature; now lives at OS level.
- The pattern is consistent: any feature that's "useful for everyone, especially the hearing-impaired" ends up shipped at platform scale and becomes commodity plumbing for the OEM.

## Open Questions
- **Latency.** Sub-200ms end-to-end is the conversational threshold; Apple has not published Generated Subtitles latency. For non-live content, latency is less critical.
- **Multi-speaker diarization.** Single-stream captions are a stepping stone; multi-speaker, speaker-labeled captions are the meaningful next step for the dinner-table use case where hearing aids fail hardest.
- **Caption + hearing-aid co-personalization.** Does the wearer's caption-reading behavior get fed back into audio-side personalization? Unbuilt today.
- **Battery economics of caption-display devices.** Smart-glasses caption rendering is far more power-hungry than hearing-aid amplification; all-day wear feasibility is unclear.
- **Regulatory framing.** Section 508 / EAA / WCAG 2.2 trends increasingly recognize captions as a primary accommodation; this regulatory tailwind compounds the platform shift.

## Related Pages
- [[../entities/apple-hearing-features.md]] — Primary mover of the platform-scale substrate.
- [[companion-phone-speech-pipeline.md]] — The phone-side on-device ASR substrate that powers Generated Subtitles is the same one that powers caption-side speech enhancement.
- [[on-device-ml-hearing-aids.md]] — Sets the on-chip ceiling that defines what audio enhancement must deliver beyond captions.
- [[communication-accessibility-metric.md]] — The Pichora-Fuller / WCA framework for measuring accessibility outcomes is naturally multi-modal; visual-substitution evaluation belongs in the same metric stack.
- [[auracast-bluetooth-le-audio.md]] — The audio-pathway analog for venue-installed accessibility infrastructure.

## Sources
- [Apple WWDC 2026 — Generated Subtitles](../../sources/apple-wwdc-2026-generated-subtitles-jun-2026.md) — Platform-scale on-device ASR captioning, Jun 8 2026.
- [Apple WWDC 2026 — Name Recognition + MfI Handoff Confirmation](../../sources/apple-wwdc-2026-name-recognition-mfi-confirmation-jun-2026.md) — Semantic alerting in 50+ languages, Jun 8 2026.
- [Live-Captioning Smart Glasses Roundup — May 2026](../../sources/live-captioning-smart-glasses-may-2026.md) — Wearable visual-substitution form factor.
- [Microsoft Edge 148 On-Device Web Speech API](../../sources/microsoft-edge-148-on-device-speech-api-june-2026.md) — Browser-side on-device ASR.
- [Adobe + Speechmatics On-Device STT (April 2026)](../../sources/adobe-speechmatics-on-device-stt-april-2026.md) — Vendor-side commodification.
