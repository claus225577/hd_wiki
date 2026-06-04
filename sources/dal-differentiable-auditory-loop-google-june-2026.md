---
title: "The Differentiable Auditory Loop (DAL): An ML Framework for Hyper-Personalized Hearing Aids"
url: https://arxiv.org/abs/2606.04103
date: 2026-06-04
type: paper
authors: Alejandro Ballesta Rosen, Jason Mikiel-Hunter, Julian Maclaren, Jack Collins, Richard F. Lyon, Simon Carlile
affiliations: Google Research Australia; Macquarie University
arxiv_id: 2606.04103
tags: [differentiable-cochlea, carfac, personalization, perceptual-loss, google, hearing-aid-fitting, jax, open-source]
---

# The Differentiable Auditory Loop (DAL): An ML Framework for Hyper-Personalized Hearing Aids

## Key Extractions

- arXiv 2606.04103, submitted 4 Jun 2026
- Authors: Ballesta Rosen, Mikiel-Hunter, Maclaren, Collins, Lyon, Carlile
- Affiliations: Google Research Australia (4 authors); Macquarie University (joint affiliation, 2 authors)
- Open-source framework for personalized hearing-aid design and fitting
- Core architectural move: put CARFAC (Cascade of Asymmetric Resonators with Fast-Acting Compression, Lyon's cochlear model) inside the training loop by porting it to JAX
- Two CARFAC instances run side by side during training: a normal-hearing reference and a per-wearer instance fitted to the wearer's outer-hair-cell (OHC) loss profile
- Loss function operates in the perceptual / cochlear-neural-activity domain, not in the signal domain (PESQ / STOI / HASPI)
- Two loss components: Neural Activity Pattern (NAP) mismatch and Stabilized Auditory Image (SAI) mismatch
- SAI provides a 2D phase-insensitive representation of auditory nerve output
- The trainable processor is SEANet — waveform-to-waveform fully convolutional UNet generator
- SEANet learns by gradient descent to simultaneously denoise the input and compensate for the wearer's hearing loss in a single end-to-end optimization
- Reported result: DAL-optimized SEANet outperforms master hearing aid (MHA) baselines on neural-representation and signal-fidelity metrics, particularly in cocktail-party (multi-talker) conditions
- Next step listed by the authors: hardware deployment for clinical testing

## Relevance to Hearing + AI

- **Loss-function relocation.** The differentiator vs prior CARFAC work (e.g., CARFAC v2, arXiv:2404.17490) and prior differentiable-hearing-loss work (e.g., Tu et al., arXiv:2106.04639) is that DAL is the first published end-to-end hearing-aid framework in which the perceptual loss is defined on the output of a differentiable cochlear model inside the backprop graph, not as a perceptual surrogate post-hoc.
- **Prescription → cost function.** Fitting prescriptions (NAL-NL3, DSL v5, manufacturer-specific defaults like Phonak APD / Oticon VAC+) are population-derived signal-domain priors. DAL reframes those priors as warm starts for a per-wearer optimization whose objective lives in the auditory-nerve-activity space, not the signal space.
- **Brain-aligned loss thread.** Provides the tractable gradient bridge that the FUEL / communication-accessibility argument (Pichora-Fuller, Aram Glorig Award WCA 2026), the Mesgarani closed-loop AAD paper (Nat Neurosci, 11 May 2026), and the Ciferri/Whisper-ECoG paper (arXiv:2606.02305, 1 Jun 2026) have been pointing at conceptually but not architecturally.
- **Open-source strategic implications.** Whoever owns the differentiable perceptual model owns the loss function the next decade of personalization will be optimized against. Google open-sourcing both CARFAC-JAX and DAL changes the access economics — academic groups and OEMs without proprietary cochlear simulators can now train against a credible perceptual loss without building one.
- **OEM positioning.** No major OEM has published a differentiable-cochlea fitting pipeline. The closest adjacent work is GN Advanced Science's AIDA-2 Bayesian generative model (arXiv:2603.28436, 30 Mar 2026) — also a non-DNN-maximalist track, but operating in signal/spectral domain rather than perceptual domain.
- **Regulatory question.** If the loss function flows through a per-wearer model of the wearer's cochlea, "personalization" becomes a per-device training run on patient-specific data — bringing predetermined change control plans, FDA AI/ML SaMD framing, and audit trails into the fitting workflow.

## Cross-references
- CARFAC GitHub: https://github.com/google/carfac
- CARFAC v2 paper: arXiv:2404.17490 (Lyon, 2024)
- Differentiable hearing-loss baseline: arXiv:2106.04639 (Tu et al., 2021)
- SEANet original paper: Tagliasacchi et al., 2020 (waveform-to-waveform UNet generator for audio)
- Adjacent Bayesian alternative: AIDA-2 (arXiv:2603.28436, GN Advanced Science + TU Eindhoven, Mar 2026)
