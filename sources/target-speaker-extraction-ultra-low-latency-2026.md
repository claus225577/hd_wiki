---
title: "Target Speaker Extraction with Ultra-Low Latency for Hearing Assistive Devices"
authors: Hsu et al.
source: arXiv eess.AS
date: 2026-04-25
ingested: 2026-04-25
tags: [target-speaker-extraction, speaker-embedding, hearing-assistive, ultra-low-latency, causal]
---

# Target Speaker Extraction with Ultra-Low Latency for Hearing Assistive Devices

## Key Claims
- Sub-5ms causal target speaker extraction using speaker embeddings
- Designed specifically for hearing assistive devices (hearing aids, cochlear implants)
- Uses a speaker embedding to identify and extract the target speaker from a multi-talker mixture
- Causal architecture — no future lookahead, compatible with real-time processing constraints
- Latency under 5ms — well within the <10ms threshold for hearing aid perceptibility

## Significance for Hearing AI
- **Target speaker extraction (TSE)** is distinct from general speech enhancement: instead of enhancing "all speech" or suppressing "all noise," it extracts a specific speaker identified by a pre-enrolled embedding
- This enables **personalized listening**: the hearing aid knows who the user wants to hear, not just that speech is present
- Sub-5ms latency makes this feasible for real-time hearing aid deployment — most prior TSE systems operated at higher latency
- Connects to auditory attention decoding: TSE could be steered by EEG-based attention signals rather than manual selection
- Speaker embeddings could be enrolled via companion app (spouse's voice, caregiver, etc.)

## Technical Approach
- Causal neural network architecture (details from paper)
- Speaker embedding acts as a conditioning signal — tells the model which speaker to extract
- Optimized for compute constraints typical of hearing aid hardware
- Sub-5ms achieved through careful architecture design for minimal receptive field

## Relevance to Wiki
- Extends [[speech-enhancement-neural-networks]] with TSE as a specialized enhancement task
- Connects to [[auditory-attention-decoding]] — TSE + AAD could enable brain-steered speaker selection
- Relevant to [[on-device-ml-hearing-aids]] — sub-5ms latency on hearing aid hardware
- Relevant to [[cochlear-implant-ai]] — hearing assistive devices includes CI
