---
title: "Balancing ASR and Diarization in End-to-End LLMs for Multi-Talker Speech Recognition"
type: source
source_type: arxiv-paper
arxiv_id: 2606.13095
authors: [Naijun Zheng, Yuke Lin, Sanli Tian, Mengtian Li, Zhiwei Lin, Longshuai Xiao, Dandan Tu]
affiliations: [Huawei]
date_published: 2026-06-11
ingested: 2026-06-15
url: https://arxiv.org/abs/2606.13095
tags: [multi-talker-asr, diarization, llm-asr, speaker-attribution, alimeeting, aishell4, who-said-what, overlapping-speech, hearing-aid-asr]
---

# LLM-based Joint ASR + Diarization (Zheng et al., Huawei, June 2026)

## Bibliographic
- **Authors:** Naijun Zheng, Yuke Lin, Sanli Tian, Mengtian Li, Zhiwei Lin, Longshuai Xiao, Dandan Tu
- **Affiliation:** Huawei
- **Posted:** 11 June 2026 (arXiv:2606.13095)
- **URL:** https://arxiv.org/abs/2606.13095

## Problem
Multi-talker ASR is the "who said what" problem: not just transcribing speech in a multi-party scene, but attributing each utterance to the correct speaker through overlapping segments. Existing pipelines split ASR and diarization as cascaded stages, which loses information at the seam.

## Contribution
End-to-end LLM with four design choices:
1. **Two encoders.** Separate semantic and speaker-feature encoders feed the LLM rather than one shared trunk.
2. **Interleaved token format.** Semantic and speaker tokens are interleaved in the input sequence so the LLM can attend to both per-token.
3. **Speaker-attribution loss.** A specialized loss term encourages correct speaker labeling rather than just sequence-level WER.
4. **Adaptive overlap threshold.** A learned threshold mechanism to handle overlapping-speech segments — historically the hardest part of multi-talker ASR.

## Key Results
- 18% relative WER improvement on **AliMeeting**.
- 24% relative improvement on **AISHELL-4**.
- Both vs the strongest open-source multi-talker baselines.

## Why It Matters for Hearing Aids
- Hearing-aid wearers spend most of their listening time in multi-talker scenes (restaurants, family dinners, group meetings). Speaker-attributed transcription is the substrate for any downstream "show me what was said by whom" UX — Apple's WWDC 2026 generated subtitles feature is the first consumer-grade hint of this direction.
- Diarization is also the upstream signal for selective enhancement: "enhance the speaker the user is looking at / attending to" requires knowing where speaker boundaries are.
- LLM-on-companion-phone is the natural architecture (compute does not fit in the aid). The phone-side speech pipeline thread (see `companion-phone-speech-pipeline`) is where this lands.

## Open Questions
- Streaming latency — paper benchmarks are offline; multi-talker LLMs in production need to run with sub-second turn-by-turn latency.
- Model size and on-device feasibility — 7B+ LLM on a phone is plausible (Apple Intelligence, Gemini Nano) but the speaker-encoder side adds budget.
- Generalization to non-Mandarin benchmarks — AliMeeting and AISHELL-4 are Mandarin; the speaker-attribution loss may interact with language.

## Related Wiki Pages
- [[../wiki/concepts/companion-phone-speech-pipeline.md]] — phone-side compute substrate
- [[../wiki/concepts/multi-talker-asr.md]]
- [[../wiki/concepts/speaker-diarization.md]]
- [[../wiki/concepts/llm-speech-recognition.md]]
- [[../wiki/concepts/foundation-model-fusion-speech.md]]
