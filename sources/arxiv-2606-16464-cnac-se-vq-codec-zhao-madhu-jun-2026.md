---
title: Towards Robust Generative Speech Enhancement Using Vector Quantisation-Based Neural Audio Codec
type: research-paper
date: 2026-06-15
url: https://arxiv.org/abs/2606.16464
authors: [Haixin Zhao, Nilesh Madhu]
arxiv_id: 2606.16464
tags: [speech-enhancement, generative-se, neural-audio-codec, vector-quantisation, latent-space, llm-based-speech-enhancement, dns-mos]
---

# Towards Robust Generative Speech Enhancement Using Vector Quantisation-Based Neural Audio Codec

## Key Extractions

- **Submitted:** 15 Jun 2026 (arXiv:2606.16464)
- **Authors:** Haixin Zhao, Nilesh Madhu
- **Question asked:** Should generative SE inside a VQ-based neural audio codec model the latent as **continuous representations** or **discrete tokens**?
- **Frameworks introduced:**
  - **cNAC-SE** — predicts continuous representations in the codec latent space.
  - **dNAC-SE** — predicts discrete tokens.
- **Headline finding:** Fully fine-tuned cNAC-SE **consistently outperforms all dNAC-SE variants** across diverse test conditions and achieves leading performance among generative SE methods on **DNS-MOS** metrics.
- **Mechanism claim:** The robustness benefit of VQ codec SE comes from **clean-prior-constrained regularisation** induced by the codec's quantiser, **independent of the discretisation itself**. The regularisation effect is transferable to other continuous modelling methods.

## Why This Matters

- The codec-LM paradigm that swept TTS over the last 18 months is now landing in **speech enhancement**, where discriminative ANN/CRN systems still dominate.
- The cNAC > dNAC result is **counter to the prevailing TTS intuition** (where discrete-token modelling has been the default since 2023). It says: for SE, you want the codec's prior, but you don't want to throw away the continuous geometry that the codec's encoder built.
- Pragmatically: this dissolves the "we need a discrete tokeniser to plug into an LM" framing for SE — you can borrow the codec's regularising prior without committing to autoregressive token modelling.
- Cost note: still well outside the **1–3 mW / 512 KB–2 MB** hearing-aid power envelope. Cloud / phone-companion deployment only at present. Relevant for the **companion-phone speech pipeline** path, not on-device.

## Affected Wiki Pages

- [[../wiki/concepts/llm-based-speech-enhancement]] — Add cNAC-SE as the headline 2026-06 codec-prior SE result, with the "VQ provides prior regularisation independent of discretisation" mechanism claim.
- [[../wiki/concepts/speech-enhancement-neural-networks]] — Note as the generative-codec-SE branch counterpoint to the discriminative band-axis (BASENet) and Schrödinger-bridge (SBRF) lines that landed earlier in June.
- [[../wiki/concepts/probabilistic-generative-models-hearing-ai]] — Cross-reference: VQ-codec-as-prior is a probabilistic generative framing, and the cNAC/dNAC comparison is a clean empirical wedge on the continuous-vs-discrete debate.
- [[../wiki/concepts/companion-phone-speech-pipeline]] — Where this kind of model can realistically run for hearing applications until silicon catches up.

## Sources
- [arXiv:2606.16464](https://arxiv.org/abs/2606.16464) — abstract, headline frameworks (cNAC-SE, dNAC-SE), DNS-MOS leading result, and clean-prior-constrained regularisation mechanism claim.
