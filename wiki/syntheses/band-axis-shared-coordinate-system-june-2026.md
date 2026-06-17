---
title: The Band-Axis as a Shared Coordinate System for Hearing AI — June 2026
type: synthesis
created: 2026-06-17
updated: 2026-06-17
sources:
  - biear-meng-2026-arxiv.md
  - arxiv-2606-12662-basenet-band-adapted-se-jun-2026.md
  - arxiv-2606-14120-faconformer-aad-jun-2026.md
related:
  - ../concepts/efferent-moc-feedback-hearing-ai.md
  - ../concepts/speech-enhancement-neural-networks.md
  - ../concepts/auditory-attention-decoding.md
  - ../concepts/dnn-architectures-hearing-aids.md
  - ../concepts/differentiable-cochlear-models.md
  - ../concepts/brain-aligned-speech-foundation-models.md
  - ../concepts/non-intrusive-intelligibility-prediction.md
  - on-chip-hearing-ai-levers-june-2026.md
  - clinical-ml-convergence-june-2026.md
tags: [band-axis, bark-scale, critical-bands, cross-band-attention, speech-enhancement, aad, moc, neuro-steered-hearing, synthesis, june-2026]
---

# The Band-Axis as a Shared Coordinate System for Hearing AI — June 2026

## Observation

Between **June 5 and June 16, 2026** — eleven calendar days — three independent groups, working on three nominally different problems at three different layers of the auditory pipeline, each shipped an arXiv paper whose architectural primitive is **the same operator on the same axis**:

- **Periphery (cochlea):** **BiEAR** — Meng, Ambikairajah, Sethu, Zhang, Li (UNSW Sydney + NUS / CUHK Shenzhen), arXiv:2606.06795, **Jun 5 2026**. MOC-style learned controller adaptively modulates **per-band** binaural filterbank selectivity at inference. Filterbank is split along an auditory critical-band axis; the controller emits a low-rate gain modulation per band.
- **Speech enhancement mid-stage:** **BASENet** — Martins Gomes & Capman, arXiv:2606.12662, **Jun 10 2026**. **Bark-scale critical-band partition**, scaled-capacity encoder per band, **linear-complexity cross-band attention** over frequency-pooled per-band representations. 3.55 PESQ / ~96% STOI / 0.83 M params / 7.3 GMACs on VoiceBank+DEMAND; causal variant (3.44 PESQ) surpasses several non-causal baselines.
- **Cortex (EEG):** **FAConformer** — Wang, He, Jia, Wang & Wu (Huazhong U Sci & Tech), arXiv:2606.14120, **Jun 12 2026**. EEG decomposed into bands; each band gets an independent CNN-Transformer encoder; a **Frequency-Aware Attention** module treats band-wise features as tokens and learns inter-band dependencies. +4.9% over the strongest of 12 AAD baselines.

## The Common Architectural Move

> **Split signal along a perceptually-grounded frequency-band axis; encode each band with its own branch; then mix bands with cross-band attention.**

Same axis (Bark / critical bands / EEG canonical bands — all variants of "what the ear and the cortex already group by"). Same operator (cross-band attention as the inter-band mixing primitive). Three different layers of the auditory pipeline. Eleven days.

## Why This Coincidence Is Not a Coincidence

The band axis has been the right inductive bias for hearing all along. What changed in 2026 is that the **operator** that lets you usefully mix bands at deployable cost finally arrived:

- **Linear-complexity attention over per-band tokens** (BASENet) makes the inter-band mixing cheap enough to run on a CRN-family SE backbone in a 0.83 M / 7.3 GMACs envelope.
- **Per-band branches feeding a Frequency-Aware Attention layer** (FAConformer) makes the same primitive work on EEG without blowing the AAD compute budget.
- **A learned controller modulating per-band gain at inference** (BiEAR) makes the same band primitive appear at the very front of the pipeline, not just inside the enhancement stage.

Together they argue that **the band axis is becoming a shared coordinate system across the hearing-AI stack** — periphery, enhancement, cortex — using the same operator at each layer.

## What This Implies for Hearing AI

### A unified band-axis control bus is now plausible
If every stage of the pipeline now speaks the same band axis, the natural next move is to expose a **band-axis control bus** end-to-end: cortex-side attention decoded into a band-axis weighting (FAConformer-style), passed through the SE stage (BASENet-style), down to the periphery filterbank (BiEAR-style). The interfaces line up.

### Compute structure matches HA silicon
Modern hearing-aid DSP / NPU already natively operates on per-band representations (1/3-octave, ERB, Bark filterbanks). Cross-band attention over a small number of bands (~20–30) is cheap. The three-paper triangle aligns the **ML primitive** with what the chip already does.

### Personalisation along the band axis
The audiogram is a band-axis object. The fitting prescription is a band-axis object. Dead regions and broadened auditory filters are band-axis objects. A band-axis-native ML stack lets per-listener personalisation route through the same primitive the audiologist already uses.

## Unbuilt Piece

> **A unified band-axis control bus and an end-to-end demonstration linking the three modules — periphery (BiEAR), SE (BASENet), cortex (FAConformer) — through a common per-band representation. HASPI / STOI / HASQI are not yet band-conditioned for benchmark scoring.**

The synthesis-as-architecture move is concrete: pick a shared Bark-scale partition; expose a per-band weighting as an explicit hidden state; let each module read from and write to it. The benchmark-as-metric move is the band-conditioned perceptual loss: HASPI / STOI / HASQI scored per band, so that ML losses can flow gradients down to where the band axis actually carries hearing-relevant information.

Neither piece is built. Both are within the reach of any one of the three labs above.

## Related Wiki Pages
- [[../concepts/efferent-moc-feedback-hearing-ai]] — periphery-side band-axis controller (BiEAR)
- [[../concepts/speech-enhancement-neural-networks]] — SE mid-stage container; BASENet is the new band-adapted entry
- [[../concepts/auditory-attention-decoding]] — cortex-side band-axis (FAConformer)
- [[../concepts/dnn-architectures-hearing-aids]] — backbone family taxonomy
- [[../concepts/differentiable-cochlear-models]] — adjacent: afferent forward cochlear model (DAL); the band-axis is the natural ML interface to plug DAL into
- [[../concepts/brain-aligned-speech-foundation-models]] — adjacent: band-axis layer-routing inside speech FMs
- [[../concepts/non-intrusive-intelligibility-prediction]] — band-conditioned HASPI / STOI / HASQI are the unbuilt benchmark piece this synthesis names
- [[on-chip-hearing-ai-levers-june-2026]] — adjacent June 2026 synthesis on the chip levers
- [[clinical-ml-convergence-june-2026]] — adjacent June 2026 synthesis on construct-stack convergence

## Sources
- [BiEAR (arXiv:2606.06795, Jun 5 2026)](../../sources/biear-meng-2026-arxiv.md) — periphery-side cross-band controller
- [BASENet (arXiv:2606.12662, Jun 10 2026)](../../sources/arxiv-2606-12662-basenet-band-adapted-se-jun-2026.md) — SE-stage band-adapted network with linear-complexity cross-band attention
- [FAConformer (arXiv:2606.14120, Jun 12 2026)](../../sources/arxiv-2606-14120-faconformer-aad-jun-2026.md) — cortex-side band-axis with Frequency-Aware Attention
