---
title: Standard Audiogram Classification from Loudness Scaling Data — Unsupervised, Supervised, and Explainable ML
type: research-paper
date: 2026-04
journal: International Journal of Audiology (Taylor & Francis)
url: https://www.tandfonline.com/doi/full/10.1080/14992027.2026.2642765
tags: [audiogram, bisgaard, loudness-scaling, acalos, machine-learning, self-fitting, otc-hearing-aids, calibration-independent]
---

# Standard Audiogram Classification from Loudness Scaling Data

## Key Extractions

### Approach
- Investigates whether **adaptive categorical loudness scaling (ACALOS)** data can be used to approximate individual audiograms.
- Frames the problem as classifying listeners into **standard Bisgaard audiogram types** (a small, clinically meaningful target space).
- Compares unsupervised, supervised, and explainable ML approaches.

### Headline Result
- **Logistic Regression** emerged as the most effective model among supervised approaches.
- ACALOS data carries enough signal to recover Bisgaard archetypes without the calibrated audiometric setup typically required for pure-tone audiometry.

### Why Bisgaard Archetypes Matter
- Bisgaard standard audiograms are a discrete, well-validated set of canonical hearing-loss profiles widely used in hearing-aid fitting research and prescriptive formulae.
- Mapping a listener to a Bisgaard type is a usable bridge to first-fit gain prescription.

## Relevance
- A practical path toward **calibration-independent self-fitting** in OTC and consumer hearing devices: replace pure-tone thresholds with a brief loudness-scaling task.
- Aligns with a broader pattern in 2025–2026 audiology ML — using interpretable, low-dimensional output spaces (Bisgaard types, audiometric configurations) instead of free-form regression on every frequency.
- Connects directly to OTC self-fitting requirements under FDA's October-2022 rule.
