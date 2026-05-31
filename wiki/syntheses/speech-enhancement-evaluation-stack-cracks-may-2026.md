---
title: The Hearing-AI Speech-Enhancement Evaluation Stack — Three Cracks in Twelve Days (May 2026)
type: synthesis
created: 2026-05-19
updated: 2026-05-28
sources:
  - codec-intelligibility-se-behringer-arxiv-2026.md
  - l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md
  - asr-too-good-to-be-true-arxiv-may-2026.md
  - frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md
  - arxiv-2605-23604-word-level-cpc3-fusion-nakazawa-may-2026.md
related:
  - listening-effort-evaluation.md
  - linguistic-hallucination-speech-enhancement.md
  - lalm-selective-auditory-attention.md
  - speech-enhancement-neural-networks.md
  - llm-based-speech-enhancement.md
  - companion-phone-speech-pipeline.md
  - dnn-in-hearing-aids.md
  - non-intrusive-intelligibility-prediction.md
  - foundation-model-fusion-speech.md
  - clarity-prediction-challenge.md
tags: [evaluation-metrics, speech-enhancement, asr-wer, listening-effort, linguistic-hallucination, hearing-aid-ai, synthesis, interspeech-2026, foundation-model-fusion, cpc3]
---

# The Hearing-AI Speech-Enhancement Evaluation Stack — Three Cracks in Twelve Days (May 2026)

Between May 5 and May 12, 2026, three independent papers (all submitted to Interspeech 2026) each argued that one of the field's most-used speech-enhancement (SE) evaluation tools is structurally inadequate for the modern generative-SE regime. Read together, they make a single argument: **the current evaluation stack systematically flatters models that the human hearing-aid wearer will still struggle with.**

## The Three Papers

### 1. Behringer et al. (arXiv:2605.03776, May 5)
**Crack: Intelligibility scores hide effort differences.**

- First codec-level demonstration that **listening-effort metrics reveal differences invisible to intelligibility scores**.
- Neural codecs degrade more than classical codecs as noise rises — directly contradicting the "neural is always better" prior in the LE Audio / Auracast era.
- ASR-derived metrics correlate strongly with subjective effort — a usable automatic proxy.

### 2. L3-SE — Wang et al. (arXiv:2605.08608, May 9)
**Crack: PESQ/STOI/HASPI miss linguistic hallucination.**

- Language-model-based SE produces "perceptually plausible yet linguistically incorrect" output under heavy noise.
- The audio sounds clean, but the words the listener hears are not the words that were actually spoken.
- This is a categorical new failure mode: the LM in the SE has prior over plausible speech and reconstructs *something* coherent. No standard SE metric flags this.

### 3. de Oliveira, Peer & Gerkmann (arXiv:2605.12107, May 12)
**Crack: ASR-WER itself is broken from the opposite direction.**

- Modern ASR systems with large-scale noisy training and embedded language models correlate more with human WER than simpler ones — *but* the noise robustness and contextual inference that drive that correlation are "uninformative to an acoustics-focused evaluation".
- The yardstick has a built-in language prior that transcribes correctly through residual SE failure.
- In effect, the SE failure mode L3-SE warns about (LM-driven hallucination in the *enhancer*) recurs in the *evaluator*: a generative model with incentive to cover for its sibling.

## The Unified Argument

The two most common ladders for evaluating hearing-aid speech enhancement —
- **Perceptual surrogates** (PESQ, STOI, HASPI, HASQI, SI-SNR, DNS-MOS), and
- **ASR-derived WER** —

both reward systems for hallucinating around their own failures, in different ways:

| Failure mode the model exhibits | Why perceptual surrogates miss it | Why ASR-WER misses it |
|---|---|---|
| LM in the SE invents plausible but wrong words | Audio is perceptually clean; PESQ/STOI/HASPI score high | A noise-robust ASR also transcribes the plausible words confidently |
| Effort-only degradation (intelligibility tied, fatigue doubled) | No effort term in the loss | ASR-WER does not measure cognitive cost on the listener |
| Late-reverberation residual or codec-induced spectral damage | Surrogate metric averages over the residual | LM in ASR repairs the resulting word ambiguity |

For voice assistants and dictation, these gaps are tolerable — the listener is the ASR. For hearing aids, **the listener is the metric**, and acoustic faithfulness is the entire product.

## What's Unbuilt — the Concrete List

The three papers, taken together, name three distinct evaluation primitives that the hearing-aid field needs and that are not off the shelf today:

1. **Word-level linguistic faithfulness** — independent of perceptual quality. A "did the model report the words that were actually said?" metric that does not itself contain a language model with incentive to cover. (L3-SE).
2. **Listening effort at HA-relevant SNRs** — a HASPI-equivalent for cognitive cost; today only pupillometry, dual-task RT, and subjective scales exist, none scalable to telemetry. (Behringer et al.).
3. **ASR-independent acoustic faithfulness** — a yardstick whose evaluator does not itself reconstruct intended meaning from broken input. (de Oliveira / Peer / Gerkmann).

All three would need to exist before generative SE ships into hearing aids with the rigor the field expects of a medical device.

## Why These Three Cracks Compound

The cracks are not independent. They reinforce in a specific pattern:

- A generative SE that hallucinates words (L3-SE) produces audio whose listener will need more effort to extract meaning (Behringer) and whose damage is exactly what a modern ASR's language prior will smooth over (de Oliveira et al.).
- A hearing-aid R&D team optimizing PESQ + ASR-WER would deploy this model and watch the metrics improve while the wearer's listening fatigue rose and word-level errors went unnoticed.
- The generative-SE wave is not theoretical — DriftSE (May), DiffVQE (May), and predictive-generative drift decomposition (May) all argue single-step generative SE is increasingly within real-time budgets for the companion-phone tier upstream of the hearing aid.

## Implications

### For OEM R&D
- Don't ship a feature whose only proof point is a WER number from a SOTA ASR.
- Pair every ASR-based eval with formal listener panels — and make at least one panel hearing-impaired.
- Treat acoustic faithfulness, linguistic faithfulness, and effort as separate axes; one cannot substitute for the others.

### For Companion-Phone Pipelines
- When upstream cleaning (DiffVQE-class) hands audio to the aid, the aid inherits the upstream's faithfulness liabilities. A trust-calibration layer on the device — "how much should I trust what arrived?" — is now a first-class requirement, not a future research direction.

### For Regulators
- Any FDA / EMA AI-ML SaMD pathway accepting WER-based SE validation will need to specify which ASR and what text normalization. As written today, both choices materially move the result.

### For Researchers
- "We beat SOTA on PESQ + STOI + DNS-MOS" is no longer a complete claim for an SE paper targeting hearing aids. The bar is rising in real time, and Interspeech 2026 may be where it shifts.

## Open Questions

- What does a HASPI-equivalent for **faithfulness** look like? Does it need to be reference-based at all, or can a separate forced-alignment system provide ground truth?
- Can ASR-derived effort proxies (Behringer's positive finding) generalize to hearing-impaired listeners, or do they break the same way ASR-WER does?
- Will Interspeech 2026 codify any of these as challenge tracks? (DASR, URGENT, and Audio Reasoning Challenge are precedents for shifting evaluation by inviting submissions.)

## Update — 27 May 2026: What the Replacement Architecture Is Starting to Look Like

Ten days after the third crack landed, the first concrete look at the *replacement* yardstick appeared.

**Nakazawa, "Frame-Aligned Fusion of Canary and WavLM for Non-Intrusive Intelligibility Prediction of Hearing-Aid-Processed Speech"** (arXiv:2605.23619, 22 May 2026) attacks CPC3 (3rd Clarity Prediction Challenge) with two frozen speech encoders — Nvidia **Canary** (ASR-side) and Microsoft **WavLM** (SSL-side) — and asks the question every multi-foundation-model system now has to answer: **where do you fuse?**

- Compares single-backbone, uniform score averaging, late-pool, cross-attention, frame-aligned, reverse-aligned fusions under a left/right-preserving **binaural** framework.
- Best: **temporally prepare WavLM with a learnable strided convolution, frame-align with Canary on the coarser Canary timeline, fuse before pooling.**
- **Eval RMSE 24.96, Eval Corr 0.796.**
- Headline inductive bias: *coarse local temporal correspondence before pooling.*

### What This Tells the Field
1. The lever moved up one layer: from "which encoder" to "where do they fuse." Encoder-pair × fusion-architecture is the new search space.
2. **Binaural preservation has become a design constant** in the next-gen evaluator (hearing aids are binaural devices; spatial perception is part of intelligibility).
3. The replacement metric architecture is **server-side, compact head, frozen backbones** — viable for fitting software, central QA, and regulator-facing post-market surveillance, but not on-chip.
4. CPC3 is functionally becoming the field's **training set for evaluation models**, not only for SE models.

### What Is Still Missing
The Nakazawa paper addresses axis (1) — non-intrusive intelligibility under listener-stratified ground truth — but axes (2) word-level linguistic faithfulness and (3) HA-relevant listening effort remain unbuilt as deployable, foundation-model-fusion-class metrics. The architecture template now exists; the missing labels and benchmarks are the next bottleneck.

## Update — 28 May 2026: Granularity Joins as a Third Axis

Six days *before* the frame-aligned fusion paper, the same author (Nakazawa) posted a companion paper attacking CPC3 along a completely different architectural axis: predict intelligibility **word by word**, not utterance by utterance.

**Nakazawa, "Word-Level Modeling with Alignment-Aware Acoustic Fusion for Text-Assisted Intelligibility Prediction in Listeners with Hearing Loss"** (arXiv:2605.23604, 22 May 2026):

- **Frozen Whisper encoder** processes degraded speech; **decoder is conditioned on the canonical transcript**.
- **Word-aligned local acoustic branch** uses character-level cross-attention; **utterance-level global branch** calibrates.
- Per-word correctness probabilities aggregate into sentence intelligibility.
- Results on CPC3: incorrect-word F1 = 0.778, MCC = 0.626, sentence-level Corr = 0.806, RMSE = 24.39 (baseline 24.92).

### Why Granularity Is a Separable Axis
Hearing aids do not fail uniformly across speech — they fail on the **content words** (proper nouns, sentence-final keywords, low-frequency vocabulary). A sentence-level evaluator gives a wearer "73% intelligibility." A word-level evaluator tells the OEM and regulator *which 27%*, by word class, by acoustic scene, by SNR bin. That stratification is the substrate for post-market surveillance distributions that sentence-level metrics literally cannot produce.

### The Search Space Got Bigger This Week
What started (May 5) as "three cracks in the evaluation stack" and consolidated (May 22-27) into "the constructive replacement architecture" now has **three separable search axes**:

1. **Encoder choice and pairing** — Whisper / Canary / WavLM / HuBERT / Voxtral / MERT / Qwen3-ASR / ...
2. **Fusion architecture** — frame-aligned, cross-attention, late-pool, reverse-aligned, MoE-over-experts
3. **Output granularity** — utterance, sentence, **word**, phoneme

Plus the listener-model axis (population / individual-conditioned / hearing-loss-stratified) and the binaural-preservation constraint.

The two Nakazawa papers (same author, same week, same CPC3 dataset, two different axes) are the cleanest illustration this year of how fast the evaluation-metric search space is expanding. CPC3 is functionally the field's training set for *evaluation models*, not just enhancement models.

## Sources
- [Behringer et al. — On the Influence of Speech Enhancement and Codecs on Speech Intelligibility and Listening Effort](../../sources/codec-intelligibility-se-behringer-arxiv-2026.md) — listening-effort axis
- [Wang et al. — L3-SE: Reducing Linguistic Hallucination in LM-Based Speech Enhancement](../../sources/l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md) — linguistic-faithfulness axis
- [de Oliveira, Peer & Gerkmann — Too Good to Be True: Modern ASR for SE Evaluation](../../sources/asr-too-good-to-be-true-arxiv-may-2026.md) — ASR-yardstick axis
- [Nakazawa — Frame-Aligned Fusion of Canary and WavLM on CPC3 (arXiv:2605.23619)](../../sources/frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md) — the constructive direction (foundation-model fusion + binaural preservation + CPC3-style labels)
- [Nakazawa — Word-Level Modeling with Alignment-Aware Acoustic Fusion (arXiv:2605.23604)](../../sources/arxiv-2605-23604-word-level-cpc3-fusion-nakazawa-may-2026.md) — granularity as a third axis; text-assisted reference-conditioned word-level intelligibility on the same CPC3 dataset
