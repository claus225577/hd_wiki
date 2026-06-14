---
title: "Speech enhancement techniques for hearing aids: a systematic review"
type: source
source_type: peer-reviewed-review
date_published: 2026-04
date_ingested: 2026-06-14
authors: [P. D. Tetteh, R. M. O. Mensah Gyening, J. Arthur]
identifier: 10.1007/s10209-026-01342-7
url: https://link.springer.com/article/10.1007/s10209-026-01342-7
venue: Universal Access in the Information Society (Springer)
tags: [speech-enhancement, hearing-aids, systematic-review, deep-learning, hybrid-models, signal-processing]
---

# Speech Enhancement Techniques for Hearing Aids: A Systematic Review

## Bibliographic
- **Authors:** Tetteh, P. D.; Mensah Gyening, R. M. O.; Arthur, J.
- **DOI:** 10.1007/s10209-026-01342-7
- **Venue:** Universal Access in the Information Society, Springer (Apr 2026)
- **URL:** https://link.springer.com/article/10.1007/s10209-026-01342-7

## Scope
Systematic review of AI-driven speech enhancement techniques designed for hearing aids, covering the literature window 2017–2025. Studies are categorised into three groups:
1. Traditional signal processing methods (Wiener filtering, spectral subtraction, classical beamforming, statistical denoising).
2. Deep learning-based approaches (CRNs, U-Nets, conv-TasNet/SuDoRM-RF derivatives, transformer-based SE, generative SE).
3. Hybrid models integrating AI with adaptive filtering or contextual / noise-aware control.

## Headline Finding
Deep learning techniques consistently outperform classical methods in complex acoustic scenarios (multi-talker babble, low SNR, reverberant rooms). Hybrid approaches close the latency / power gap for embedded deployment without giving up most of the perceptual gain.

## Why It Matters
- Single most-recent (2026) literature anchor we can cite when arguing for DNN-based SE pipelines in hearing-aid contexts.
- Anchors the "DL > classical, hybrid sits in between" trichotomy that the broader Hearing-AI-Wiki uses as a default frame for SE evaluation.
- Useful counterpoint to the engineering-only literature on SuDoRM-RF++ FPGA (`fpga-sudormrf-feasibility-radboud-june-2026.md`) and the DAL personalization frame (`dal-differentiable-auditory-loop-google-june-2026.md`): the review confirms the field-wide pattern that those single studies embody.

## Open Questions / Limitations
- Review window stops at 2025, so the 2026 wave of generative SE (e.g. AIDA-2, GMAPSE, SBRF) and on-FPGA work isn't covered.
- Hybrid-class taxonomy is loose — the boundary between "contextual" classical and "lightweight DL" is unstable.

## Used In
- [[wiki/concepts/speech-enhancement-neural-networks.md]]
- [[wiki/concepts/dnn-in-hearing-aids.md]]
- [[wiki/concepts/dnn-architectures-hearing-aids.md]]
