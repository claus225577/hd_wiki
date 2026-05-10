---
title: GN Hearing / ReSound
type: entity
created: 2026-04-15
updated: 2026-05-10
sources: [amplifon-gn-acquisition-2026.md, auracast-hearing-accessibility-2026.md, resound-vivia-launch-2025.md, aida-2-bayesian-generative-se-arxiv-2026.md]
related: [amplifon.md, ../concepts/auracast-bluetooth-le-audio.md, ../concepts/closed-loop-data-flywheel.md, ../concepts/probabilistic-generative-models-hearing-ai.md, sonova-ag.md]
tags: [company, manufacturer, resound, gn-group, acquired, dnn, auracast, dual-chip, bayesian, gn-advanced-science]
---

# GN Hearing / ReSound

Danish hearing aid manufacturer, formerly part of GN Group (which also owns Jabra). Being acquired by Amplifon in a deal expected to close end of 2026.

## Brands & Products
- **ReSound** — Primary hearing aid brand
- **ReSound Vivia** — Flagship AI hearing aid (Feb 2025, unveiled at CES 2025)
- **ReSound Nexia** — First hearing aid with Auracast support
- **Beltone** — Secondary brand (primarily North American market)

## Technology

### ReSound Vivia (Feb 2025) — First ReSound DNN Hearing Aid
Introduced at **CES 2025**, Vivia represents GN Hearing's entry into dedicated deep neural network hearing aids:
- **Dual-chip architecture** — Separate 360-series chip for standard audio processing + dedicated DNN chip for neural network inference
- **Trained on 13.5 million sentences** — Large-scale speech-focused training corpus
- **3.9 million DNN parameters**
- **4.9 trillion operations per day** — Continuous real-time inference load
- **World's smallest AI micro-RIE** — Smallest AI-powered receiver-in-ear form factor at launch
- **Intelligent Focus** — Adapts directional processing based on head direction (similar in concept to Oticon's 4D head motion sensing)
- **First fully Auracast-equipped hearing aid** — Ships with Bluetooth LE Audio + Auracast broadcast support out of the box
- **64% of users report improved hearing in noise** in clinical user trials
- Achieves **35% less listening effort** in difficult environments (per published data)

### Architecture Note
ReSound Vivia and Phonak Audéo Sphere Infinio are the only 2 products globally with real-time AI neural network processing as of mid-2025. Both use dedicated AI chips (Vivia: dual-chip 360+DNN; Phonak: DEEPSONIC dual-chip). Oticon uses an integrated NPU within the Sirius SoC.

### Earlier Platform
- **Organic Hearing platform** — Proprietary chip and signal processing underlying earlier ReSound products
- **M&RIE (Microphone & Receiver-in-Ear)** — Unique receiver design that uses the ear's natural acoustic shape for improved spatial hearing
- **ReSound Smart 3D app** — Consumer app with hearing aid controls and remote fine-tuning

## Auracast Leadership
- First to market with Bluetooth LE Audio Auracast broadcast support (ReSound Nexia)
- ReSound Vivia ships as the first fully Auracast-equipped hearing aid at launch
- Cross-pollination between Jabra (enterprise audio/conferencing) and ReSound R&D teams was a noted advantage for Bluetooth/wireless development

## Acquisition by Amplifon (2026)

### Deal Structure
- **GN Group receives**: €1.69 billion cash + 56 million Amplifon shares
- Amplifon becomes vertically integrated: largest hearing aid retailer + a full manufacturer
- Transaction expected to close **end of 2026** (pending regulatory/antitrust approval)
- Post-sale, GN Group will refocus on its audio/video peripherals business (Jabra)

### Strategic Rationale
- Creates the first major retailer+manufacturer combination since Sonova (AudioNova) and Demant (HearingLife)
- Gives Amplifon proprietary AI hearing aids (ReSound Vivia) to sell through its 10,000+ clinics
- Enables closed-loop data flywheel: patient outcome data from clinics feeds back to product R&D
- US market becomes the combined entity's biggest single market

## GN Advanced Science — Research Arm

GN's research organization (Eindhoven, NL), connected to TU Eindhoven via long-running collaborations with Bert de Vries (ELLIS Unit Eindhoven). Notable for advancing factor-graph and Bayesian-inference approaches to hearing-aid signal processing alongside the dominant DNN line.

### AIDA-2 — Probabilistic Generative Speech Enhancement (March 2026)
Hidalgo-Araya, Trésor, van Erp, Nuijten, van de Laar, de Vries (arXiv 2603.28436, 30 March 2026) propose a unified Bayesian generative model in which signal enhancement, training, and personalization all become inference tasks in the same factor graph (RxInfer.jl):
- ~85 effective parameters competitive with Wiener filtering on VoiceBank+DEMAND (PESQ 2.17 vs 2.22).
- Six orders of magnitude fewer parameters than DNN baselines.
- Personalization is Bayesian posterior updating on user appraisals — no separate fitting pipeline.
- Signals industrial validation of probabilistic generative modeling as a third path beyond DNN-vs-classical DSP. See [[../concepts/probabilistic-generative-models-hearing-ai]].

This positions GN distinctively against Phonak/Sonova (DEEPSONIC DNN), Oticon (Sirius NPU), and Starkey (Omega DNN 360) — all of whom are scaling deep networks. ReSound Vivia is GN's DNN play; AIDA-2 hints at a parallel non-DNN R&D track.

## Related Pages
- [[amplifon]] — Acquirer; full deal terms and strategic implications
- [[auracast-bluetooth-le-audio]] — GN/ReSound as first mover
- [[closed-loop-data-flywheel]] — Data strategy enabled by Amplifon merger
- [[../concepts/probabilistic-generative-models-hearing-ai]] — AIDA-2 / GN Advanced Science line

## Sources
- [Amplifon-GN Acquisition 2026](../sources/amplifon-gn-acquisition-2026.md)
- [Auracast Hearing Accessibility 2026](../sources/auracast-hearing-accessibility-2026.md)
- [ReSound Vivia Launch 2025](../sources/resound-vivia-launch-2025.md) — CES 2025 introduction, dual-chip architecture, DNN specs, Auracast
- [AIDA-2 — A Probabilistic Generative Model for Spectral Speech Enhancement](../sources/aida-2-bayesian-generative-se-arxiv-2026.md) — GN Advanced Science + TU Eindhoven, arXiv 2603.28436, 30 Mar 2026
