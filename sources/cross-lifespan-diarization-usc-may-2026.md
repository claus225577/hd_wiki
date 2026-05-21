---
title: "Exploring Speech Foundation Models for Speaker Diarization Across Lifespan"
authors: [Anfeng Xu, Tiantian Feng, Shrikanth Narayanan]
affiliation: University of Southern California
date: 2026-05-19
arxiv_id: "2604.05201"
url: https://arxiv.org/abs/2604.05201
arxiv_html: https://arxiv.org/html/2604.05201
type: research-paper
source_type: arxiv-preprint
category: eess.AS
ingested: 2026-05-21
tags: [speaker-diarization, speech-foundation-models, lifespan, pediatric-speech, older-adult-speech, domain-adaptation, zero-shot, end-to-end-neural-diarization, age-distribution-shift, training-data-moat, whisper, voxtral, hearing-aids]
---

# Exploring Speech Foundation Models for Speaker Diarization Across Lifespan (Xu, Feng & Narayanan, May 2026)

## Bibliographic
- **Authors:** Anfeng Xu, Tiantian Feng, Shrikanth Narayanan (University of Southern California)
- **arXiv ID:** 2604.05201 (v2 posted **May 19, 2026**)
- **Category:** eess.AS (Audio and Speech Processing)
- **URL:** https://arxiv.org/abs/2604.05201
- **HTML:** https://arxiv.org/html/2604.05201

## Core Claim
Speech foundation models — the substrate currently being fine-tuned across the speech-AI field — inherit the adult-skewed pre-training distribution of the corpora they were trained on, and **fail predictably at the edges of the human lifespan** (children and older adults) when used for speaker diarization. Domain adaptation closes most of the gap.

## Method
- **Framework:** end-to-end neural speaker diarization built on top of speech foundation models.
- **Coverage:** cross-lifespan evaluation across children, adults, and older adults.
- **Regimes evaluated:**
  - **Zero-shot cross-age inference** — model trained on one age band, tested on another.
  - **Joint multi-age training** — single model trained over the full lifespan distribution.
  - **Domain-specific adaptation** — targeted adaptation to the age band of interest.

## Headline Finding
Foundation models trained on adult-skewed corpora **systematically degrade at the edges of the lifespan**. Cross-age zero-shot transfer is weakest at the youngest and oldest age bands. Domain adaptation closes most of the gap.

## Strategic Significance for Hearing AI
- **Customer-base alignment.** The hearing-aid customer base is **over-65 weighted** — exactly the long-tail of the lifespan where foundation models trained on adult-skewed corpora fail hardest.
- **Pediatric platforms now shipping at scale.** Oticon Play SI (April 2026) brought flagship pediatric AI hearing aids to market with 4D sensors and LE Audio; pediatric softband BCD candidacy is expanding (May 2026). Diarization quality at the pediatric edge of the lifespan now has product-level stakes.
- **Diarization is foundational** for multi-talker scene handling, conversation tracking, target-speaker extraction, and Auracast routing inside hearing aids. Errors propagate downstream into scene classification, beamforming, and personalized listening.
- **All current foundation-model substrates inherit the same age-distribution shift.** Whisper, Voxtral, Qwen3-ASR, and the QVAC MedPsy family are pre-trained on corpora that are adult-skewed by construction.
- **A new dimension of training-data moat.** Lifespan-stratified speech corpora and **age-conditioned adapters** become differentiating assets — alongside the audiogram/telemetry/fitting-outcome corpora already discussed in the pre-training-corpus-as-moat synthesis.
- **WCA 2026 Seoul (May 24–27, 2026)** "AI for the Ear and Beyond" track is the natural surfacing venue for this argument.

## Limits / Open Questions
- The paper evaluates **diarization**, not the full HA SE / scene-classification stack. The age-band degradation pattern needs to be replicated for the downstream tasks that hearing aids actually run.
- The relevant adapter form for hearing aids — **on-device** vs **companion-phone** — is not addressed; the foundation models themselves are far too large to fit a hearing-aid SoC and most likely live on the paired phone tier (see companion-phone-speech-pipeline).
- Older-adult speech also covaries with hearing-impaired speech production (presbyphonia, dysarthria, reduced articulatory precision); the paper does not separate age-related changes from hearing-loss-related changes.

## Related Wiki Pages
- [Cross-Lifespan Speech Models](../wiki/concepts/cross-lifespan-speech-models.md)
- [Speech Enhancement Neural Networks](../wiki/concepts/speech-enhancement-neural-networks.md)
- [On-Device ML in Hearing Aids](../wiki/concepts/on-device-ml-hearing-aids.md)
- [Medical-Domain Edge LLMs](../wiki/concepts/medical-domain-edge-llms.md)
- [Small Language Models for Edge AI](../wiki/concepts/small-language-models-edge-ai.md)
- [Demant / Oticon](../wiki/entities/demant-oticon.md) — Play SI pediatric platform
- [Companion-Phone Speech Pipeline](../wiki/concepts/companion-phone-speech-pipeline.md)
