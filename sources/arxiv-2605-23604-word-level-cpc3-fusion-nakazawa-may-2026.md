---
title: "Word-Level Modeling with Alignment-Aware Acoustic Fusion for Text-Assisted Intelligibility Prediction in Listeners with Hearing Loss"
type: source
source_type: arxiv-paper
authors: [Kazushi Nakazawa]
institution: not disclosed in arXiv metadata
arxiv_id: 2605.23604
url: https://arxiv.org/abs/2605.23604
published: 2026-05-22
ingested: 2026-05-27
tags: [intelligibility-prediction, hearing-aid-evaluation, speech-foundation-models, encoder-fusion, cpc3, clarity-prediction-challenge, whisper, word-level-modeling, text-assisted]
---

# Word-Level Modeling with Alignment-Aware Acoustic Fusion for Text-Assisted Intelligibility Prediction in Listeners with Hearing Loss

## Bibliographic
- **Author:** Kazushi Nakazawa (same author as arXiv:2605.23619, ingested 2026-05-27)
- **arXiv:** 2605.23604 (eess.AS)
- **Submitted:** 22 May 2026 — same date as the Canary+WavLM frame-aligned-fusion paper
- **Length:** short technical paper, CPC3 challenge submission

## Key Extraction

### Problem (same as the companion paper)
- Text-assisted speech intelligibility prediction for hearing-impaired listeners under the 3rd Clarity Prediction Challenge (CPC3).
- "Text-assisted" = the canonical transcript of the utterance is available at prediction time (as opposed to fully non-intrusive, where it is not). This is the *reference-aware* track.

### Architecture
1. **Frozen Whisper encoder** ingests the degraded (hearing-aid-processed) speech.
2. **Teacher-forced decoder** conditions on the canonical transcript and produces per-word correctness probabilities.
3. **Word-aligned local acoustic branch** uses character-level cross-attention alignment to align acoustic features to reference words — captures *where in the audio* each reference word lives and how degraded it is locally.
4. **Utterance-level global acoustic branch** adds a calibration pass over the whole utterance.
5. Sentence-level intelligibility = mean predicted correctness probability across valid reference words.

### Inductive bias (the actual contribution)
- The lever is *word-level reference conditioning*, not encoder choice. Decoder-state evidence from a transcript-conditioned model is informative about intelligibility because the decoder's per-word confidence already correlates with whether a hearing-impaired listener will recognize that word.
- Adds two acoustic branches as residual signal on top of the decoder states.

### Numerical Results (official CPC3 evaluation set)
| Variant                         | RMSE  | Correlation | F1 (incorrect word) | MCC   |
|---------------------------------|-------|-------------|---------------------|-------|
| Decoder baseline                | 24.92 | 0.795       | —                   | —     |
| Joint fusion (local + global)   | 24.39 | 0.806       | 0.778               | 0.626 |

Modest but real gain over a strong decoder baseline.

### Relationship to the Companion Paper (arXiv:2605.23619)
- Same author, same date, same challenge — Nakazawa has submitted *two distinct CPC3 papers* on the same day attacking the problem from different angles:
  - **2605.23619** (frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md): non-intrusive track, encoder-fusion lever, Eval RMSE 24.96 / Corr 0.796.
  - **2605.23604** (this paper): text-assisted track, word-level reference-conditioning lever, Eval RMSE 24.39 / Corr 0.806.
- Together they bracket the "what do you have at prediction time" axis: 2605.23619 = no reference, 2605.23604 = full reference. Both reach correlation ~0.80, suggesting the *ceiling for this class of frozen-encoder approaches is converging*.
- Headline takeaway: text-assisted gives ~+0.01 in correlation over non-intrusive on this evaluation — much smaller than one might naively expect. The interesting question is *why the gap is so small*.

## Why This Matters

### For the wiki
- Second CPC3 paper from this author in the same week. The "Nakazawa-CPC3" cluster now has two anchored sources and is becoming wiki-significant. When a third lands, a comparison page (`comparisons/non-intrusive-vs-text-assisted-cpc3.md`) becomes worth the cost.
- The convergence of non-intrusive and text-assisted correlation at ~0.80 is a *negative result worth tracking* — it implies the frozen-foundation-model encoder approach has a ceiling that adding a transcript does not break through. Either the ceiling is real (and the next step is to unfreeze the encoder for the hearing-aid domain) or the CPC3 label noise is the floor (and the metric needs revisiting).

### For hearing-aid R&D
- Word-level confidence outputs (not just sentence-level scores) are actionable for in-aid feedback loops: a system that flags *which words* a listener likely missed could drive request-to-repeat prompts, transcript surfacing on the companion device, or selective re-amplification of upcoming words sharing acoustic features with the missed one.

## Open Questions
- Does the word-level confidence head transfer to listeners outside the CPC3 audiogram distribution?
- Is the gap between non-intrusive and text-assisted really only ~0.01 in correlation, or is the test set under-discriminating?
- Why is Nakazawa publishing two separate papers rather than a unified comparison? (Possible: separate challenge tracks have separate submission rules.)

## Cross-References (existing wiki)
- `concepts/non-intrusive-intelligibility-prediction.md` — direct conceptual home (created during 2026-05-27 LinkedIn-ingest pass)
- `concepts/foundation-model-fusion-speech.md` — adjacent: where do frozen encoders meet
- `sources/frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md` — companion paper, same author, same date
- `entities/clarity-prediction-challenge.md` — challenge entity
- `concepts/listening-effort-evaluation.md` — adjacent metric class

## Tags
intelligibility-prediction, hearing-aid-evaluation, speech-foundation-models, encoder-fusion, cpc3, clarity-prediction-challenge, whisper, word-level-modeling, text-assisted
