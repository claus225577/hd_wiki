---
title: "Effects of low-latency deep-learning-based noise reduction on speech intelligibility"
type: academic-paper
date_published: 2026-01-01
date_ingested: 2026-04-15
journal: Frontiers in Audiology and Otology
url: https://www.frontiersin.org/journals/audiology-and-otology/articles/10.3389/fauot.2025.1746635/full
tags: [deep-learning, noise-reduction, speech-intelligibility, hearing-aids, low-latency]
---

# Low-Latency DNN Noise Reduction and Speech Intelligibility

## Summary

Investigates effects of low-latency deep-learning-based noise reduction on measured and predicted speech intelligibility in noise. Uses a pre-trained convolutional single-channel time-domain audio separation network achieving ultra-low latency of 1 ms.

## Key Findings

- Ultra-low latency: 1 ms algorithmic latency using convolutional time-domain network
- Tested on both normal-hearing listeners, hearing-impaired listeners, and cochlear implant users
- Evaluated measured vs. predicted intelligibility — important for validating prediction models
- Demonstrates that DNN-based noise reduction can work within hearing aid latency constraints

## Significance

Hearing aids have strict latency requirements (~6-10 ms total) to avoid the "comb filter" effect when direct and processed sound arrive at different times. Achieving 1 ms algorithmic latency leaves headroom for the full signal processing chain. This study validates that ultra-low-latency DNN approaches don't sacrifice intelligibility gains.
