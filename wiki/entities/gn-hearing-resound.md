---
title: GN Hearing / ReSound
type: entity
created: 2026-04-15
updated: 2026-05-28
sources: [gn-nal-nl3-global-launch-march-2026.md, amplifon-gn-acquisition-2026.md, auracast-hearing-accessibility-2026.md, resound-vivia-launch-2025.md, aida-2-bayesian-generative-se-arxiv-2026.md, gn-auracast-seoul-session-big-ocean-may-2026.md]
related: [amplifon.md, ../concepts/auracast-bluetooth-le-audio.md, ../concepts/closed-loop-data-flywheel.md, ../concepts/probabilistic-generative-models-hearing-ai.md, ../concepts/hearing-aid-prescription-formulas.md, sonova-ag.md, ../concepts/hearing-care-funnel-attribution.md]
tags: [company, manufacturer, resound, gn-group, acquired, dnn, auracast, dual-chip, bayesian, gn-advanced-science, nal-nl3, fitting-software, stigma, korea, lmic]
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

## NAL-NL3 — First to Ship Data-Native Prescription Formula (March 2026)

On 11 March 2026, GN became the **first hearing-aid manufacturer to ship a fitting platform built on NAL-NL3**, the successor to the 2011-era NAL-NL2 prescription formula and the field's first data-derived prescription baseline. Released globally across:
- ReSound Smart Fit 2.3.1
- Beltone Solus Max 2.3.1
- Hearing Australia Fitware 2.3.1

NL3 layers large-scale clinical fitting datasets and real-world user feedback into the prescription target itself — making the default starting point for every fitting a data-derived prior rather than a hand-tuned acoustic-loudness model. Companion enhanced AutoREM tooling automates the real-ear verification step. Combined with GN's downstream DNN (Vivia) and Bayesian (AIDA-2) lines, this is the most complete top-to-bottom data-native fitting stack of any OEM as of mid-2026. See [[../concepts/hearing-aid-prescription-formulas]] for the cross-OEM picture.

## Seoul Session at WCA 2026 — Stigma + Cultural Deployment (May 26, 2026)

At the 37th World Congress of Audiology (Seoul, May 24-27, 2026), GN partnered with Ampetronic to stage "Seoul Session" — the **first permanent Auracast venue installation in South Korea**, at Kind Seoul jazz club. The event featured a live performance by **Big Ocean**, the K-pop trio whose three members all wear hearing aids and cochlear implants.

Andreas Anderhov (GN APAC President) confirmed the installation is permanent, not a single-night event.

In parallel, GN released **YouGov stigma data** (nationally representative online surveys, 30 January – 4 February 2026, n≈3,053 across Australia / UK / US, with n≈955 hearing-loss respondents):
- Up to **40%** of people with hearing loss report being perceived as less intelligent or less capable
- More than a third are read as rude or disengaged
- More than a third report others believe they should "try harder" to hear

The combined release reframes GN's positioning at WCA from product showcase to **demand-side intervention**: the Seoul install is structurally an A/B intervention on the stigma variable that supply-side optimization (chips, DNNs, fitting) has never instrumented. GN's regional president's framing — "These misconceptions don't just affect perception, they influence how environments and policies are designed" — situates GN at the intersection of accessibility infrastructure (Auracast) and the demand-side adoption funnel.

## Related Pages
- [[amplifon]] — Acquirer; full deal terms and strategic implications
- [[auracast-bluetooth-le-audio]] — GN/ReSound as first mover; Seoul permanent venue install May 2026
- [[closed-loop-data-flywheel]] — Data strategy enabled by Amplifon merger
- [[../concepts/probabilistic-generative-models-hearing-ai]] — AIDA-2 / GN Advanced Science line
- [[../concepts/hearing-aid-prescription-formulas]] — NL3 first-mover; cross-OEM landscape
- [[../concepts/hearing-care-funnel-attribution]] — Seoul stigma intervention as funnel input

## Sources
- [GN NAL-NL3 Global Launch (March 2026)](../sources/gn-nal-nl3-global-launch-march-2026.md) — World-first commercial NL3 fitting platform across ReSound Smart Fit, Beltone Solus Max, Hearing Australia Fitware
- [Amplifon-GN Acquisition 2026](../sources/amplifon-gn-acquisition-2026.md)
- [Auracast Hearing Accessibility 2026](../sources/auracast-hearing-accessibility-2026.md)
- [ReSound Vivia Launch 2025](../sources/resound-vivia-launch-2025.md) — CES 2025 introduction, dual-chip architecture, DNN specs, Auracast
- [AIDA-2 — A Probabilistic Generative Model for Spectral Speech Enhancement](../sources/aida-2-bayesian-generative-se-arxiv-2026.md) — GN Advanced Science + TU Eindhoven, arXiv 2603.28436, 30 Mar 2026
- [GN/Ampetronic Seoul Session + YouGov stigma data (May 26, 2026)](../sources/gn-auracast-seoul-session-big-ocean-may-2026.md) — First permanent Auracast venue install in South Korea; Big Ocean K-pop performance; YouGov stigma survey across AU/UK/US
