---
title: "Beyond U-Net: A Latent-Representation-Aligned Skip-Free Backbone for Flow-Matching Speech Enhancement"
url: https://arxiv.org/abs/2606.24745
date: 2026-06-23
authors: [Wangyi Pu, Michele Scarpiniti]
arxiv_id: 2606.24745
venue: arXiv eess.AS
type: paper
tags: [speech-enhancement, flow-matching, u-net, skip-connections, foundation-models, descript-audio-codec, generative-se, latent-alignment]
---

# Beyond U-Net: A Latent-Representation-Aligned Skip-Free Backbone for Flow-Matching Speech Enhancement

## Key Extractions

- **Architectural claim:** U-Net skip connections in SE leak noise-correlated low-level features from encoder to decoder. The fix is to delete the skip connections.
- **Replacement mechanism:** Explicit alignment of bottleneck and decoder outputs to clean-speech latent features from a **frozen Descript Audio Codec (DAC)**.
- **Training paradigm:** Flow-matching (generative), not discriminative.
- **Inference budget:** Competitive PESQ with **5 function evaluations (NFE)** — a step-change vs typical 20–50 NFE for flow/diffusion SE.
- **Datasets:** WSJ0-CHiME3 and VoiceBank-DEMAND.
- **Result:** Improved PESQ and perceptual quality vs prior flow-matching baselines.

## Architecture details
- Skip-free backbone (no encoder→decoder skip paths).
- Bottleneck feature aligned to DAC latent of clean speech.
- Decoder output aligned to DAC latent of clean speech.
- DAC is a pretrained foundation audio codec used unchanged (frozen).
- Flow-matching objective trains the trajectory between noisy and clean.

## Why this matters for hearing aids
- The U-Net + skip backbone has been the default SE architecture since ~2018. Most HA SE work is "small U-Net + harder pruning + better distillation." This paper shows a viable non-U-Net path.
- 5 NFE is the new number. Not real-time on a HA SoC today, but bends the curve — generative SE on the ear becomes plausible by the 2028 chip generation, contingent on neural-accelerator support.
- The pattern of using a **frozen foundation model** (Descript Audio Codec) as the training target parallels Sabin et al. (arXiv:2606.26342, 24 Jun 2026), which used a frozen Whisper encoder to predict listener-rated ease of understanding and beat HASPIv2. Domain-specific stacks built when nothing else existed are losing out to frozen foundation models with tiny heads.
- Skip-connection leakage is a candidate explanation for the long-running discriminative-SE "over-suppression vs residual-noise" tradeoff that every audiologist complains about.

## Open questions
- Latency profile on causal (low-look-ahead) HA pipelines is not reported in the paper.
- DAC parameter count + runtime cost is non-trivial — whether the latent target needs to be present at deployment time or only at training time matters for HA chip area budget.
- Generalisation to wider noise distributions (in-the-wild HA scenes) vs the WSJ0-CHiME3 / VoiceBank-DEMAND benchmarks.

## Relevance to existing wiki concepts
- `concepts/speech-enhancement-neural-networks` — architectural shift away from U-Net default.
- `concepts/foundation-model-fusion-speech` — frozen foundation codec as training target; parallel to Sabin et al. Whisper-based listener-rating predictor.
- `concepts/probabilistic-generative-models-hearing-ai` — flow matching with 5 NFE as the latency wedge for generative SE on HAs.
- `concepts/product-level-ha-listener-rated-evaluation` — same "frozen foundation eats vertical-specific stack" pattern.
- `concepts/dnn-architectures-hearing-aids` — backbone architecture inventory update.
