---
title: "Microsoft Edge 148 Ships On-Device Web Speech API + Translator/Language Detector APIs (Build 2026)"
type: source
source_type: industry-news
date_published: 2026-06-02
date_ingested: 2026-06-10
authors: [Microsoft Edge Team]
identifier: msedge-148-on-device-ai
url: https://blogs.windows.com/msedgedev/2026/06/02/expanding-on-device-ai-in-microsoft-edge-new-models-and-apis-for-the-web/
venue: Microsoft Build 2026 / Microsoft Edge Blog
tags: [on-device-ai, browser, web-speech-api, asr, teleaudiology, edge-ai, privacy, low-latency]
---

# Microsoft Edge 148 — On-Device Web Speech API and Translator APIs

## Bibliographic
- **Announced:** 2 June 2026 at Microsoft Build 2026
- **Edge version:** 148 (stable / behind flag, depending on API)
- **URL:** https://blogs.windows.com/msedgedev/2026/06/02/expanding-on-device-ai-in-microsoft-edge-new-models-and-apis-for-the-web/

## What
Microsoft Edge 148 ships three notable browser-side on-device AI capabilities:
1. **Experimental on-device Web Speech API** — automatic speech recognition runs on a local model rather than sending audio to the cloud, with improved privacy, lower latency, and offline operation.
2. **On-device Translator API** — task-specific local translation model.
3. **On-device Language Detector API** — local language identification.

All three are exposed via standard Web APIs callable from any web app.

## Why It Matters for Hearing AI
The teleaudiology and remote-fitting pipeline has historically been bottlenecked at speech I/O — cloud ASR adds 200–800 ms latency and triggers HIPAA/GDPR review for any clinic that wants to capture spoken patient responses. On-device browser ASR collapses both problems:

- **Teleaudiology web portals** (remote fitting, fitting verification, follow-up questionnaires) can transcribe patient responses without a cloud round-trip, removing the most cited regulatory blocker.
- **Real-time captioning in browser-based hearing-aid companion apps** becomes viable on stock hardware — no extra Whisper.cpp build or WASM acrobatics.
- **Multilingual hearing care** in LMIC settings benefits doubly: language detection + translation + speech-to-text all run locally on whatever device the patient brought.

The trend signal is more important than the specific API: browser vendors are normalizing on-device ASR as a baseline web capability. Within ~18 months, "send audio to a cloud STT endpoint" becomes the unusual choice for new hearing-health web apps, not the default.

## Open Questions
- Word-error rate on accented and elderly speech (the bulk of the hearing-care patient population) not characterized in the announcement.
- Model size and memory footprint not disclosed — relevant for older laptops common in audiology clinics.
- Permission model for `getUserMedia` + on-device speech needs UX work before clinical deployment.

## Used In
- [[wiki/concepts/teleaudiology.md]]
- [[wiki/concepts/on-device-ml-hearing-aids.md]]
- [[wiki/concepts/medical-domain-edge-llms.md]]
- [[wiki/concepts/companion-phone-speech-pipeline.md]]
