---
title: Automated & Computational Audiometry
type: concept
created: 2026-04-15
updated: 2026-04-21
sources: [ml-pure-tone-audiometry-automated-masking-2025.md, deep-learning-audiogram-classification-2024.md, hearing-loss-type-classification-ml-2024.md, ml-menieres-disease-audiometry-2025.md, kde-vae-audiometric-data-synthesis-2025.md, audiologist-shortage-asha-sciencedirect-2025.md]
related: [teleaudiology.md, vcca-computational-audiology.md, on-device-ml-hearing-aids.md, audiologist-workforce-shortage.md, model-context-protocol.md]
tags: [audiometry, machine-learning, automated-testing, pure-tone, classification, clinical-decision-support, workforce-shortage]
---

# Automated & Computational Audiometry

The application of machine learning and AI to automate, improve, and extend pure-tone audiometry — the foundational hearing test in clinical audiology.

## Current State of the Art

### ML-Based Pure-Tone Audiometry
- Bayesian estimation and ML classification replace manual up-down threshold seeking
- **Key advance (2025):** Automated masking — ML now handles contralateral masking decisions, previously a major gap that limited clinical validity for asymmetric/conductive hearing loss (Wallaert et al., 2025)
- Still being validated for edge cases: severe hearing loss, cochlear dead zones

### Deep Learning Audiogram Classification
- DL frameworks classify audiogram patterns: flat, sloping, rising, cookie-bite, etc. (Dou et al., Clinical Otolaryngology, 2024)
- Assists non-specialist clinicians in audiogram interpretation
- InceptionV3-based interpretation (Egyptian J. Otolaryngology, 2025) — using transfer learning from image classification

### Hearing Loss Type Classification
- Automated classification: sensorineural vs. conductive vs. mixed (Nature Scientific Reports, 2024)
- Uses standard air and bone conduction threshold data
- Determines treatment pathway (aids vs. surgery vs. combined)

### Disease-Specific Applications
- **Meniere's disease:** ML diagnosis from pure-tone audiometry features; also predicts endolymphatic hydrops subtypes (Otolaryngology–HNS, 2025)
- Screening without expensive vestibular testing or MRI

## Synthetic Data for Audiometry Research

- KDE (Kernel Density Estimation) and VAE (Variational Autoencoder) approaches validated for generating synthetic audiometric data (Applied Sciences, 2025)
- Trained on NHANES dataset (36,676 participants)
- Enables ML training without privacy-sensitive patient data

## VCCA Research

Automated audiometry is a recurring VCCA theme:
- **VCCA2025:** Robert Eikelboom — ML study on audiometrically normal clients; Mériem Jaïdane — Gaussian Process Regression for Hughston-Westlake protocol
- **VCCA2025:** AI Clinical Audiometry Simulation Platform (AICAS) by Nazlı Tokatlı
- **VCCA2025:** Smartphone hearing test apps validity (Kim Hui LIM)

## Clinical Barriers to Adoption

1. **Masking:** Now addressed by ML (Wallaert 2025), but needs further clinical validation
2. **Calibration:** Automated tests on consumer devices (phones, tablets) face acoustic calibration challenges
3. **Regulation:** Clinical audiometry has established standards (ISO 8253); ML methods must meet these
4. **Edge cases:** Severe loss, cochlear dead zones, non-organic hearing loss still challenge automated systems
5. **Clinician trust:** Audiologists need to trust ML results before adopting them

## Related Pages
- [[teleaudiology]] — Remote audiometry is the primary use case for automated testing
- [[vcca-computational-audiology]] — Major venue for automated audiometry research

## Sources
- [ML Pure-Tone Audiometry with Automated Masking](../sources/ml-pure-tone-audiometry-automated-masking-2025.md)
- [Deep Learning Audiogram Classification](../sources/deep-learning-audiogram-classification-2024.md)
- [Hearing Loss Type Classification](../sources/hearing-loss-type-classification-ml-2024.md)
- [ML for Meniere's Disease](../sources/ml-menieres-disease-audiometry-2025.md)
- [KDE/VAE Audiometric Data Synthesis](../sources/kde-vae-audiometric-data-synthesis-2025.md)
