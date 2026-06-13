---
title: Non-Intrusive Intelligibility Prediction (Hearing-Aid-Processed Speech)
type: concept
created: 2026-05-27
updated: 2026-06-13
sources:
  - frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md
  - arxiv-2512-19374-deepgesi-non-intrusive-hi-intelligibility.md
related:
  - listening-effort-evaluation.md
  - linguistic-hallucination-speech-enhancement.md
  - speech-enhancement-neural-networks.md
  - llm-based-speech-enhancement.md
  - communication-accessibility-metric.md
  - foundation-model-fusion-speech.md
  - ../entities/clarity-prediction-challenge.md
tags: [evaluation-metrics, intelligibility-prediction, speech-foundation-models, encoder-fusion, hearing-aid-ai, non-intrusive-metrics]
---

# Non-Intrusive Intelligibility Prediction (Hearing-Aid-Processed Speech)

## Definition
A class of metrics that estimate **how well a hearing-impaired listener will understand hearing-aid-processed speech without access to a clean reference signal**. Inputs are typically:
- the hearing-aid output (left/right channels),
- the listener's audiogram (or a coded severity),
- optionally: hearing-aid configuration, prior fitting history.

Output: a predicted percentage of correctly recognized words (or a related intelligibility score), trained against a ground-truth panel of hearing-impaired listeners.

## Why It Is Different from Reference-Based Metrics
Reference-based metrics (HASPI, HASQI, STOI, PESQ) compare a processed signal to a clean one. In real hearing-aid deployment, the clean reference does not exist — the device is processing the actual scene. **Non-intrusive** metrics avoid that requirement and so are deployable for:
- field telemetry,
- real-world QA,
- A/B comparisons of processing strategies on unseen scenes,
- regulator-facing post-market surveillance.

## The Clarity Prediction Challenge Lineage
The Clarity project's CPC1 → CPC2 → CPC3 series has been the principal test bed for this metric class:
- **CPC3 (results presented Interspeech 2025, Rotterdam):** dynamic listening environments, real backgrounds, measured hearing-aid signals, 21 submissions from 14 teams, intrusive and non-intrusive tracks both populated.
- The CPC3 dataset and listener panel have become a *de facto* shared benchmark; entries since (including 2026 follow-up papers) re-attack this dataset.

## Current State of the Art (May 2026)
The leading direction is **multi-encoder frozen-foundation-model fusion** with a small trainable head.

### Nakazawa, May 22 2026 (arXiv:2605.23619)
- Fuses Nvidia **Canary** (ASR-side) with Microsoft **WavLM** (SSL-side).
- Best system: temporally prepare WavLM with a learnable strided convolution → frame-aligned fusion with Canary on the coarser Canary timeline → pool → trainable head.
- **Eval RMSE 24.96**, **Eval Corr 0.796**.
- Inductive bias: *coarse local temporal correspondence before pooling.*
- Binaural-preserving framework throughout (no left/right collapse).

### Architectural Shift
The competitive design choice has moved up the stack:
- 2022–2023: which single foundation model is the best feature extractor?
- 2024–2025: which layers within one foundation model are most informative?
- 2026: which **pair** of foundation models, and **where** do they interact?

The lever is now fusion location, not encoder identity.

## Open Methodological Questions
- What is the optimal encoder pair at fixed inference cost? (Whisper × WavLM, Canary × HuBERT, MERT × WavLM are largely untested with frame-aligned mid-fusion.)
- Does CPC3 listener-stratification generalize to other languages and to pediatric / oldest-old cohorts? (See cross-lifespan-speech-models.)
- Can a non-intrusive metric simultaneously score intelligibility *and* linguistic faithfulness, or do they need separate heads on a shared backbone? (See linguistic-hallucination-speech-enhancement.)
- Can ASR-derived effort proxies (Behringer et al., May 2026) ride on the same fused backbone? (See listening-effort-evaluation.)

## Why It Matters Strategically
- Whoever ships a HASPI-equivalent for the foundation-model era owns the de-facto reference metric for the next decade of hearing-aid AI.
- The CPC dataset is one of the very few public, listener-grounded, hearing-aid-processed corpora; it is structurally the field's training set for evaluation models, not just for SE models.
- Server-side eval cost is now compact enough to run inside a fitting-software workflow — not on-chip, but inside the clinical loop.

## Related Pages
- [[listening-effort-evaluation]] — the unbuilt third axis (effort) of the next-gen eval stack
- [[linguistic-hallucination-speech-enhancement]] — the unbuilt second axis (word-level faithfulness)
- [[llm-based-speech-enhancement]] — the failure mode this metric class needs to detect
- [[clarity-prediction-challenge]] — the dataset / challenge that anchors this work
- [[foundation-model-fusion-speech]] — the methodology
- [[communication-accessibility-metric]] — the conversational/interactional layer this metric still does not capture

## Sources
- [Nakazawa — Frame-Aligned Fusion of Canary and WavLM (arXiv:2605.23619)](../../sources/frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md) — current SOTA configuration and the architectural-lever framing
- [DeepGESI — Non-Intrusive Objective Evaluation for HI Listeners (arXiv:2512.19374)](../../sources/arxiv-2512-19374-deepgesi-non-intrusive-hi-intelligibility.md) — HI-tuned non-intrusive metric, candidate as DSP training objective
