---
title: Sonova AG
type: entity
created: 2026-04-15
updated: 2026-04-17
sources: [phonak-infinio-sphere-2024.md, phonak-dnn-noise-reduction-clinical-trial-april-2026.md, advanced-bionics-research-collaboration-ci-april-2026.md]
related: [../concepts/on-device-ml-hearing-aids.md, demant-oticon.md, ws-audiology-signia.md, gn-hearing-resound.md, starkey.md, phonak-audeo-sphere-infinio.md, advanced-bionics.md, ../concepts/cochlear-implant-ai.md]
tags: [company, manufacturer, phonak, unitron, advanced-bionics, ai-chip, dual-chip, clinical-trial, cochlear-implant]
---

# Sonova AG

Swiss hearing care company and one of the world's largest hearing aid manufacturers. Headquartered in Stäfa, Switzerland. Primary hearing aid brand is **Phonak**.

## Brands
- **Phonak** — Primary/flagship hearing aid brand (Audéo Sphere Infinio, Virto R Infinio, Lumity, Infinio lines)
- **Unitron** — Mid-tier hearing aid brand
- **Advanced Bionics** — Cochlear implant division (see [[advanced-bionics]])
- **AudioNova** — Retail hearing care network (acquired 2016)

## Technology Platform

### DEEPSONIC Chip (2025)
Sonova's proprietary next-generation AI chip powering the Infinio Ultra platform:
- **7.7 billion operations per second** processing capacity
- **4.5 million neural network connections** on-device
- **Dual-chip architecture** — 53x more processing power than the industry standard single-chip approach
- Trained on **22 million sound scenes** (vs. earlier generation training datasets)
- Enables real-time AI audio processing that competitors cannot match with single-chip designs

### Earlier Platform
- **PRISM chip** — Powered Phonak Lumity and early Infinio; now superseded by DEEPSONIC for flagship products

### Key Features
- **Spheric Speech Clarity 2.0** — AI-driven speech enhancement leveraging DEEPSONIC compute
- **AutoSense OS** — ML-based automatic program switching (acoustic scene classification); foundation for newer AI features
- **Roger** — Proprietary wireless microphone system for noisy/educational environments
- **myPhonak app** — Consumer-facing app with remote fitting capabilities

## Product Milestones
- **Audéo Sphere Infinio (Aug 2024)** — Flagship AI hearing aid; world's first dedicated real-time AI chip (DEEPSONIC). DNN trained on 22M+ samples. Spheric Speech Clarity 2.0. AutoSense OS 7.0. Initial 24% improvement in speech intelligibility. One of only 2 products globally with real-time AI processing as of mid-2025 (alongside ReSound Vivia). 56-hour battery life.
- **Virto R Infinio** — Custom IIC/ITC form-factor AI hearing aid; won **2026 iF Design Award** and **AI Excellence Award**
- **Ultra firmware update (Oct 2025)** — Retrained DNN with 30% more efficiency, resulting in 35% less listening effort for users. Added 18x more real-world training data post-launch. Speech intelligibility improvement revised up to 35%.
- **Infinio Ultra Sphere** — Announced at EUHA 2025, expanding the Infinio Ultra platform

## Dual-Chip Architecture Significance
Sonova's decision to use two dedicated chips (one for standard processing, one for AI) is a deliberate architectural bet against competitors who use a single integrated chip. The 53x processing headroom claim positions Sonova as having the highest AI compute capacity in hearing aids as of 2025–2026. Oticon (Demant) has publicly defended a single-chip (integrated NPU) approach as sufficient for their DNN models.

HearAdvisor independent testing rated the Audéo Sphere Infinio as best-in-class for noise performance.

## Recent Developments (April 2026)

### Phonak DNN Clinical Trial (NCT07526428)
- Registered interventional study for DNN noise reduction in moderate-to-severe hearing loss
- First clinical trial specifically targeting DNN efficacy for more severe hearing loss populations
- Signals evidence-building strategy for DEEPSONIC platform claims

### Advanced Bionics Research Collaboration
- AB announced new research collaboration to advance next-generation cochlear implant innovation (April 14, 2026)
- Dual-track innovation: hearing aid AI (DEEPSONIC) + CI technology development
- CI market ($2B+ annually) is a strategic growth segment with higher margins

## Market Position
- Consistently #1 or #2 globally by revenue (competing with Demant)
- Strong in pediatric audiology
- Integrated manufacturer + retailer (AudioNova acquisition)

## Data Science Relevance
- DEEPSONIC dual-chip represents the highest on-device ML compute in any hearing aid to date
- 22M sound scene training corpus exceeds competitor published figures (Oticon: 13M, ReSound: 13.5M sentences)
- Ultra firmware OTA update mechanism demonstrates ongoing model improvement post-deployment
- Roger ecosystem generates usage data across education and workplace settings
- Remote fitting through myPhonak creates digital touchpoints for data collection

## Related Pages
- [[phonak-audeo-sphere-infinio]] — Detailed product page for Sonova's flagship AI hearing aid
- [[advanced-bionics]] — Cochlear implant subsidiary; next-gen CI research collaboration
- [[on-device-ml-hearing-aids]] — DEEPSONIC dual-chip as key architecture example
- [[cochlear-implant-ai]] — AI applications in Sonova's CI division
- [[demant-oticon]], [[ws-audiology-signia]], [[gn-hearing-resound]], [[starkey]] — Competitors

## Sources
- [Phonak Infinio Sphere 2024](../sources/phonak-infinio-sphere-2024.md) — DEEPSONIC chip specs, launch details, Ultra update, awards
- [Phonak DNN Clinical Trial](../sources/phonak-dnn-noise-reduction-clinical-trial-april-2026.md) — NCT07526428
- [AB Next-Gen CI Collaboration](../sources/advanced-bionics-research-collaboration-ci-april-2026.md) — CI research partnership
