---
title: Your U-Net Dereverberation Model is Secretly an RIR Encoder
type: source
date: 2026-06-08
ingested: 2026-06-10
authors: [Sina Khanagha, Timo Gerkmann]
publication: arXiv:2606.09557 (eess.AS), accepted Interspeech 2026
url: https://arxiv.org/abs/2606.09557
institution: Universität Hamburg, Signal Processing Group
tags: [dereverberation, room-impulse-response, rir-encoder, u-net, diffusion-se, contrastive-learning, interspeech-2026, hearing-aids, implicit-representations, speech-enhancement]
---

# Your U-Net Dereverberation Model is Secretly an RIR Encoder

## Metadata
- **Title:** Your U-Net Dereverberation Model is Secretly an RIR Encoder
- **Authors:** Sina Khanagha, Timo Gerkmann (Universität Hamburg, Signal Processing Group)
- **arXiv:** 2606.09557 (cs.SD / eess.AS)
- **Posted:** June 8, 2026
- **Accepted:** Interspeech 2026
- **Code:** Pending Interspeech-camera-ready (typical Gerkmann-group practice; UHH SP-G releases reference implementations)

## Method
- Probes both **diffusion-based** and **discriminative** U-Net architectures trained for audio dereverberation.
- Empirically demonstrates that the **deeper layers of the U-Net encode structured Room Impulse Response (RIR)-dependent embeddings**, even though the networks were never explicitly told to estimate the RIR.
- Quality of the implicit RIR representation (measured via probe regression onto known RIR characteristics) **correlates with downstream dereverberation performance** — better implicit RIR encoding → better dereverb output.
- Builds on this finding with an explicit conditioning strategy:
  - Train an **RIR embedding encoder via self-supervised contrastive learning** (positive pairs from same room, negatives from different rooms).
  - Condition the U-Net dereverberation network on these pretrained RIR embeddings.
- Reports:
  - **Faster convergence** during training
  - **Better dereverberation quality** on standard metrics
  - **Significantly fewer reverse diffusion steps required at inference** — a latency improvement that maps directly onto hearing-aid deployment constraints

## Why It Matters for Hearing AI

### Reverberation is a top-3 wearer complaint
- Speech-in-noise, own-voice, and reverberation dominate the perceptual issues reported by hearing-aid wearers.
- For ~30 years the dominant dereverberation approach has been **blind**: noisy reverberant signal in, cleaner signal out, with the room characteristics absorbed silently into network weights.
- This paper says: the network was learning to estimate the room all along. The architectural opportunity is to extract that estimate, share it across modules, and condition downstream stages on it.

### Room embedding as a first-class on-chip object
- Small, low-rate, shareable across speech enhancement, scene classification, beamforming, and own-voice detection.
- One representation, many consumers — exactly the kind of architecture that favors hearing-aid power-budgeted DSP/NPU silicon.

### Two complementary axes for inference-step reduction
- **SB-RF (arXiv:2606.05575, June 4, 2026)** cuts inference steps by replacing the ODE with a Schrödinger-Bridge / Rectified-Flow geodesic.
- **RIR-conditioning (this paper, June 8, 2026)** cuts inference steps by giving the network the answer to a question it was solving implicitly.
- These are **complementary, not competing** — could stack.

### Frequent-room prior
- Hearing-aid wearers spend 80%+ of their time in a small set of "frequent rooms" (kitchen, office, car, bedroom, a few friends' apartments). A per-wearer RIR library + room-recognition + room-conditioned dereverb is structurally cheap and clinically meaningful.
- No product on the market currently does this.

### Open piece — benchmark gap
- HASPI / STOI / Clarity Prediction Challenge (CPC1/2/3) do not directly score "RIR-aware processing." A room-conditioned hearing-aid SE benchmark is unwritten.
- Likely Clarity Project / Interspeech challenge candidate for 2027.

## Cross-References
- Related concept: `room-aware-dereverberation.md` (new)
- Related concept: `speech-enhancement-neural-networks.md` (add this paper)
- Related source: `arxiv-2606-05575-sbrf-schrodinger-bridge-jun-2026.md` (sibling axis)
- Related concept: `differentiable-cochlear-models.md` (different forward-path approach; DAL vs RIR-conditioning is forward-model vs explicit-room)
- Related concept: `implicit-representations-speech-models.md` (new candidate concept page; this paper + Whisper-ECoG, June 3, both make the same "deep layers know more than the loss asked for" point)
