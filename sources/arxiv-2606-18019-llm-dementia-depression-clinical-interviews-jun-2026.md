---
title: "Reading between the Lines: Leveraging Large Language Models for Global Dementia and Depression Assessment from Clinical Interviews"
type: source
source_type: arxiv-paper
arxiv_id: 2606.18019
authors: [Franziska Braun, Alea Rüggeberg, Thomas Ranzenberger, Hartmut Lehfeld, Thomas Hillemacher, Tobias Bocklet, Korbinian Riedhammer]
affiliations: [Technische Hochschule Nürnberg Georg Simon Ohm (Bocklet, Riedhammer, likely Braun/Ranzenberger/Rüggeberg), Paracelsus Medical University Nürnberg (Lehfeld, Hillemacher)]
date_published: 2026-06-16
ingested: 2026-06-17
url: https://arxiv.org/abs/2606.18019
tags: [dementia, depression, llm-clinical-evaluation, open-weights-llm, mistral, deephermes, qwen3, german-language, history-taking-interview, global-deterioration-scale, global-depression-scale, pause-enriched-transcripts, structured-feature-extraction]
---

# Reading between the Lines — LLMs for Dementia and Depression Assessment (Braun et al., June 2026)

## Bibliographic
- **Authors:** Franziska Braun, Alea Rüggeberg, Thomas Ranzenberger, Hartmut Lehfeld, Thomas Hillemacher, Tobias Bocklet, Korbinian Riedhammer
- **Likely affiliations:** Technische Hochschule Nürnberg Georg Simon Ohm (Bocklet, Riedhammer, and the speech-ML group); Paracelsus Medical University (Lehfeld, Hillemacher, clinical psychiatry)
- **Posted:** 16 June 2026 (arXiv:2606.18019)
- **URL:** https://arxiv.org/abs/2606.18019

## Problem
Most LLM-for-clinical-speech work targets Cookie Theft or other constrained elicitations on English-language US-clinic populations. The real clinical workflow is the **standardised history-taking interview** — a longer, less constrained, more naturalistic conversation, in the patient's native language, where clinicians read both dementia *and* depression signals simultaneously and often co-occurringly. There is also a structural objection to closed-API LLMs in clinical settings (data residency, audit, on-prem deployability).

## Contribution
Braun et al. evaluate **open-weights LLMs** — **Mistral 3.1, DeepHermes, Qwen3** — on:
- **154 German-speaking subjects**
- **Standardised history-taking interviews** (not Cookie Theft)
- Dual outcome targets:
  - **Global Deterioration Scale (GDS)** — dementia severity, 1–7
  - **Observer-based Global Depression Scale** — depression severity

The methodological move is comparing **zero-shot LLM scoring** to **structured-feature-extraction + LLM scoring** (i.e. extract clinician-meaningful intermediate variables first, then score from those).

## Headline Numbers
- **Best MAE 0.60 — depression (zero-shot).** Zero-shot is already the best on depression. Depression signal is apparently dense enough in the interview transcript that explicit feature extraction does not help.
- **Best MAE 0.78 — dementia (with structured feature extraction).** Dementia needs the structured-feature stage.
- **Up to 35% error reduction** from structured feature extraction vs zero-shot baseline (on dementia).
- **Pause-enriched transcripts approach human-transcription quality** — i.e. running the ASR with explicit pause / disfluency annotation closes most of the gap to human-transcribed reference.

## Why It Matters for Hearing AI

### 1. Open-weights LLMs at clinical-grade scoring quality
The Mistral / DeepHermes / Qwen3 result is the key strategic data point. Closed-API LLMs (GPT-4, Claude) are non-starters for an in-clinic or on-device hearing-care companion. Open-weights LLMs at sub-1 MAE on a clinician-graded depression / dementia rating is what makes the **on-device / on-prem deployment path** for a longitudinal speech-derived clinical companion app actually plausible — see [[../wiki/concepts/medical-domain-edge-llms.md]].

### 2. Pause-enriched transcripts as a hearing-aid native feature
ASR systems already detect non-speech intervals to gate VAD. Surfacing those gaps into the transcript as **typed pause / disfluency annotations** is a cheap upgrade that, per this paper, closes most of the gap to a human transcriber for downstream LLM scoring. This is exactly the kind of low-cost, high-leverage telemetry change a hearing-aid companion-app pipeline can ship.

### 3. Multilingual / non-English clinical evidence
Most LLM-for-dementia work has been English (DementiaBank Pitt, ADReSS). Working in **German** with a German clinical scale — and getting structured-feature-extraction gains on it — argues that the rubric-scoring pattern transfers across languages without re-training. That is the regulatory and product story for any hearing-care OEM operating outside the US.

### 4. Dementia and depression in one pass
Hearing loss is a risk factor for both dementia (see [[../wiki/concepts/hearing-loss-dementia-link.md]]) and depression in older adults. A single audio substrate that can score both — and a paper that shows the optimal scoring strategies differ per construct — is the structural argument for a multi-target hearing-care cognitive companion, not a single-disease screening tool.

## Limits / Open Questions
- 154 subjects is small. Generalisation across clinical sites and across non-German-speaking populations is open.
- Interview audio was clinician-conducted in a controlled setting, not ambient hearing-aid telemetry. Distribution shift to the ambient case is unmeasured.
- The structured-feature stage is presumably hand-engineered. Whether the engineered feature set generalises to other clinical scales (GDS for depression, MMSE, MoCA) is open.
- The pause-enriched transcript pipeline depends on a high-quality ASR upstream — the elderly-ASR failure mode ([[../wiki/concepts/elderly-speech-recognition.md]]) propagates straight into this scoring layer.

## Related Wiki Pages
- [[../wiki/concepts/digital-phenotyping-cognitive-decline.md]] — main cognitive-screening container
- [[../wiki/concepts/elderly-speech-recognition.md]] — upstream ASR substrate
- [[../wiki/concepts/hearing-loss-dementia-link.md]] — clinical context
- [[../wiki/concepts/medical-domain-edge-llms.md]] — open-weights LLM deployment surface
- [[../wiki/concepts/companion-phone-speech-pipeline.md]] — deployment substrate

## Related Sources
- [Cognitive-linguistic Features for Dementia (Xu et al., Jun 2026)](arxiv-2606-18054-cognitive-linguistic-features-dementia-jun-2026.md) — same week, English Cookie Theft, Claude 3.5 Sonnet rubric scoring
- [Cross-Lingual Alzheimer Detection (Girish et al., Jun 2026)](arxiv-2606-17254-cross-lingual-alzheimer-detection-jun-2026.md) — same week, multilingual axis
- [Elderly-ASR papers (Deng et al., Jun 2026)](arxiv-2606-16539-elderly-asr-online-adaptation.md) — upstream transcription substrate
