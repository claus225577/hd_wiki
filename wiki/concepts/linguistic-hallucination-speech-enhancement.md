---
title: Linguistic Hallucination in Speech Enhancement
type: concept
created: 2026-05-14
updated: 2026-06-13
last_change: 2026-06-13 — added Saha Shetu / Habets / Brendel (arXiv:2606.02913, Jun 1 2026, Fraunhofer IIS / Erlangen) — the first empirical quantification of generative-SE hallucination on the diffusion-SE branch using WER + phoneme similarity rather than perceptual surrogates. Extends L3-SE's naming of the failure mode from LM-based SE to the broader generative-SE paradigm. Also added cross-references to C2D microphone projection (Nakatani et al., ICASSP 2026, arXiv:2606.13109) as an upstream mitigation via real paired training data.
sources: [l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md, asr-too-good-to-be-true-arxiv-may-2026.md, arxiv-2606-02913-generative-vs-discriminative-se-jun-2026.md, arxiv-2606-13109-c2d-microphone-projection-nakatani-jun-2026.md]
related: [llm-based-speech-enhancement.md, speech-enhancement-neural-networks.md, dnn-in-hearing-aids.md, probabilistic-generative-models-hearing-ai.md, eu-ai-act-medical-devices.md, subjective-objective-hearing-gap.md, on-device-ml-hearing-aids.md, software-defined-medical-implants.md, listening-effort-evaluation.md, lalm-selective-auditory-attention.md, close-to-distant-microphone-projection.md, training-deployment-distribution-gap.md, ../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md]
tags: [hallucination, generative-se, llm-based-se, evaluation-metrics, faithfulness, factuality, safety, hearing-aids, audiology-metrics, hallucination-quantification, wer, phoneme-similarity, diffusion-se]
---

# Linguistic Hallucination in Speech Enhancement

A failure mode of **generative** speech enhancement — particularly [[llm-based-speech-enhancement]] — in which the system outputs speech that is **perceptually plausible but linguistically incorrect**. The output sounds natural and human, but the words the listener hears are not the words that were actually spoken.

Identified and named in the May 2026 L3-SE paper (Wang et al., arXiv:2605.08608) as a distinct failure-mode category for LM-based SE. Structurally identical to text-LLM hallucination: a generative model with a strong prior confidently emitting plausible-but-false outputs under uncertainty.

## Why This Is a Categorically New Failure Mode

Classical SE failure modes are **audible to the listener**:

| Failure mode | Cause | Listener experience |
|---|---|---|
| Residual noise | Imperfect noise estimation | Hear noise alongside speech |
| Musical artifacts | Spectral processing remnants | Hear "watery" or "tonal" artifacts |
| Speech smearing | Over-aggressive mask | Speech sounds blurred / distant |
| Robotic over-suppression | Predictive model over-zeros | Speech sounds artificial / robotic |
| Phase distortion | Magnitude-only processing | Reduced speech naturalness |

In every case the listener can tell *something is wrong*, even without a reference signal. The complaint pathway works: "the new hearing aid sounds robotic in the restaurant."

**Linguistic hallucination is inaudible.** The output is fully natural-sounding speech with the wrong words. The listener has **no reference signal** to compare against — and no acoustic cue that the system has failed. The complaint pathway breaks: the listener cannot complain about an error they cannot detect.

This is structurally the same problem as text-LLM hallucination, transplanted into a real-time always-on audio device worn on the body.

## Why Generative SE Hallucinates

LM-based SE works by **predicting** clean speech under a strong language prior. Under moderate noise this is a feature — the prior fills in degraded acoustic detail and produces natural output. Under **severe** noise (low SNR, heavy reverberation, codec degradation), the acoustic evidence becomes too weak to constrain the prior, and the model falls back on what its training distribution says is plausible.

Plausible ≠ true. The model outputs a sentence that is:
- Phonotactically valid
- Lexically coherent
- Syntactically well-formed
- Semantically plausible in context
- ...and not what the speaker said

The deeper the noise, the more the output is driven by the prior rather than the input — the same dynamic as text-LLM hallucination under sparse or contradictory context.

L3-SE's mitigation strategy is to **explicitly preserve semantic content in the conditioning representation** via dual acoustic-semantic distillation, so the LM has lexical evidence to anchor against. This reduces but does not eliminate the failure mode; the question of how to detect residual hallucinations at inference time is open.

## The Evaluation-Metric Gap

The standard speech-enhancement evaluation stack measures **perceptual quality** and **intelligibility**, not **faithfulness to ground truth**:

| Metric | What it measures | Catches hallucination? |
|---|---|---|
| PESQ | Perceptual quality vs reference | No — hallucinated speech can match reference quality |
| STOI | Short-time objective intelligibility | No — measures whether *something* intelligible is present, not whether it's correct |
| SI-SNR | Scale-invariant SNR | No — assumes mask-based processing |
| HASPI | HA speech perception index | No — perceptual model, no lexical fidelity |
| HASQI | HA speech quality index | No — quality-focused |
| DNS-MOS / NISQA | Non-intrusive MOS prediction | No — predicts perceived quality |
| Listener panel subjective | Listener rating | Partial — only if reference is available |

A hallucinated output can score well on every one of these. **The field has no standard metric for the property "the words in the output match the words in the source."**

What the field needs (borrowed and adapted from the text-LLM evaluation toolkit):

1. **Word Error Rate against ground-truth transcripts.** Run an external ASR on the enhanced output, compute WER against the known clean transcript. Detects substitutions, insertions, deletions at lexical resolution.
2. **Semantic-similarity to source.** Embedding distance between enhanced-output transcript and source transcript. Catches paraphrase-level hallucinations that WER can miss.
3. **Adversarial low-SNR benchmark sets.** Curated test sets specifically in the regime where hallucination is most likely (very low SNR, heavy reverb, codec stacking).
4. **Phoneme-level fidelity scoring.** Sub-word resolution — catches errors below the word level.
5. **Confidence calibration.** Does the model know when it does not know? Output-side uncertainty estimates could let the system flag low-confidence regions to downstream consumers (or to the listener via a "uncertain audio" UI cue).

**Word-level fidelity to ground truth needs to become a first-class audiology metric.** Not as a replacement for PESQ/STOI/HASPI — those still measure real things — but as a co-equal axis. A hearing aid that achieves better PESQ but worse lexical fidelity is *not* a better hearing aid.

## Why This Matters for Hearing Aids Specifically

### 1. High-Stakes Communication

Hearing aids are used in contexts where the wrong word can cause real harm:
- **Medical:** "take *one* pill" vs "take *none*" / "take *some*"
- **Financial:** "*thousand*" vs "*million*"
- **Legal:** courtroom testimony, contract terms, witness statements
- **Safety:** "*go*" vs "*don't go*"; addresses, phone numbers, names
- **Family:** Names of grandchildren, medications, appointments

The base rate of dangerous hallucinations may be low, but the cost of any single instance is high — and the listener has no way to verify against the source acoustic signal because the hearing aid is the only path the audio takes to their ear.

### 2. No External Verification Path

A text-LLM hallucination is at least typically read by a sighted user who could plausibly notice an inconsistency. A hearing-aid hallucination is consumed by a hearing-impaired listener whose default mode is to **trust the device's reconstruction** — that is literally what the device is for.

There is no spell-checker for processed audio at the listener's ear.

### 3. Asymmetric Trust by User Group

The [[dnn-in-hearing-aids]] page documents that DNN benefit correlates inversely with baseline hearing ability — **CI users (+5.7 dB) and severe HI users gain most** from aggressive enhancement. These are exactly the users whose ground-truth acoustic input is most degraded — and therefore the users least able to detect hallucinations independently. The population most likely to benefit from generative SE is also the population least equipped to catch its errors.

### 4. Regulatory Implications

EU MDR + AI Act and FDA AI/ML SaMD frameworks were designed around algorithms whose failure modes are detectable through standard quality / intelligibility metrics. A device that can confidently output the wrong words is a categorically new product-risk class. Likely regulatory consequences:

- **Predetermined change control plans** (PCCPs) for generative SE will need to specify hallucination-rate bounds, not just quality bounds.
- **Post-market surveillance** will need lexical-fidelity telemetry, not just user-comfort ratings.
- **Substantial-equivalence (510(k))** comparisons to predicate non-generative devices may not apply; hallucination is a new failure mode without a predicate.

See [[eu-ai-act-medical-devices]] and [[software-defined-medical-implants]].

### 5. Connection to the Subjective-Objective Gap

Hallucination is a sharper edge case of the [[subjective-objective-hearing-gap]] problem: the subjective experience (sounds fine) is decoupled from the objective ground truth (wrong words). Standard hearing-aid fitting infrastructure has no instrument that surfaces this gap — fitting verifies amplification targets, not lexical fidelity.

## What the Field Needs to Build, In Order

1. **A standard hallucination benchmark.** Public test set with controlled low-SNR / reverb conditions, ground-truth transcripts, and standardized scoring (WER + semantic-similarity).
2. **A faithfulness metric in the HA evaluation stack.** Co-equal with PESQ/STOI/HASPI in published evaluations.
3. **Inference-time confidence estimates.** A generative SE system that can say "I am uncertain about this segment" lets downstream code fall back to predictive / mask-based processing for that segment — a hybrid that resembles the predictive-generative drift decomposition of Richter et al. but gated on lexical confidence rather than residual energy.
4. **Hearing-impaired listener evaluations focused on lexical fidelity, not just quality.** Forced-choice transcription tests under enhanced output for HI and CI listeners.
5. **Regulatory guidance for generative SaMD.** A formal expectation that hallucination-rate bounds are documented and monitored.

Hearing-aid manufacturers shipping LM-based or generative SE without this stack in place will be shipping a category of risk the field has not seen before.

## Relationship to Other Failure Modes

| Failure mode | Detectable by listener? | Detectable by current metrics? |
|---|---|---|
| Residual noise | Yes | Yes (PESQ, SNR) |
| Musical artifacts | Yes | Partially (PESQ, listener) |
| Robotic over-suppression | Yes | Partially (subjective) |
| Speech smearing | Yes | Yes (STOI, HASPI) |
| **Linguistic hallucination** | **No** | **No** (none of the standard SE metrics) |

The right-hand column is the structural argument: the standard evaluation stack was designed for the top four rows. Linguistic hallucination breaks the assumption that quality metrics suffice.

## Open Questions

- **Base rate.** What is the actual hallucination rate of current LM-based SE systems on representative HA acoustic conditions? L3-SE reports reduction but not absolute rates on a shared benchmark.
- **Severity distribution.** Are most hallucinations harmless (filler-word substitutions) or are dangerous high-impact substitutions over-represented in the long tail?
- **User detection thresholds.** Can listeners detect hallucinations from context alone, without acoustic cues? How does this vary by hearing-loss severity?
- **Hybrid architectures.** Can a confidence-gated hybrid (predictive for low-confidence segments, generative for high-confidence) eliminate dangerous hallucinations while keeping naturalness gains?
- **Multilingual / accent fairness.** Hallucination rates likely concentrate in under-represented populations in training data — an outcome-equity question.
- **Adversarial robustness.** Can a malicious actor craft acoustic input that *deliberately* induces a target hallucination at the listener's ear? (Speculative but the threat model is now coherent.)

## Related Pages
- [[llm-based-speech-enhancement]] — the architectural paradigm where this failure mode was first named
- [[speech-enhancement-neural-networks]] — broader SE context; classical failure-mode catalog
- [[dnn-in-hearing-aids]] — production SE lineage; standard evaluation stack
- [[probabilistic-generative-models-hearing-ai]] — counter-paradigm with explicit likelihoods; offers interpretable failure-mode analysis
- [[eu-ai-act-medical-devices]] — generative SaMD raises new regulatory questions
- [[subjective-objective-hearing-gap]] — hallucination is the sharpest instance of this gap
- [[on-device-ml-hearing-aids]] — deployment context; faithfulness telemetry is an open infrastructure question
- [[software-defined-medical-implants]] — post-market surveillance and PCCP implications
- [[close-to-distant-microphone-projection]] — upstream mitigation via real paired training data
- [[training-deployment-distribution-gap]] — broader framing: hallucination is the SE-side instance of the distribution gap

## The Evaluator Problem (May 2026)

The standard objective fallback for catching hallucinations would be: run an ASR on the SE output and compute WER against ground truth. **de Oliveira, Peer & Gerkmann (arXiv:2605.12107, May 12 2026)** argue this fallback is broken — modern ASRs have their own embedded language models with strong priors over plausible speech, and those LMs can transcribe correctly through residual acoustic damage that the SE failed to remove. The ASR-evaluator hallucinates *with* the SE-hallucinator in the same direction, hiding the failure.

This compounds the gap: the SE has an LM prior that produces plausible-but-wrong words; the evaluator has an LM prior that recognizes those words confidently. Neither side surfaces the error. The synthesis is in [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]].

## First Empirical Quantification on the Diffusion-SE Branch (Saha Shetu, Habets, Brendel, Jun 2026)

L3-SE *named* linguistic hallucination as a failure mode of **LM-based** SE. **Saha Shetu, Habets & Brendel (arXiv:2606.02913, 1 Jun 2026, International Audio Laboratories Erlangen / Fraunhofer IIS)** are the first to *quantify* the same failure mode on the **diffusion-style generative** SE branch — using **WER against ground-truth transcripts and phoneme similarity** instead of perceptual surrogates.

Key findings relevant to this concept page:

- **Generative methods hallucinate measurably more than discriminative ones**, and the gap is largest in exactly the conditions a hearing-aid wearer encounters most often — non-stationary noise and unseen reverberation (OOD).
- **The hallucination gap is invisible to PESQ / STOI / HASPI / HASQI / DNS-MOS.** A diffusion-SE output can match a discriminative baseline on every perceptual surrogate while scoring measurably worse on WER and phoneme similarity.
- **The phenomenon is paradigm-level, not architecture-level.** Latency-floor work (SB-RF, DriftSE, DiffVQE, HALO) does not solve it. Single-step generative SE inherits the hallucination class from its multi-step ancestors.

### Implications for This Page

- The failure-mode catalog is no longer LM-SE-only. The "Why This Is a Categorically New Failure Mode" section applies to diffusion-style generative SE, not only LM-based SE.
- The mitigation taxonomy gets a new entry: **upstream training-data substrate matters.** Real paired training data via C2D (Nakatani et al., ICASSP 2026, arXiv:2606.13109) narrows the OOD region the model has to extrapolate across — partially mitigating one of the upstream causes (training-distribution mismatch), though not eliminating the language-prior-driven core of the failure. See [[close-to-distant-microphone-projection]].
- For Class IIa hearing-aid claims, this is the first empirical magnitude on the lexical-fidelity tradeoff. PESQ + STOI + HASPI alone are no longer a complete validation stack for a generative SE feature.

## Sources
- [L3-SE — Reducing Linguistic Hallucination in LM-Based Speech Enhancement (Wang et al., May 2026)](../../sources/l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md) — arXiv:2605.08608; named the failure mode, proposed acoustic-semantic distillation as mitigation
- [Too Good to Be True: Modern ASR for SE Evaluation (de Oliveira, Peer & Gerkmann, May 2026)](../../sources/asr-too-good-to-be-true-arxiv-may-2026.md) — arXiv:2605.12107; argues the ASR-WER fallback is structurally inadequate as an SE evaluator
- [Saha Shetu, Habets & Brendel — Generative vs Discriminative SE Comparison (Jun 2026)](../../sources/arxiv-2606-02913-generative-vs-discriminative-se-jun-2026.md) — arXiv:2606.02913; first empirical quantification of generative-SE hallucination via WER + phoneme similarity on the diffusion-SE branch
- [Nakatani et al. — C2D Microphone Projection (ICASSP 2026)](../../sources/arxiv-2606-13109-c2d-microphone-projection-nakatani-jun-2026.md) — arXiv:2606.13109; upstream mitigation via real paired training data (reduces OOD generalization burden)
