---
title: A Comparison of Generative and Discriminative Methods for Speech Enhancement — Robustness, Complexity, and Hallucination (Saha Shetu, Habets, Brendel)
type: source
source_type: arxiv-paper
arxiv_id: 2606.02913
authors: [Shrishti Saha Shetu, Emanuël A. P. Habets, Andreas Brendel]
affiliations: [International Audio Laboratories Erlangen, Fraunhofer IIS]
published: 2026-06-01
ingested: 2026-06-08
re_ingested: 2026-06-13
url: https://arxiv.org/abs/2606.02913
tags: [speech-enhancement, generative-models, diffusion, discriminative-models, out-of-distribution, hallucination, hallucination-quantification, wer, phoneme-similarity, complexity, convergence, evaluation, hearing-aids, class-iia]
---

# A Comparison of Generative and Discriminative Methods for Speech Enhancement: Robustness, Complexity, and Hallucination

**arXiv:2606.02913** — Saha Shetu, Habets, Brendel (International Audio Laboratories Erlangen / Fraunhofer IIS, Germany), submitted 1 Jun 2026.

## What

A controlled empirical head-to-head between **diffusion-style generative SE** and **standard discriminative DNN SE** across multiple axes that the SE literature normally treats one at a time:

- **High SNR vs low SNR.**
- **Matched vs mismatched training distribution** (OOD generalization).
- **Data-volume effects** (how each paradigm scales with training-set size).
- **Model convergence behavior** during training.
- **Compute / complexity tradeoffs** at inference time.
- **Hallucination** — measured via downstream **word error rate (WER)** and **phoneme similarity**, not via perceptual surrogates (PESQ / STOI / HASPI).

## Why This Is Categorically New

This is the **first study to quantify the hallucination cost of generative SE methods against discriminative baselines using ASR-derived metrics rather than perceptual surrogates.** Prior generative-SE papers have benchmarked against PESQ / STOI / HASPI / DNSMOS — all of which are insensitive to lexical fidelity (see [[../wiki/concepts/linguistic-hallucination-speech-enhancement]]). This paper uses WER against ground-truth transcripts and phoneme-level similarity to directly measure whether the generative outputs preserve the words that were said.

The L3-SE paper (Wang et al., arXiv:2605.08608, May 14 2026) **named** linguistic hallucination as a failure mode of LM-based SE. The Fraunhofer paper **quantifies** that the same failure mode is present and measurable in diffusion-style generative SE — not just LM-based SE.

## Key Findings

- **Discriminative wins on stationary intrusive noise and in-distribution conditions** — established discriminative SE remains the strongest paradigm when the noise distribution matches training and SNR is high.
- **Generative wins on non-stationary noise and unseen reverberation (OOD)** — diffusion-style generative SE generalizes better to OOD acoustic conditions, the regime that matters most clinically.
- **Generative methods hallucinate measurably more than discriminative ones**, and the gap is **invisible to standard SE metrics** — only WER / phoneme-similarity surface it.
- **Compute / complexity gap is significant** — generative methods carry inference-cost penalties that are paradigm-level, not just architecture-level. The latency-floor work (SB-RF, DriftSE, DiffVQE, HALO) is necessary but not sufficient.
- **Data-volume scaling differs** between paradigms — at the same training-set size the two paradigms occupy different points on the quality-vs-fidelity Pareto.
- The findings argue against treating the two paradigms as interchangeable; the right choice is **acoustic-condition-dependent**, and the headline number a paper reports may not be the number that matters for a hearing-aid wearer.

## Why It Matters for Hearing Aids

- **Sober companion to SB-RF.** SB-RF (arXiv:2606.05575) made the one-step generative SE pitch — proves the *latency* floor for generative SE has cracked, opening on-chip viability for hearing-aid budgets. This paper makes the inconvenient complementary point: the *content-fidelity* problem is not yet solved, and the gap is invisible to the standard HA evaluation stack.
- **A Class IIa faithfulness-vs-quality tradeoff.** For Class IIa hearing-aid claims (EU MDR + AI Act + FDA AI/ML SaMD), this introduces a tradeoff that the audiology evaluation stack does **not** currently measure. PESQ / STOI / HASPI / HASQI / DNS-MOS all flatter generative SE outputs that score high on perceptual quality while scoring lower on lexical fidelity than discriminative baselines. A device validated only on quality metrics may ship with worse word-fidelity than the predicate it replaces.
- **Quantifies the third crack in the SE evaluation stack.** The May 2026 trio (Behringer / L3-SE / de Oliveira-Peer-Gerkmann; see [[../wiki/syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]]) argued the evaluation stack is structurally inadequate for the generative-SE regime. This paper is the **first empirical measurement** of the magnitude of the gap on the lexical-faithfulness axis, using WER + phoneme similarity as the yardstick.
- **OOD conditions are exactly the HA case.** Non-stationary noise and unseen reverberation — the conditions where generative wins on perceptual metrics and loses on lexical fidelity — are the dominant acoustic regime a real-world hearing-aid wearer encounters. The product-relevant Pareto curve runs through exactly the conditions where the two paradigms diverge most.
- **Population-asymmetric risk.** The DNN-noise-reduction benefit curve (Schulz et al. 2026) shows CI and severe-HI users gain most from aggressive SE. These are the same users least equipped to detect hallucinations independently because their ground-truth acoustic input is most degraded. Generative SE deployment without lexical-fidelity telemetry is structurally riskier for the population that benefits most.

## Carry-Forward Flags

- A paper that ships an explicit *artifact-rate metric* (analogous to WER for ASR) alongside PESQ / HASPI / CEC3 in the HA evaluation stack would close the loop. The Fraunhofer paper provides the empirical motivation; the standardized metric is still missing.
- **The hybrid-architecture answer** (generative-when-OOD, discriminative-when-in-distribution, decided by an on-device scene classifier) is the obvious next product move — and connects to the predictive-generative drift-decomposition thread (Richter et al., May 2026) where the predictive ↔ generative weight is exposed as a personalization knob.
- The companion-phone tier is the natural home for generative SE — handing off to the on-chip discriminative path when scene confidence is low. See [[../wiki/concepts/companion-phone-speech-pipeline]].
- C2D microphone projection (Nakatani et al., ICASSP 2026, arXiv:2606.13109) reduces the train-vs-deploy distribution gap upstream — partially addressing the OOD-hallucination root cause rather than only its measurement.

## Related Wiki Pages

- [[../wiki/concepts/probabilistic-generative-models-hearing-ai.md]] — Generative paradigm contender; this paper benchmarks the broader generative-vs-discriminative question.
- [[../wiki/concepts/speech-enhancement-neural-networks.md]] — Core concept page.
- [[../wiki/concepts/linguistic-hallucination-speech-enhancement.md]] — Names the failure mode; this paper quantifies it on the diffusion-SE branch.
- [[../wiki/concepts/llm-based-speech-enhancement.md]] — Adjacent generative paradigm; same hallucination class.
- [[../wiki/syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md]] — Quantification of the third crack.
- [[../wiki/concepts/close-to-distant-microphone-projection.md]] — Training-substrate complement (reduces OOD generalization burden upstream).
