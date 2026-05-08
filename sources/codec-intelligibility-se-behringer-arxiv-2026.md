---
title: "Assessing the Impact of Noise and Speech Enhancement on the Intelligibility of Speech Codecs"
authors: [Lyonel Behringer, Anna Leschanowsky, Anjana Rajasekhar, Emily Kratsch, Guillaume Fuchs]
date: 2026-05-05
arxiv_id: "2605.03776"
url: https://arxiv.org/abs/2605.03776
venue: Submitted to Interspeech 2026
type: research-paper
tags: [speech-codecs, speech-enhancement, intelligibility, listening-effort, neural-codecs, classical-codecs, asr-metrics, hearing-streaming]
---

# Codec Intelligibility under Noise and Speech Enhancement (Behringer et al., 2026)

## Key Extraction

- **Question:** How do classical (e.g., LC3, EVS) vs. neural (learned) speech codecs perform on intelligibility and listening effort under noisy conditions, and how does speech-enhancement preprocessing change that picture?
- **Method:** Subjective intelligibility + listening-effort tests across clean and noisy conditions, with and without an SE front-end. Cross-checked with ASR-based objective intelligibility metrics.

## Headline Findings

1. **Classical codecs were more noise-robust than neural codecs.** A useful counter to "newer = better" assumptions in the codec discourse.
2. **Speech enhancement preprocessing significantly improved both intelligibility and listening effort** for codecs that otherwise degraded in noise — i.e., SE is a real lever for codec deployment, not just a "nice to have" upstream stage.
3. **Listening effort revealed differences when intelligibility plateaued** — the field is increasingly using effort as a sensitivity-floor metric where word-recognition saturates.
4. **ASR-based objective intelligibility correlated strongly with subjective scores** when averaged per condition — usable proxy for large-scale evaluation.

## Relevance to Hearing + AI

- **Streaming pipelines for hearing aids** routinely involve a codec (LC3 / LC3plus over Auracast, AAC over classic Bluetooth, proprietary CIs). This paper is directly applicable to hearing-aid streaming chains where audio is encoded → transmitted → rendered to a hearing-impaired listener.
- **Counter-intuitive policy implication:** Adopting a neural codec just because it advertises higher MOS may regress intelligibility for hearing-impaired listeners under realistic noise. Codec selection for hearing devices should be co-evaluated with the SE stage, not in isolation.
- **Listening-effort focus** aligns with where modern hearing-aid evaluation is moving (cognitive load, dual-task paradigms) rather than pure word-recognition scores.

## Open Questions / Follow-up

- Were any of the tested codecs the LC3plus profile actually deployed in current Auracast hearing devices?
- Would jointly optimizing SE + codec end-to-end (rather than cascading) outperform either alone for hearing-impaired listeners?
- How does the result generalize beyond average listeners to audiogram-conditioned models?
