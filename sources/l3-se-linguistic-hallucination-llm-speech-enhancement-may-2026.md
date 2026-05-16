---
title: "Reducing Linguistic Hallucination in LM-Based Speech Enhancement via Noise-Invariant Acoustic-Semantic Distillation (L3-SE)"
authors: [Zheng Wang, Xiaobin Rong, Hang Su, Tianyi Tan, Junnan Wu, Lichun Fan, Zhenbo Luo, Jian Luan, Jing Lu]
affiliation: undisclosed (eess.AS submission)
date: 2026-05-09
arxiv_id: "2605.08608"
url: https://arxiv.org/abs/2605.08608
arxiv_listing: https://arxiv.org/list/eess.AS/2026-05
type: research-paper
tags: [speech-enhancement, language-models, llm-based-se, linguistic-hallucination, acoustic-semantic-distillation, wavlm, neural-codec, autoregressive-lm, generative-se, hearing-aids, evaluation-metrics]
---

# L3-SE — Reducing Linguistic Hallucination in LM-Based Speech Enhancement (Wang et al., May 2026)

## Bibliographic
- **Authors:** Wang, Rong, Su, Tan, Wu, Fan, Luo, Luan, Lu
- **Submitted:** 9 May 2026 (arXiv:2605.08608, eess.AS)
- **URL:** https://arxiv.org/abs/2605.08608
- **Code / audio demos:** promised post-acceptance

## Core Premise

**LM-based speech enhancement** — predicting clean-speech tokens with a decoder-only language model — produces highly natural-sounding outputs because the LM has absorbed a strong language prior. But under severe noise, that same prior becomes a liability: the model generates speech that is **perceptually plausible yet linguistically incorrect**. The output sounds clean and human, but the words the listener hears are not the words that were actually spoken.

The authors call this **linguistic hallucination** and frame it as a new failure mode distinct from classical distortion or DNN over-suppression. They propose **L3-SE** (noise-invariant acoustic-semantic distillation) to mitigate it.

## Architecture (Three Components)

1. **Noise-invariant conditioning encoder** — trained with **dual distillation targets**: an acoustic teacher and a semantic teacher. Forces the encoder to produce a representation that is robust to noise while preserving both phonetic detail (acoustic) and lexical content (semantic).
2. **High-fidelity codec with learnable weighted WavLM-layer representations** — discretizes speech using WavLM-derived features, with learned per-layer weights so the codec retains the lexically-discriminative information that pure acoustic codecs strip out.
3. **Decoder-only autoregressive LM** — predicts clean-speech tokens conditioned on the acoustic-semantic features from the encoder; the same shape as a Whisper- or VALL-E-style LM but trained as a denoiser.

The novel piece is the **acoustic-semantic distillation** in (1) and (2): instead of conditioning only on acoustic features (which lose lexical content under severe noise) or only on semantic features (which lose paralinguistic detail), the LM sees a fused representation explicitly trained to preserve both.

## Reported Results

- **Substantial reduction in linguistic hallucinations**, with the largest gains in **low-SNR and reverberant conditions** — exactly the regime where hearing-impaired listeners struggle most.
- **Perceptual quality preserved** — the naturalness benefit of LM-based SE is retained.
- Demos + code promised after acceptance; no numeric tables in the abstract.

## Why This Matters for Hearing AI

### 1. A New Failure Mode Category

Classical SE failures (residual noise, musical artifacts, speech smearing, robotic over-suppression) are **audible** — the listener can tell something is wrong even without a reference. Linguistic hallucination is **inaudible**: the output sounds clean, but the words are wrong. The listener has **no reference signal** to verify against and cannot detect the error.

This is categorically different from every prior failure mode in the speech-enhancement literature. It is structurally identical to text-LLM hallucination: a generative model with a strong prior confidently emitting plausible-but-false outputs.

### 2. The Evaluation-Metric Gap

The hearing-aid evaluation stack — PESQ, STOI, SI-SNR, HASPI — measures **perceptual quality** and **intelligibility**. None of them measure **faithfulness to the words that were actually said**. A hallucinated output can score well on all of them.

Before generative / LM-based SE ships in hearing aids, the field needs to import **hallucination benchmarks** from the text-LLM community: word error rate against ground-truth transcripts, semantic-similarity to source, lexical-preservation metrics. "Word-level fidelity to ground truth" needs to become a first-class audiology metric.

### 3. High-Stakes Communication

Hearing aids are used in safety-critical and legally-consequential contexts: medical instructions, financial decisions, courtroom testimony, family conversations. A device that confidently outputs the wrong words — and the listener has no way to know — is a categorically new product-risk class. Regulators (FDA, EU MDR/AI Act) will need to think about this differently from "speech enhancement quality."

### 4. Architectural Implication for HA Generative SE

Any hearing aid manufacturer pursuing LM-based or generative SE (GAP-URGENet, Richter et al.'s predictive-generative drift decomposition, diffusion-based reconstruction) inherits this hallucination risk. L3-SE's contribution — explicit semantic conditioning during distillation — is a candidate template for keeping the generative path's language prior tied to the actual acoustic content.

## Open Questions / Limitations

- No latency characterization — autoregressive LM-based SE is far from the <10 ms hearing-aid budget. This is currently a research-grade architecture, not a production candidate. The hallucination concern, however, transfers to any LM-based or diffusion-based SE that does enter products.
- Authors did not establish the **measurement methodology for hallucination rate**. The field needs a standard: WER against ground truth? Semantic similarity? Adversarial low-SNR test sets? L3-SE reports reduction but the absolute baseline is fuzzy.
- Demos and code are post-acceptance — the claims are not externally reproducible yet.
- Generalization across languages, accents, and hearing-aid microphone conditioning is unproven.
- Composition with binaural / spatial / target-speaker-extraction pipelines (Lee, Huang, Hsu 2026) is open — adding spatial context might help disambiguate the language prior, or might compound errors.

## Related (in this wiki)
- [[../wiki/concepts/llm-based-speech-enhancement]] — primary home for the LM-based SE paradigm
- [[../wiki/concepts/linguistic-hallucination-speech-enhancement]] — the failure-mode page and the evaluation-metric gap argument
- [[../wiki/concepts/speech-enhancement-neural-networks]] — broader SE architecture context
- [[../wiki/concepts/dnn-in-hearing-aids]] — generative SE is the next branch of this lineage
- [[../wiki/concepts/large-sensor-models]] — LM-based SE is a foundation-model-shaped approach to audio
- [[../wiki/concepts/model-compression]] — compressing an autoregressive LM into a HA budget is the deployment question
- [[../wiki/concepts/on-device-ml-hearing-aids]] — deployment target
- [[../wiki/concepts/eu-ai-act-medical-devices]] — regulatory implications of generative models in SaMD
- [[../wiki/concepts/probabilistic-generative-models-hearing-ai]] — counter-paradigm; Bayesian generative models have explicit likelihoods over content
