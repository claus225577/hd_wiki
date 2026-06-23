---
title: "A DDSP Framework for Adaptive Room Equalization"
type: source
source_type: arxiv-paper
arxiv_id: 2606.22563
authors: [F. Marcos-Macias, M. P. Daza-Llin, M. Camara, J. L. Blanco]
date_published: 2026-06-21
ingested: 2026-06-23
url: https://arxiv.org/abs/2606.22563
venue: "Accepted at 29th International Conference on Digital Audio Effects (DAFx26)"
tags: [ddsp, differentiable-dsp, adaptive-room-equalization, fxlms, filtered-x-lms, feedback-cancellation, vent-eq, dafx26, open-source, hearing-aids, hidvas]
---

# arXiv:2606.22563 — DDSP Framework for Adaptive Room Equalization (Marcos-Macias et al., Jun 2026)

## Bibliographic
- **Authors:** F. Marcos-Macias, M. P. Daza-Llin, M. Camara, J. L. Blanco
- **Posted:** 21 June 2026 (arXiv:2606.22563, eess.AS)
- **Venue:** Accepted at the **29th International Conference on Digital Audio Effects (DAFx26)**
- **URL:** https://arxiv.org/abs/2606.22563

## Problem
Adaptive room equalisation under **time-varying acoustic conditions** (listener moves, doors open, occupancy changes, temperature drifts) is the canonical use case for **filtered-x LMS (FxLMS)** and its frequency-domain variants. FxLMS has been the workhorse since the 1980s — well understood, mathematically tractable, but locked to a specific filter structure and adaptation rule. As soon as the EQ topology, optimizer, or per-frequency error weighting needs to change, the analytical FxLMS framing breaks down and the engineer is back to deriving update rules by hand.

## Contribution
A **Differentiable DSP (DDSP)** framework that recasts adaptive room EQ as a gradient-descent problem inside an autodiff graph:
- **FxLMS recovered as a special case.** Under the specific choice of EQ structure (linear filter), loss (per-sample MSE), and optimizer (SGD with the secondary-path-filtered reference), the DDSP framework reproduces FxLMS exactly. This is the unification claim — the classical algorithm is one point in a continuous parameter space the framework can search over.
- **Flexible EQ structures and optimizers.** Different filter topologies (cascade biquads, parametric EQs, learned implicit responses), perceptually-weighted losses, and modern optimizers (Adam, RMSprop) all plug in without re-deriving update rules.
- **Open-source implementation.** The framework is published as a software basis for adaptive-EQ research.

## Headline Numbers
- **~70% reduction in system distance** vs unequalized reference.
- **13% worst-case improvement in mel-spectral distance** vs unequalized response — i.e. the *worst* test condition (the hardest room geometry / listener position) improves by 13%, not just the average.

## Why It Matters for Hearing AI

### FxLMS is the workhorse of hearing-aid feedback cancellation
The classical adaptive-filter stack on every modern hearing aid is built around FxLMS-family algorithms:
- **Feedback cancellation** — estimating the secondary path from receiver back to mic through the vent + leak; cancelling the feedback signal before it triggers howl.
- **Dome / vent compensation** — adapting the EQ to the wearer's chosen dome (open / semi-open / closed) and the leakage profile it produces.
- **Leak management** — tracking the time-varying vent acoustics as the wearer's jaw moves, hat is donned, phone presses against the ear.
- **Room EQ for streaming audio** — when a hearing aid streams from a TV / phone / Auracast source, the receiver-to-eardrum path is a small "room" the device equalises.

All four sit inside the same FxLMS-shaped problem statement. Recasting FxLMS as a DDSP special case **unifies feedback cancellation, vent-EQ, and room-EQ under a single differentiable operator family** — and exposes the EQ topology + loss + optimizer triple as free hyperparameters that can be searched.

### Stacks with HIDVAS (KU Leuven, June 12 2026)
HIDVAS publishes real dummy-head recordings spanning four dome configurations and four reverberation conditions, with impulse responses included. That is **exactly the substrate** an adaptive-EQ DDSP framework needs:
- Train the DDSP-EQ on HIDVAS impulse responses → personalize per dome configuration.
- Hold out a dome / reverb condition → evaluate generalization.
- Composes a closed loop where HIDVAS is the data substrate and the DDSP framework is the optimizer.

### Parallel to Google DAL on the loss-function-relocation axis
DAL (arXiv:2606.04103, Google Research Australia + Macquarie, 4 Jun 2026) put a **differentiable cochlear model** inside the training loop, making the perceptual loss flow through CARFAC. This DDSP-EQ paper does the analogous move for the **environment** side: put a **differentiable EQ structure** inside the training loop, making the adaptation rule flow through any chosen filter topology + optimizer. Both reframe a previously hand-derived analytical step as a gradient-descent special case.

Together they argue that 2026 is the year **adaptive hearing processing moves from per-component analytical rules to a single end-to-end differentiable graph** spanning cochlea (DAL), room/vent (this paper), and downstream SE (band-axis cluster, on-chip levers).

### DDSP as the lingua franca
The Engel et al. 2020 DDSP paper introduced the term for music-side differentiable signal processing. Its migration into **hearing-aid-adjacent adaptive filtering** in 2026 — first published at DAFx26 — signals the operator family is generalising beyond synthesis and effects to include **adaptive control** problems that have lived in pure DSP for forty years.

## Open Questions
- On-chip cost: the FxLMS reference is famously cheap (a handful of MACs per sample). Does the DDSP recast preserve that footprint at deployment, or only at training?
- Per-wearer fitting: a personalised vent-EQ per dome configuration is the obvious clinical workflow — does the framework support warm-starting from a population prior + fine-tuning on the wearer's IRs?
- Closed-loop stability: FxLMS has known convergence guarantees; do learned EQ topologies retain stability margins under the same secondary-path conditions?
- Coupling to deep feedback cancellation (DFC-IL, Voit & Doclo, Jun 2026): both target the same loop. Are they complementary (DDSP-EQ for slow path drift, neural DFC for fast non-stationary feedback) or substitutable?

## Cross-References
- **HIDVAS dataset (training substrate):** [arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md](arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md) — KU Leuven, June 12, 2026
- **DAL (parallel differentiable-loop work):** [dal-differentiable-auditory-loop-google-june-2026.md](dal-differentiable-auditory-loop-google-june-2026.md) — Google Research Australia + Macquarie, June 4, 2026
- **DFC-IL (the in-the-loop neural FC counterpart):** `arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md` — Voit & Doclo, June 2026
- **RIR-encoder (room-aware SE parallel):** [arxiv-2606-09557-rir-encoder-dereverb-khanagha-gerkmann-jun-2026.md](arxiv-2606-09557-rir-encoder-dereverb-khanagha-gerkmann-jun-2026.md) — Khanagha & Gerkmann, U Hamburg, accepted Interspeech 2026
- **Related concept pages:** `wiki/concepts/acoustic-feedback-cancellation.md`; `wiki/concepts/room-aware-dereverberation.md`; `wiki/concepts/differentiable-cochlear-models.md`; new candidate page `wiki/concepts/differentiable-dsp.md` (consolidates DDSP as a hearing-AI operator family); new candidate page `wiki/concepts/fxlms-adaptive-filtering.md` (catalogues the classical algorithm and its DDSP recast)
