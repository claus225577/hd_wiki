---
title: LM-Based Speech Enhancement
type: concept
created: 2026-05-14
updated: 2026-06-17
sources: [l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md, arxiv-2606-16464-cnac-se-vq-codec-zhao-madhu-jun-2026.md]
related: [speech-enhancement-neural-networks.md, linguistic-hallucination-speech-enhancement.md, dnn-in-hearing-aids.md, dnn-architectures-hearing-aids.md, large-sensor-models.md, model-compression.md, on-device-ml-hearing-aids.md, probabilistic-generative-models-hearing-ai.md, eu-ai-act-medical-devices.md, audio-reasoning-chain-of-thought.md, companion-phone-speech-pipeline.md]
tags: [llm-based-se, language-models, generative-se, autoregressive, neural-codec, wavlm, acoustic-semantic-distillation, foundation-models, speech-enhancement, vector-quantisation]
last_change: 2026-06-17 — added cNAC-SE / dNAC-SE (Zhao & Madhu, arXiv:2606.16464). The headline result — fully fine-tuned continuous-latent cNAC-SE consistently outperforms discrete-token dNAC-SE variants on DNS-MOS — and the underlying mechanism claim — VQ's robustness benefit comes from *clean-prior-constrained regularisation*, independent of the discretisation itself — together split the codec-prior axis from the discrete-token axis on this page for the first time.
---

# LM-Based Speech Enhancement

A class of speech enhancement systems that treats denoising as a **language modeling** problem: discretize speech into tokens, then use a decoder-only autoregressive LM to predict the clean-speech token sequence conditioned on the noisy input. Structurally a sibling of text-LLMs and audio-LLMs (Whisper, VALL-E, AudioLM) — not a spectral mask network.

This is a **structurally different paradigm** from the CRN / Transformer / Mamba mask-prediction lineage covered in [[speech-enhancement-neural-networks]]. The defining feature is the **autoregressive language prior** over speech tokens — and that prior is also the source of LM-based SE's distinctive failure mode (see [[linguistic-hallucination-speech-enhancement]]).

## Core Architecture

A typical LM-based SE system has three stages:

1. **Codec / tokenizer** — encodes the audio (noisy input, clean reference) into discrete tokens. Often built on self-supervised encoders such as WavLM, HuBERT, or wav2vec 2.0, or on neural audio codecs (EnCodec, SoundStream).
2. **Conditioning encoder** — extracts a representation of the noisy input that the LM will be conditioned on. May produce acoustic features, semantic features, or a fusion of both.
3. **Decoder-only autoregressive LM** — predicts the next clean-speech token, autoregressively, conditioned on the encoder output. The same architectural family as GPT-style text LMs and Whisper-style audio LMs.

The LM is trained on paired noisy → clean speech with next-token prediction loss. After training, it generates clean-speech tokens; a vocoder or codec decoder converts those back to waveform.

## Why LM-Based SE Exists

- **Naturalness.** Mask-based SE removes noise from a noisy signal — phase artifacts, smearing, and residual roughness remain. LM-based SE *synthesizes* clean speech from a prior, so the output sounds inherently natural.
- **Strong language prior.** The LM has absorbed phonotactic, lexical, and syntactic structure during training. Under moderate noise this prior fills in missing acoustic detail — a denoising version of what text-LLMs do for missing tokens.
- **Universal degradation handling.** A single autoregressive LM can in principle handle noise, reverberation, bandwidth limitation, codec artifacts, and clipping with the same machinery — similar to how the URGENT 2026 universal-enhancement framing motivated GAP-URGENet (mask-based but generative-fusion).
- **Unifies SE with the foundation-model trajectory.** As speech foundation models scale (Parakeet, Whisper, AudioLM), SE becomes a downstream application of the same backbone rather than a separate engineering discipline. See [[large-sensor-models]] for the broader cross-modal trend.

## L3-SE (Wang et al., May 2026) — Acoustic-Semantic Distillation

The May 2026 L3-SE paper (arXiv:2605.08608) is the most prominent recent contribution and the anchor source for this page. Its specific architectural innovations:

- **Noise-invariant conditioning encoder** trained with **dual distillation targets** — an acoustic teacher and a semantic teacher — so the encoder representation preserves both phonetic detail and lexical content under severe noise.
- **High-fidelity codec with learnable weighted WavLM-layer representations** — different WavLM layers encode different aspects of speech (lower layers more acoustic, higher layers more semantic); learned per-layer weights let the codec keep the lexically-discriminative information that a pure acoustic codec would discard.
- **Decoder-only autoregressive LM** conditioned on the fused acoustic-semantic features.

Reported result: substantial reduction in **linguistic hallucinations** with perceptual quality preserved, with the largest gains in low-SNR and reverberant conditions. See the [[linguistic-hallucination-speech-enhancement]] page for the failure-mode argument that motivated this design.

## cNAC-SE / dNAC-SE (Zhao & Madhu, Jun 2026) — Codec Prior Without Discretisation

The June 2026 Zhao & Madhu paper (arXiv:2606.16464) asks a question the L3-SE / VALL-E lineage implicitly answered with "discrete tokens": *does generative SE inside a VQ-based neural audio codec actually need the discretisation, or only the codec's prior?*

- **Two frameworks compared head-to-head on the same codec backbone:**
  - **cNAC-SE** predicts **continuous representations** in the codec latent space.
  - **dNAC-SE** predicts **discrete tokens** (the standard codec-LM framing).
- **Headline result:** fully fine-tuned cNAC-SE **consistently outperforms all dNAC-SE variants** across diverse test conditions, and achieves leading performance among generative SE methods on **DNS-MOS**.
- **Mechanism claim (the part that matters for the field):** the robustness benefit of VQ codec SE comes from **clean-prior-constrained regularisation** induced by the quantiser — and this regularisation effect is **transferable to other continuous modelling methods**, independent of whether discretisation actually happens at inference.

Taken at face value this **splits two axes** that have been conflated in the LM-based SE literature for the last 18 months: (a) "use a codec-derived prior" and (b) "predict discrete tokens autoregressively". The Zhao & Madhu result says (a) is doing most of the work, and (b) may be costing you continuous-geometry information without paying you back. If it generalises, it's an argument that the most productive direction is *non-autoregressive continuous-latent SE with a quantiser-shaped prior* — not the autoregressive token LM that L3-SE and the broader codec-LM lineage assumed.

Hearing-aid relevance is indirect for now — model still well outside the 1–3 mW envelope — but the framing matters: a non-autoregressive continuous-latent generative SE removes the **sequential token-decoding latency floor** that has been the single biggest blocker for any on-ear deployment of LM-based SE. See [[companion-phone-speech-pipeline]] for the realistic deployment path on a 12–24 month horizon.

## Relationship to Other SE Paradigms

| Paradigm | Mechanism | Failure mode under severe noise |
|---|---|---|
| Mask-based DNN (CRN, FullSubNet) | Predict T-F mask, apply to noisy input | Speech smearing, robotic over-suppression, musical artifacts |
| Generative-predictive fusion (GAP-URGENet, Richter drift decomp.) | Mask + diffusion refinement | Lower over-suppression; some risk of generative drift |
| Diffusion / flow-based reconstruction | Iterative denoising of a generative prior | Possible generative hallucination, expensive inference |
| **LM-based (L3-SE, autoregressive token LMs)** | Autoregressive generation under a language prior | **Linguistic hallucination** — confidently wrong words |
| Probabilistic generative (AIDA-2) | Bayesian factor graph; explicit likelihoods | Limited scale; tied to Wiener-baseline quality so far |

LM-based SE sits at the most "generative" end of the spectrum — most natural output, strongest language prior, and the most novel failure mode.

## Hearing-Aid Deployment Considerations

LM-based SE is currently **far from a hearing-aid latency budget**. Autoregressive generation requires token-by-token inference; even with small models and aggressive caching, latency is dominated by sequential decoding, not by per-token compute. Hearing aids require <10 ms algorithmic latency end-to-end; current LM-based SE systems are research-grade and orders of magnitude above that.

That said, the **deployment pressure** is real:
- Smartphone-side audio processing already runs on-device speech LMs (Whisper variants, Gemma 3n audio). The "phone does the LM, hearing aid streams the cleaned audio back" architecture is technically buildable today; the latency budget for this hybrid is a separate research question.
- As model compression and on-chip NPU compute scale (see [[model-compression]], [[on-device-ml-hearing-aids]]), small autoregressive LMs running on hearing-aid SoCs become plausible on a 3-5 year horizon.
- The hallucination question (see below) needs to be solved **before** deployment, not after — once a generative SE system is on a user's ear, there is no way for the user to know when it is wrong.

## The Hallucination Question (Cross-Link)

LM-based SE inherits the failure mode that defines text-LLMs: **confident generation of plausible-but-false outputs under uncertainty**. In speech enhancement this manifests as words the speaker never said being inserted into the listener's audio. Because the output sounds natural and the listener has no reference signal, the error is undetectable from the listener's perspective.

This is the central concern for hearing-aid applications of LM-based SE. See [[linguistic-hallucination-speech-enhancement]] for the full treatment, including:
- Why current SE metrics (PESQ, STOI, HASPI, SI-SNR) do not detect hallucination
- What evaluation infrastructure needs to be imported from the text-LLM community
- Why faithfulness/factuality needs to become a first-class audiology metric
- Regulatory and safety implications

## Open Questions

- **Latency floor.** What is the theoretically minimal latency for token-level autoregressive SE? Can speculative decoding, parallel decoding, or non-autoregressive variants close the gap to <10 ms?
- **Hallucination measurement methodology.** WER against ground truth? Semantic similarity? Adversarial low-SNR benchmark sets? The field has no standard yet — L3-SE reports reduction but not on a shared benchmark.
- **Composition with spatial / target-speaker pipelines.** Can L3-SE plug into binaural processing, target-speaker extraction (Hsu et al. 2026), or neural directional filtering (Huang/NDF+ 2026)? Does spatial context help anchor the language prior, or compound errors?
- **Multilingual generalization.** A WavLM-conditioned LM trained primarily on English will have a strong English-language prior. Behavior on under-represented languages and accents is an open question with equity implications.
- **Hearing-impaired-listener evaluation.** Current SE evaluation is dominated by normal-hearing listeners and objective metrics. LM-based SE needs HI-listener subjective evaluation with explicit attention to lexical fidelity.

## Related Pages
- [[linguistic-hallucination-speech-enhancement]] — the failure-mode page; central concern for any HA deployment of LM-based SE
- [[speech-enhancement-neural-networks]] — broader SE architecture catalog; LM-based SE is structurally distinct
- [[dnn-in-hearing-aids]] — production SE lineage that LM-based SE branches from
- [[dnn-architectures-hearing-aids]] — architectural survey context
- [[large-sensor-models]] — LM-based SE is a foundation-model-shaped approach
- [[model-compression]] — compressing autoregressive LMs into HA budgets
- [[on-device-ml-hearing-aids]] — deployment target
- [[probabilistic-generative-models-hearing-ai]] — counter-paradigm with explicit likelihoods over content
- [[eu-ai-act-medical-devices]] — generative SaMD raises predetermined-change-control questions
- [[audio-reasoning-chain-of-thought]] — audio-LLM family; same backbone, different downstream task

## Sources
- [L3-SE — Reducing Linguistic Hallucination in LM-Based Speech Enhancement (Wang et al., May 2026)](../../sources/l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md) — arXiv:2605.08608, noise-invariant acoustic-semantic distillation; anchor source for this page
- [cNAC-SE / dNAC-SE — Robust Generative SE with VQ Neural Audio Codec (Zhao & Madhu, Jun 2026)](../../sources/arxiv-2606-16464-cnac-se-vq-codec-zhao-madhu-jun-2026.md) — arXiv:2606.16464, head-to-head continuous-latent vs discrete-token under the same codec backbone; mechanism claim that VQ's robustness is clean-prior-constrained regularisation, transferable to continuous methods.
