---
title: Low-Latency DNN Noise Reduction for NH, HI, and CI Users
type: paper
date: 2025-01-01
url: https://www.frontiersin.org/journals/audiology-and-otology/articles/10.3389/fauot.2025.1746635/full
tags: [dnn, noise-reduction, cochlear-implant, low-latency, RNN, SepFormer]
---

# Low-Latency DNN Noise Reduction for NH, HI, and CI Users

## Key Extractions
- Ultra-low latency target: 1ms end-to-end DNN noise reduction
- First study to assess ultra-low latency DNN noise reduction across all three listener groups: normal hearing (NH), hearing impaired (HI), and cochlear implant (CI)
- Time-domain DNN algorithm — operates directly on waveform rather than spectral features
- Architectures evaluated: RNN and SepFormer
- Custom training dataset of approximately 30 hours
- 13 CI listeners included in the evaluation
- Ultra-low latency is critical for CI users due to interaction with device processing delays and potential for temporal distortion
- SepFormer showed strong separation performance but RNN more amenable to latency constraints

## Relevance
The 1ms latency target is a landmark constraint — CI users are especially sensitive to processing delays. This study bridges the gap between NH/HI hearing aid research and CI-specific needs, informing unified DNN pipeline design.
