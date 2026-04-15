---
title: "Speech foundation models on intelligibility prediction for hearing-impaired listeners"
type: academic-paper
date_published: 2024-01-01
date_ingested: 2026-04-15
url: https://arxiv.org/html/2401.14289v1
tags: [speech-foundation-models, self-supervised-learning, hearing-impairment, intelligibility-prediction]
---

# Speech Foundation Models for Hearing-Impaired Intelligibility Prediction

## Summary

Evaluates whether large self-supervised speech foundation models (e.g., NVIDIA Parakeet with 600M parameters, trained on 120k hours of English) can predict speech intelligibility for hearing-impaired listeners. Explores using distance between clean and noisy speech representations as an intelligibility metric.

## Key Findings

- Self-supervised speech representations correlate with human intelligibility ratings better than traditional signal-based metrics (e.g., PESQ, STOI)
- Foundation model features capture aspects of speech quality/intelligibility that hearing-impaired listeners perceive
- Non-intrusive prediction possible (no clean reference needed at inference time)

## Significance

Speech foundation models pre-trained on massive datasets may capture perceptual qualities relevant to hearing impairment without being explicitly trained for it. This opens the door to using off-the-shelf foundation models for hearing aid signal processing evaluation, reducing need for expensive listener panels.
