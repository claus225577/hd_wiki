---
title: "A Large-Scale Database and Predictive Model of Listener-Rated Ease of Speech Understanding in Commercial Hearing Aids"
type: source
source_type: arxiv-preprint
date_published: 2026-06-24
date_ingested: 2026-06-26
authors: [Andrew Sabin, Steve Taddei, Abram Bailey]
identifier: arXiv:2606.26342
url: https://arxiv.org/abs/2606.26342
venue: arXiv eess.AS
tags: [non-intrusive-intelligibility, ease-of-understanding, commercial-hearing-aids, whisper-encoder, foundation-models, haspi, hearingtracker, listener-ratings, product-level-evaluation]
---

# A Large-Scale Database and Predictive Model of Listener-Rated Ease of Speech Understanding in Commercial Hearing Aids

## Bibliographic
- **Authors:** Andrew Sabin, Steve Taddei, Abram Bailey
- **Affiliation:** HearingTracker (consumer hearing-aid review platform + research group)
- **arXiv ID:** 2606.26342 (eess.AS)
- **Submitted:** 24 Jun 2026
- **URL:** https://arxiv.org/abs/2606.26342
- **Relation to VCCA 2026:** Featured talk in Session 5.B at VCCA 2026 main programme (Jun 25–26, https://computationalaudiology.com/vcca2026-programme/) the day after the arXiv drop — the preprint operationalises the talk.

## Headline Claim
A frozen foundation-model encoder (Whisper) + a tiny supervised head trained on listener ratings of *commercial hearing aids* in realistic scenes outperforms the field-standard objective metric HASPIv2 by a wide margin on the same listener-rated test set, and approaches listener-rating reliability in loud-scene conditions.

## Dataset
- **151,608 ratings** collected from website visitors with self-reported hearing loss completing a blind, MUSHRA-inspired listening test.
- **104,298 ratings retained after quality screening** (deduplication, anomaly filtering, calibration checks).
- **10,394 binaural acoustic-manikin (KEMAR-class) recordings** spanning **83 commercial hearing-aid products** across **72 realistic acoustic scenes** (mixed: quiet, conversational background, restaurant babble, traffic, music).
- Each rating is on a five-point **"Ease of Understanding"** scale, treated as ordinal regression downstream.
- Construction sample: by far the largest population-rated commercial-HA database in the public record.

## Model
- **Input:** aided binaural recording + clean reference (same scene without the HA).
- **Backbone:** **frozen Whisper encoder** (no fine-tuning, no domain-specific pre-training) applied to both aided and clean signals.
- **Difference embedding:** subtract / contrast aided vs clean Whisper representations to form a "what the HA did" embedding.
- **Head:** small multilayer perceptron predicting the listener-rated mean Ease of Understanding score for that recording.
- Total trainable parameters in the head: small enough that no specialised compute is needed at inference.

## Reported Results — Correlation vs Listener Ratings
| Condition | Whisper + MLP (new) | HASPIv2 (baseline) |
|---|---|---|
| **Overall** | **0.92** | 0.83 |
| **Loud scenes** | **0.89** | 0.75 |
| **Quiet scenes** | **0.79** | 0.58 |

Loud-scene performance reaches the reliability ceiling of a single listener; quiet-scene performance approaches it but does not yet hit it. HASPIv2 is the standing field benchmark for objective intelligibility scoring of HA-processed speech.

## Why This Matters for Hearing-Aid R&D
1. **Unit of evaluation flips from signal to product.** HASPI/HASQI/STOI/PESQ score *a signal*. Sabin et al. score *a product wearing a scene*. The 83-commercial-product matrix is the operational substrate for product-comparison claims, regulator-facing post-market surveillance, and competitive marketing.
2. **Foundation models eat another vertical-specific stack.** Whisper was trained on 680K hours of unstructured internet audio. Frozen. No HA-specific pretraining. Tiny head. Beat a 20-year hand-engineered HA intelligibility metric. Repeats the foundation-model takeover pattern already established in vision, ASR, biomedical NLP, protein folding.
3. **Ease-of-Understanding becomes a learnable target.** Aligns with the Pichora-Fuller / FUEL listening-effort lineage and the WCA 2026 communication-accessibility metric argument — the field has been talking about effort-and-understanding as the right wearer outcome for a decade; here is the first model that lets you optimise for it on real product data.
4. **Comparative claims face an external ruler.** A consumer-side group (HearingTracker) now holds a database that ranks shipping products on listener-rated ease. OEMs no longer fully control the evaluation narrative.

## Limitations / Open Questions
- Acoustic-manikin recording — does not capture per-wearer audiogram interactions or own-ear-canal acoustics.
- Self-reported hearing loss on web — no audiogram on file; demographic and severity distribution not yet published in detail.
- HASPIv2 is one baseline; comparison against HASQI, NCM, DeepGesi-class non-intrusive predictors (arXiv:2512.19374), CPC3-fusion approaches (arXiv:2605.23619) not yet reported.
- Five-point scale + ordinal regression vs continuous predicted score — calibration mapping for product-level claims (e.g. "Product X is 12% easier to understand than Product Y") still needs to be standardised.
- Foundation-model dependency on Whisper — if the encoder is updated / deprecated, the database labels remain but the model has to be retrained.

## Cross-References Inside This Wiki
- `wiki/concepts/non-intrusive-intelligibility-prediction.md` — primary concept this paper extends from "predict listener intelligibility on processed signal" to "predict listener ease-of-understanding on shipping product."
- `wiki/concepts/foundation-model-fusion-speech.md` — same family of frozen-foundation-encoder + small head used in CPC3 fusion work (Nakazawa, Canary + WavLM).
- `wiki/concepts/listening-effort-evaluation.md` — Ease of Understanding sits in the effort / understanding outcome family.
- `wiki/concepts/communication-accessibility-metric.md` — Pichora-Fuller WCA 2026 lineage of communication-as-outcome.
- `wiki/concepts/subjective-objective-hearing-gap.md` — paper's whole point is closing the gap.
- `wiki/syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md` — extends the "evaluation stack is cracking" argument from SE models to commercial-HA products.
- `wiki/syntheses/pretraining-corpus-as-moat-hearing-ai.md` — foundation-model-pretraining-corpus as moat applies again here.
- `wiki/entities/clarity-prediction-challenge.md` — Clarity = "challenge for SE models on HA-processed signals"; Sabin et al. = "challenge for shipping products on real listener ratings" — different unit, same logic.
- `wiki/entities/vcca-computational-audiology.md` — Sabin's Session 5.B talk was the conference preview of this preprint.
