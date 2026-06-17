---
title: "BASENet: Band-Adapted Speech Enhancement Network with Cross-Band Attention"
type: source
source_type: arxiv-paper
arxiv_id: 2606.12662
authors: [Damien Martins Gomes, François Capman]
affiliations: [Thales (likely; Capman group)]
date_published: 2026-06-10
ingested: 2026-06-17
url: https://arxiv.org/abs/2606.12662
tags: [speech-enhancement, band-adapted, bark-scale, critical-bands, cross-band-attention, convolutional-recurrent-network, inverted-residual, dense-connectivity, voicebank-demand, causal-streaming, hearing-aid-latency, interspeech-likely]
---

# BASENet — Band-Adapted Speech Enhancement Network (Martins Gomes & Capman, June 2026)

## Bibliographic
- **Authors:** Damien Martins Gomes, François Capman
- **Posted:** 10 June 2026 (arXiv:2606.12662)
- **URL:** https://arxiv.org/abs/2606.12662

## Problem
Production-deployable speech enhancement (SE) lives under a small parameter and MAC budget. The dominant CRN-family backbone (CNN spatial + RNN temporal) treats frequency as a flat axis at the input, then learns whatever band structure emerges. This wastes capacity in three places: (i) all bands get equal encoder capacity even though Bark-scale critical-band density is far from uniform, (ii) inter-band dependencies are forced through generic self-attention or fully-connected mixing, which scales quadratically and is expensive at low compute budgets, and (iii) the back-end has to recover band structure that was thrown away at the front.

## Contribution
BASENet is a CRN-family SE network with an explicit **band-axis inductive bias**:

1. **Bark-scale critical-band partition.** The input spectrum is split along the Bark scale, the same critical-band partition the auditory periphery uses.
2. **Scaled-capacity per-band encoder.** Each band gets its own encoder; the per-band capacity is **scaled by the critical-band density** so that perceptually salient bands receive more parameters than bands the ear under-uses.
3. **Cross-band attention with linear complexity.** Inter-band dependencies are modelled via attention over **frequency-pooled representations**, not over the full TF grid — this is the linear-complexity move that makes cross-band attention deployable.
4. **Block stack.** Inverted residual blocks + dense connectivity + a convolutional recurrent network. The residual / dense structure is the standard efficient-CNN toolkit; the CRN backbone is the standard low-latency SE choice.

## Headline Numbers (VoiceBank+DEMAND)
- **PESQ: 3.55**
- **STOI: ~96%**
- **Parameters: 0.83 M**
- **Compute: 7.3 GMACs**

## Causal / Streaming Variant
A **causal** variant achieves **PESQ 3.44**, surpassing several non-causal baselines. This is the deployment-critical number — non-causal SE cannot ship into a hearing aid or streaming pipeline. A causal architecture that beats non-causal baselines means the band-axis prior is providing real signal, not just being subsidised by a look-ahead window.

## Why It Matters for Hearing AI

### 1. Band-axis as a deployable inductive bias
Hearing-aid silicon already runs on a perceptual scale (1/3-octave, Bark, ERB). BASENet's Bark-scale partition is **the same band axis the cochlea, the audiogram, and the fitting prescription already use** — it is not introducing a new structural primitive, it is matching the one the device stack natively speaks.

### 2. Linear-complexity cross-band attention is the operator
Cross-band attention is fast becoming the shared operator across the **band-axis triangle**:
- **Periphery** — BiEAR (Meng et al., arXiv:2606.06795, Jun 5 2026): MOC-style controller adaptively modulates per-band filter selectivity.
- **SE mid-stage** — BASENet (this paper, Jun 10 2026): linear-complexity cross-band attention over Bark-scale critical bands.
- **Cortex** — FAConformer (Wang et al., arXiv:2606.14120, Jun 12 2026): per-band CNN-Transformer branches + cross-band Frequency-Aware Attention for AAD.

Three independent groups, three different layers of the auditory pipeline, **eleven days**, **same operator (cross-band attention) on the same axis (perceptual critical bands)**.

### 3. Parameter / compute envelope is in the HA / hearable range
0.83 M params and 7.3 GMACs is materially below the operating point of typical Transformer SE baselines. Combined with the causal-variant PESQ result, this puts BASENet in plausible reach of a hearing-aid co-processor or hearable NPU.

## Limits / Open Questions
- VoiceBank+DEMAND is the standard SE benchmark but is not a hearing-aid benchmark. **HASPI / STOI / HASQI in band-conditioned form are not reported.** The band-axis architecture should be a natural fit for band-conditioned perceptual losses; the paper doesn't pursue that.
- The Bark partition is fixed by acoustics, not learned. Whether a learned partition (or a hearing-loss-personalised partition) outperforms Bark is open.
- No multi-channel / binaural variant reported.
- Hearing-impaired listeners have **dead regions** and **broadened auditory filters** — the optimal per-band capacity allocation almost certainly differs from the normal-hearing Bark prior. BASENet is a normal-hearing parameterisation by default.

## Related Wiki Pages
- [[../wiki/concepts/speech-enhancement-neural-networks.md]] — primary concept; BASENet is the band-adapted entry in the CRN-family taxonomy
- [[../wiki/concepts/efferent-moc-feedback-hearing-ai.md]] — periphery-side band-axis counterpart
- [[../wiki/concepts/auditory-attention-decoding.md]] — cortex-side band-axis counterpart (FAConformer)
- [[../wiki/concepts/dnn-architectures-hearing-aids.md]] — CRN backbone in HA context

## Related Sources
- [BiEAR (arXiv:2606.06795)](biear-meng-2026-arxiv.md) — periphery-side band-axis paper
- [FAConformer (arXiv:2606.14120)](arxiv-2606-14120-faconformer-aad-jun-2026.md) — cortex-side band-axis paper
