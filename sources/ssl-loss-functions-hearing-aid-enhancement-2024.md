---
title: "Using Speech Foundational Models in Loss Functions for Hearing Aid Speech Enhancement"
type: academic-paper
date_published: 2024-07-01
date_ingested: 2026-04-15
url: https://arxiv.org/html/2407.13333v1
tags: [speech-enhancement, self-supervised-learning, hearing-aids, loss-functions, clarity-challenge]
---

# Speech Foundation Models as Loss Functions for Hearing Aid Enhancement

## Summary

Uses self-supervised speech representation models as loss functions for training hearing aid speech enhancement networks. Funded by UK CDT in Speech and Language Technologies, EPSRC Clarity Project, WS Audiology, and Toshiba.

## Key Contributions

- Novel approach: instead of using foundation model features as inputs, use them in the loss function during training
- Perceptually-motivated training objective that aligns with hearing-impaired intelligibility
- Connected to the Clarity Challenge ecosystem for hearing aid speech enhancement benchmarking
- Industry backing from WS Audiology and Toshiba

## Significance

Traditional loss functions (MSE, SI-SNR) don't correlate well with perceived speech quality for hearing-impaired listeners. Using self-supervised representations in the loss function may produce enhancement models that better match perceptual quality, bridging the gap between objective metrics and subjective listening experience.
