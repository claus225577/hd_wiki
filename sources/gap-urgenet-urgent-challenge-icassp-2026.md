---
title: "GAP-URGENet: 1st Place URGENT 2026 Challenge (ICASSP 2026)"
type: paper
date: 2026-04-08
url: https://arxiv.org/abs/2604.01832
tags: [speech-enhancement, universal, generative-predictive, icassp-2026, challenge-winner, urgent]
---

# GAP-URGENet: 1st Place URGENT 2026 Challenge (ICASSP 2026)

**arXiv:** 2604.01832

## Key Findings

- **Won 1st place** in the URGENT 2026 Challenge at ICASSP 2026
- URGENT = Universal speech Restoration with Generative approaches
- Proposes GAP-URGENet: a **generative-predictive fusion framework** for universal speech enhancement
- "Universal" means handling multiple degradation types simultaneously: noise, reverberation, bandwidth limitation, clipping, codec artifacts
- Fusion of generative and predictive approaches combines:
  - **Predictive path:** Direct mask/mapping estimation (fast, reliable, but limited by input quality)
  - **Generative path:** Diffusion/flow-based speech reconstruction (higher quality ceiling, but slower and potentially hallucinating)
  - **Fusion:** Combines both paths to get reliability of predictive with quality of generative

## Significance for Hearing AI

- **Universal enhancement is the hearing aid goal:** Hearing aids face all degradation types simultaneously — noise, reverb, bandwidth limitations of tiny speakers, mic artifacts. A universal framework aligns with real-world hearing aid needs.
- **Generative-predictive fusion addresses a key tradeoff:** Pure predictive models (current hearing aid DNNs) are reliable but limited; pure generative models risk hallucination. Fusion could offer a practical middle ground.
- **ICASSP challenge winner = state of the art:** URGENT challenge results establish the current performance ceiling for universal speech enhancement
- **Potential for CI applications:** CI users face especially severe degradation (20 spectral channels); generative reconstruction could potentially fill in missing spectral detail
- Architectural inspiration for next-gen hearing aid models, though significant compression would be needed for on-device deployment
