---
title: "Effects of low-latency deep-learning-based noise reduction on speech intelligibility"
authors: Schulz et al.
type: academic-paper
date_published: 2026-01-06
date_ingested: 2026-04-15
journal: Frontiers in Audiology and Otology
url: https://www.frontiersin.org/journals/audiology-and-otology/articles/10.3389/fauot.2025.1746635/full
tags: [deep-learning, noise-reduction, speech-intelligibility, hearing-aids, low-latency, conv-tasnet, cochlear-implant]
---

# Low-Latency DNN Noise Reduction and Speech Intelligibility

## Summary

Investigates effects of low-latency deep-learning-based noise reduction on measured and predicted speech intelligibility in noise. Uses a pre-trained convolutional single-channel time-domain audio separation network achieving ultra-low latency of 1 ms.

## Key Findings

- **Architecture:** Conv-TasNet (Convolutional Time-domain Audio Separation Network) with 1 ms algorithmic latency
- Tested on three listener groups: normal-hearing, hearing-impaired, and cochlear implant users
- **CI users gained 5.7 dB** SNR improvement — the largest benefit across groups
- **Hearing-impaired listeners gained 0.8 dB** — modest but positive
- **Normal-hearing listeners slightly degraded** — DNN processing may interfere with already-good perception
- **Key insight:** Benefit correlates inversely with baseline deficit — listeners with worse baseline hearing benefit most from DNN noise reduction
- Evaluated both measured and predicted intelligibility — important for validating prediction models

## Significance

Hearing aids have strict latency requirements (~6-10 ms total) to avoid the "comb filter" effect when direct and processed sound arrive at different times. Achieving 1 ms algorithmic latency leaves headroom for the full signal processing chain. This study validates that ultra-low-latency DNN approaches don't sacrifice intelligibility gains.

The 5.7 dB CI benefit is particularly significant — cochlear implant users have the most degraded baseline perception and stand to gain the most from DNN noise reduction. The inverse correlation between baseline ability and DNN benefit has implications for product targeting: DNN noise reduction should be prioritized for severe hearing loss and CI users, where it delivers the largest absolute improvement.
