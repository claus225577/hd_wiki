---
title: "BiEAR: A Human Auditory-Inspired Adaptive Binaural Front-end for Multi-Speaker Localisation and Distance Estimation"
source_type: arxiv-paper
publisher: arXiv (eess.AS); accepted INTERSPEECH 2026
date: 2026-06-05
url: https://arxiv.org/abs/2606.06795
arxiv_id: 2606.06795
authors: [Hanyu Meng, Eliathamby Ambikairajah, Vidhyasaharan Sethu, Qiquan Zhang, Haizhou Li]
affiliations: [UNSW Sydney (Meng/Ambikairajah/Sethu/Zhang), Haizhou Li (NUS / CUHK Shenzhen)]
type: arxiv-paper
tags: [binaural, auditory-front-end, medial-olivocochlear, moc-reflex, efferent-feedback, adaptive-filterbank, cochlear-models, multi-speaker-localisation, distance-estimation, hearing-aids, biologically-inspired-ml, interspeech-2026]
ingested: 2026-06-09
---

# BiEAR: A Human Auditory-Inspired Adaptive Binaural Front-end (Meng et al., June 5 2026)

## Summary
A new arXiv paper, accepted to INTERSPEECH 2026, introduces **BiEAR** — a binaural auditory front-end whose **filterbank frequency selectivity is adaptively adjusted at inference time by a neural controller**. The biological inspiration is explicit: the **medial olivocochlear (MOC) reflex**, the efferent feedback loop in human hearing in which the brainstem modulates outer hair cell gain in response to the acoustic scene.

The system yields **time-frequency adaptive representations** and improves **multi-speaker localisation and distance estimation**, with robustness to unseen rooms and unseen speakers compared to fixed binaural front-ends commonly used in spatial audio ML.

## Authors & Affiliations
- Hanyu Meng (PhD candidate, UNSW Sydney, School of EE & Telecommunications)
- Eliathamby Ambikairajah (UNSW Sydney)
- Vidhyasaharan Sethu (UNSW Sydney)
- Qiquan Zhang (UNSW Sydney)
- Haizhou Li (NUS / CUHK Shenzhen — major figure in speech ML / target speaker extraction)

## Headline Facts
- **Posted:** June 5, 2026 (arXiv:2606.06795).
- **Venue:** Accepted INTERSPEECH 2026.
- **Tasks evaluated:** Multi-speaker localisation; distance estimation. Anechoic and real-room conditions.
- **Result:** Improved localisation accuracy + robustness to unseen speakers/rooms vs commonly used fixed binaural front-ends.
- **Mechanism:** Neural controller adaptively adjusts the frequency selectivity of a binaural auditory filterbank during inference; bilateral feedback controllers modulate filter characteristics based on per-frame subband sound pressure levels.
- **Analysis claim:** Visualisation of learned filter adaptations shows BiEAR "emphasises informative frequency bands over time."

## Biological Reference: The MOC Reflex
The medial olivocochlear (MOC) reflex is an **efferent** (descending) auditory pathway: brainstem neurons in the superior olivary complex synapse onto outer hair cells in the cochlea and modulate cochlear gain in response to the acoustic environment. Functions established in the auditory neuroscience literature include:

- **Anti-masking** — reducing the response to a steady background to better resolve a transient foreground.
- **Selective attention support** — efferent feedback is implicated in helping listeners focus on one talker in cocktail-party scenes.
- **Protective gain reduction** — efferent feedback reduces cochlear sensitivity in sustained loud environments.

BiEAR is one of the **first end-to-end ML systems to model the MOC reflex as a learned controller**, rather than treating the cochlea as a fixed preprocessing block.

## Significance for Hearing-Aid AI

### 1. Closes the "afferent vs efferent" loop alongside DAL
A useful pairing:
- **Google DAL (June 4, 2026, arXiv:2606.04103)** — Differentiable Auditory Loop; embeds CARFAC as a differentiable forward cochlear model and trains the DNN above it. *This is the afferent (forward) side of the auditory system.*
- **BiEAR (June 5, 2026, arXiv:2606.06795)** — Learned MOC-style efferent controller modulating cochlear filterbank selectivity at inference. *This is the efferent (descending) side.*

Together, the two papers — posted within 24 hours of each other — mean that 2026 is the year the cochlear loop, forward and back, becomes a first-class ML object instead of a fixed preprocessing block.

### 2. Reframes binaural processing
In conventional hearing aids, the binaural processing chain treats the filterbank as fixed at manufacture, the gain map as fixed at fitting, and adapts only the back-end (beamformer, noise reduction, scene classifier). BiEAR moves the adaptation point upstream into the **filterbank itself**, so the very basis on which features are extracted becomes scene- and time-dependent.

### 3. Second axis of personalization
The audiogram-shaped insertion gain has been a one-shot, person-level parameter for forty years. Efferent gain control is the **second axis** — moment-by-moment, scene-conditioned. A learned MOC-controller could in principle be personalized to a wearer's residual efferent function (which is impaired in many forms of hearing loss).

### 4. Maps to existing chip primitives
The MOC-style adaptive filterbank is a small, low-rate control signal modulating a structured filterbank — exactly the kind of computation that maps cheaply onto power-budgeted DSP / NPU hearing-aid silicon. Unlike adding more parameters to a back-end DNN, this is a structural addition that should not blow the power budget.

## Limits / Open Questions
- The paper evaluates localisation/distance estimation, not speech-in-noise intelligibility (HASPI/STOI/CEC). The HA-relevant SI loss is the natural next port.
- Hearing-impaired efferent function differs from normal-hearing. Whether the same controller architecture transfers to impaired listeners is an open empirical question.
- Hardware translation cost on actual hearing-aid silicon (vs simulation) is not addressed.
- The MOC literature is rich but the specific loss function BiEAR uses to "supervise" the controller is downstream task loss (localisation/distance) — not a direct biological-fidelity loss. Whether the learned policy resembles the biological MOC is an interesting downstream analysis.

## Related Wiki Pages
- [Efferent MOC Feedback in Hearing AI](../wiki/concepts/efferent-moc-feedback-hearing-ai.md) (new)
- [Differentiable Cochlear Models](../wiki/concepts/differentiable-cochlear-models.md) (afferent counterpart)
- [Binaural Beamforming](../wiki/concepts/binaural-beamforming.md) (legacy fixed-filterbank baseline being upgraded)
- [Auditory Attention Decoding](../wiki/concepts/auditory-attention-decoding.md) (cocktail-party context)

## Related Sources
- [dal-differentiable-auditory-loop-google-june-2026.md](dal-differentiable-auditory-loop-google-june-2026.md) — Afferent forward cochlear model, posted June 4 2026 (companion to BiEAR's efferent side)
