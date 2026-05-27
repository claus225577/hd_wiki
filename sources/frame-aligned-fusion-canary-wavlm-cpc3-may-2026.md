---
title: "Frame-Aligned Fusion of Canary and WavLM for Non-Intrusive Intelligibility Prediction of Hearing-Aid-Processed Speech"
type: source
source_type: arxiv-paper
authors: [Kazushi Nakazawa]
institution: not disclosed in arXiv metadata
arxiv_id: 2605.23619
url: https://arxiv.org/abs/2605.23619
published: 2026-05-22
ingested: 2026-05-27
tags: [intelligibility-prediction, hearing-aid-evaluation, speech-foundation-models, encoder-fusion, cpc3, clarity-prediction-challenge, binaural-processing, wavlm, canary]
---

# Frame-Aligned Fusion of Canary and WavLM for Non-Intrusive Intelligibility Prediction of Hearing-Aid-Processed Speech

## Bibliographic
- **Author:** Kazushi Nakazawa
- **arXiv:** 2605.23619 (eess.AS)
- **Submitted:** 22 May 2026
- **Length:** short technical paper

## Abstract (verbatim)
> Non-intrusive intelligibility prediction estimates how well hearing-impaired listeners understand hearing-aid-processed speech without a clean reference. We study this task in the 3rd Clarity Prediction Challenge using two frozen speech encoders, Canary and WavLM. The central question is not only whether complementary pretrained representations should be combined, but where their interaction should occur. We compare single-backbone baselines, uniform score averaging, pool-late fusion, cross-attention, frame-aligned fusion, and reverse alignment under a shared left/right-preserving binaural framework. Among the compared systems, the best model temporally prepares WavLM with a learnable strided convolution and fuses it with Canary on the coarser Canary timeline before pooling, reaching Eval RMSE 24.96±0.06 and Eval Corr 0.796±0.001. Severity, enhancement-system, layer-window, and temporal-shift analyses indicate that coarse local temporal correspondence before pooling is a useful inductive bias for this task.

## Key Extraction

### Problem
- **Non-intrusive intelligibility prediction**: predict the percentage of words a hearing-impaired listener correctly recognizes from hearing-aid-processed speech *without* access to a clean reference signal.
- Test bed: 3rd Clarity Prediction Challenge (CPC3) — dynamic listening environments, real backgrounds, measured hearing-aid signals, audiogram-stratified listener pool.

### Encoders Compared (both frozen)
- **Canary** (Nvidia) — ASR-side speech foundation model.
- **WavLM** (Microsoft) — self-supervised speech representation model.
- Two complementary representational priors: lexical-aware vs general-acoustic.

### Fusion Strategies Compared (the actual contribution)
1. Single-backbone baselines
2. Uniform score averaging
3. Pool-late fusion (concatenate after pooling)
4. Cross-attention between the two encoders
5. **Frame-aligned fusion** (winner — see below)
6. Reverse alignment (Canary into WavLM timeline)

### Best Configuration
- Take WavLM features, run a **learnable strided convolution** to temporally compress them onto the coarser Canary timeline.
- Concatenate frame-aligned with Canary features before pooling.
- Read off intelligibility score from a compact trainable head.
- **Eval RMSE: 24.96 ± 0.06**
- **Eval Corr: 0.796 ± 0.001**
- Uses a shared left/right-preserving binaural framework (does not collapse to monaural at any stage).

### Headline Inductive Bias
> Coarse local temporal correspondence before pooling is a useful inductive bias.

That is: the two encoders should agree about *when* a frame is what before they are asked to agree about *what* it is.

### Stated Ablations
- Severity (audiogram-stratified) analysis
- Enhancement-system (which CPC3 SE system processed the input) analysis
- Layer-window (which transformer layers to read from) analysis
- Temporal-shift analysis

## Why It Matters for Hearing-Aid AI
1. **Evaluation-stack rebuild.** Following the May 2026 "three cracks" papers (L3-SE, Behringer, de Oliveira), this is the first concrete look at what the *replacement* yardstick architecture is becoming: frozen foundation-model fusion with binaural preservation, trained on listener-stratified CPC3-style labels.
2. **Architectural choice over encoder choice.** The lever moved from "which encoder" to "where do they fuse." For OEM evaluation teams this re-prioritizes the search space.
3. **Binaural-preserving framework is the design constant.** Multiple groups now treat binaural information as non-optional during evaluation — important because hearing aids are binaural devices and the wearer's spatial perception is part of "intelligibility."
4. **Compact head, frozen backbones.** Reachable inference cost for a server-side evaluation harness; not viable on-chip, but appropriate for fitting-software and central QA.

## Relations
- Direct successor to the three May 2026 "evaluation stack cracks" papers; provides constructive direction where they provided critique.
- Sibling to other CPC3 submissions and to the broader speech-foundation-model intelligibility-prediction literature (Whisper-based, layer-fusion, etc.).
- Methodologically downstream of WavLM (Microsoft) and Canary (Nvidia) as frozen-backbone foundation models for speech.

## Open Questions
- What encoder pair maximizes prediction quality at fixed eval-cost budget? Whisper × WavLM, Canary × HuBERT, Whisper × MERT, etc., are untested at frame-aligned-mid-fusion.
- Does the temporal-alignment trick generalize to other audio evaluation problems (faithfulness, effort)?
- Will CPC4 require submissions to specify a fusion architecture rather than a single backbone? The challenge is implicitly drifting in that direction.
- Can on-device approximations of this evaluator close the cloud-vs-device gap for in-clinic verification?
