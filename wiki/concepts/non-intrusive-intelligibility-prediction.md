---
title: Non-Intrusive Intelligibility Prediction (Hearing-Aid-Processed Speech)
type: concept
created: 2026-05-27
updated: 2026-06-26
last_change: 2026-06-26 — added Sabin/Taddei/Bailey (arXiv:2606.26342, 24 Jun 2026): Whisper-frozen-encoder + tiny MLP head trained on 151,608 listener ratings of 83 commercial HAs, correlation 0.92 vs HASPIv2's 0.83. Introduces the product-level evaluation axis (signal → product) and the new sibling concept page `product-level-ha-listener-rated-evaluation`.
sources:
  - frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md
  - arxiv-2512-19374-deepgesi-non-intrusive-hi-intelligibility.md
  - sabin-taddei-bailey-commercial-ha-database-arxiv-2606-26342-jun-2026.md
related:
  - listening-effort-evaluation.md
  - linguistic-hallucination-speech-enhancement.md
  - speech-enhancement-neural-networks.md
  - llm-based-speech-enhancement.md
  - communication-accessibility-metric.md
  - foundation-model-fusion-speech.md
  - product-level-ha-listener-rated-evaluation.md
  - subjective-objective-hearing-gap.md
  - ../entities/clarity-prediction-challenge.md
tags: [evaluation-metrics, intelligibility-prediction, speech-foundation-models, encoder-fusion, hearing-aid-ai, non-intrusive-metrics, ease-of-understanding, whisper-encoder, commercial-hearing-aid-evaluation, product-level-evaluation]
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

## June 2026 — The Unit-of-Evaluation Shift (Sabin, Taddei & Bailey)
**Sabin, Taddei & Bailey, arXiv:2606.26342 (24 Jun 2026, presented at VCCA 2026 Session 5.B the following day):**

- Dataset: **151,608 listener ratings** (104,298 after QC) of **"Ease of Understanding"** (five-point scale) on **10,394 binaural acoustic-manikin recordings** of **83 commercial hearing-aid products** across **72 realistic acoustic scenes**.
- Model: **frozen Whisper encoder** over aided + clean signals, tiny MLP head on the difference embedding.
- **Correlation vs listener ratings: 0.92 overall, vs HASPIv2's 0.83.** Loud scenes 0.89 vs 0.75. Quiet 0.79 vs 0.58. Loud-scene performance reaches single-listener-rating reliability.

### Why this is the bigger shift than CPC3 fusion
- **CPC3 work scores signals.** A single SE/HA processing output on a calibrated test scene.
- **Sabin et al. scores products.** A shipping commercial hearing aid worn in a real scene by an acoustic manikin, rated by a population.

This is the **unit-of-evaluation flip from signal-level to product-level** — covered in detail in the sibling concept page [[product-level-ha-listener-rated-evaluation]].

### Three additional implications
1. **The objective-metric era is closing.** HASPI/HASQI were SOTA because the field could not afford 100K real listener ratings on 83 commercial products. A consumer-side group (HearingTracker) has just shipped that dataset.
2. **Foundation models eat another vertical-specific stack.** Whisper — frozen, no HA-specific pretraining — beat a 20-year hand-engineered HA intelligibility metric. The pattern is now familiar enough that every domain-specific evaluator in our industry should be re-benchmarked against a frozen-foundation-model baseline this quarter.
3. **Ease of Understanding becomes a learnable target.** Aligns with the Pichora-Fuller / FUEL listening-effort lineage and the WCA 2026 communication-accessibility metric argument — the construct the field has been talking about for a decade is now optimisable on real product data.

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
- [[product-level-ha-listener-rated-evaluation]] — sibling page for the **product-level** axis introduced by Sabin et al. (Jun 2026)
- [[listening-effort-evaluation]] — the unbuilt third axis (effort) of the next-gen eval stack
- [[linguistic-hallucination-speech-enhancement]] — the unbuilt second axis (word-level faithfulness)
- [[llm-based-speech-enhancement]] — the failure mode this metric class needs to detect
- [[subjective-objective-hearing-gap]] — the gap this concept family is built to close
- [[clarity-prediction-challenge]] — the dataset / challenge that anchors this work
- [[foundation-model-fusion-speech]] — the methodology
- [[communication-accessibility-metric]] — the conversational/interactional layer this metric still does not capture

## Sources
- [Nakazawa — Frame-Aligned Fusion of Canary and WavLM (arXiv:2605.23619)](../../sources/frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md) — current SOTA configuration and the architectural-lever framing
- [Sabin, Taddei, Bailey — Large-Scale Database + Predictive Model of Listener-Rated Ease of Understanding in Commercial HAs (arXiv:2606.26342)](../../sources/sabin-taddei-bailey-commercial-ha-database-arxiv-2606-26342-jun-2026.md) — June 2026 unit-of-evaluation flip from signal to product
- [DeepGESI — Non-Intrusive Objective Evaluation for HI Listeners (arXiv:2512.19374)](../../sources/arxiv-2512-19374-deepgesi-non-intrusive-hi-intelligibility.md) — HI-tuned non-intrusive metric, candidate as DSP training objective
