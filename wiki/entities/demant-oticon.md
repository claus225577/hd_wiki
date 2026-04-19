---
title: Demant / Oticon
type: entity
created: 2026-04-15
updated: 2026-04-17
sources: [oticon-intent-launch-2024.md, oticon-verit-launch-april-2026.md, oticon-play-si-pediatric-launch-april-2026.md]
related: [sonova-ag.md, ../concepts/on-device-ml-hearing-aids.md, ws-audiology-signia.md, gn-hearing-resound.md, starkey.md, ../concepts/auracast-bluetooth-le-audio.md]
tags: [company, manufacturer, oticon, denmark, dnn, brainhearing, single-chip, npu, auracast, le-audio, pediatric]
---

# Demant / Oticon

Danish hearing care conglomerate. One of the top 2-3 hearing aid companies globally. Headquartered in Smørum, Denmark.

## Brands
- **Oticon** — Premium hearing aid brand (Real, Intent lines)
- **Bernafon** — Mid-tier brand
- **Sonic** — Value brand
- **Oticon Medical** — Bone-anchored hearing systems
- **HearingLife** — Retail hearing care network

## Technology

### Polaris Platform & DNN Architecture
- **Single-chip approach** — Deliberate architectural choice; Demant argues sufficient compute for their DNN design, in contrast to Sonova's dual-chip DEEPSONIC
- **Dedicated DNN accelerator** — On-chip neural network processing block within the Polaris SoC
- **DNN research history spanning over a decade** — One of the earliest hearing aid companies to pursue deep learning for audio

### DNN Training Data
- **DNN 2.0 trained on 13 million sound scenes** (Oticon Intent, 2024) — up from 12M+ in prior reporting
- Training corpus represents real-world acoustic diversity; earlier Oticon More (2020) used smaller dataset

### BrainHearing Philosophy
- Core product philosophy: hearing aids should support the brain's natural sound processing rather than pre-selecting sounds
- Contrasts with competitors that emphasize speech-forward beam-forming — Oticon provides the brain more acoustic information and lets neural processing sort it out
- Informs the open-sound paradigm across the product line

### Oticon Intent (Feb 2024) — Sirius Platform & 4D Sensor Technology
The flagship product launching on the new **Sirius platform**, introducing multi-modal sensor fusion:
- **DNN 2.0** — Trained on 12M+ sound scenes (some reporting 13M). Delivers **35% more speech cues** vs. predecessor (Oticon Real).
- **More Sound Intelligence 3.0** — AI scene classifier powering automatic adaptation
- **Head motion sensors** — Detects where the wearer is looking
- **Body motion sensors** — Detects physical activity (walking, sitting, etc.)
- **Conversation activity sensor** — Detects whether the wearer is speaking or listening
- **Acoustic environment sensor** — Classifies the surrounding soundscape
- Together these 4 data streams inform real-time processing — if the wearer turns their head toward a speaker, the device boosts that direction
- **HearAdvisor SoundScore: 4.9/5** — Top consumer/expert rating; received **2025 Expert Choice Award**
- **Integrated NPU** — Dedicated neural processing unit within the Sirius SoC (single-chip approach)

### Oticon Intent miniBTE R (Nov 2025)
- Smaller behind-the-ear rechargeable variant of Intent platform
- Expands the 4D sensor / DNN 2.0 technology to users who prefer the miniBTE form factor

### Oticon Verit (Apr 2026)
- New premium adult hearing aid
- **Second-generation AI sound processing** — successor to DNN 2.0 in Intent
- **Bluetooth LE Audio with Auracast** broadcast support
- **Google Fast Pair** for seamless Android pairing
- First Oticon product with both Auracast and Google Fast Pair
- Signals Demant's commitment to LE Audio ecosystem and cross-platform (iOS + Android) connectivity

### Oticon Play SI (Apr 2026)
- **Pediatric hearing aid** with second-gen AI sound processing
- **4D user-intent sensors** — previously exclusive to adult Intent, now brought to pediatric line
- **Bluetooth LE Audio with Auracast** — first pediatric hearing aid with Auracast; critical for classroom accessibility
- **Made for iPhone (MFi) + Android Fast Pair** — cross-platform connectivity
- Significance: brings flagship-level AI and sensor technology to children for the first time

## Product Timeline
| Year | Product | Key Technology |
|------|---------|----------------|
| 2020 | Oticon More | First Oticon DNN hearing aid |
| Feb 2024 | Oticon Intent | Sirius platform, 4D sensors + DNN 2.0, 35% more speech cues |
| Nov 2025 | Intent miniBTE R | Intent platform, smaller form factor |
| Apr 2026 | Oticon Verit | 2nd-gen AI, Auracast, Google Fast Pair |
| Apr 2026 | Oticon Play SI | Pediatric, 2nd-gen AI, 4D sensors, Auracast |

## Corporate Developments
- **Feb 2025** — Acquired **Ohwerk Group** (77 audiology clinics across Germany), expanding Demant's retail footprint in the German market.

## Market Position
- #1 or #2 globally (neck and neck with Sonova)
- Rated **#1 prescription hearing aid 2026** (industry/consumer ratings)
- Vertically integrated (manufacturer + HearingLife retail)
- Strong research tradition (Eriksholm Research Centre)

## Data Science Relevance
- Polaris single-chip DNN accelerator: architecturally different from Sonova's dual-chip — interesting design tradeoff to track
- 4D sensor fusion (Intent) is the most sophisticated multi-modal input system in hearing aids as of 2025
- DNN trained on 13M sound scenes is among the largest published hearing-specific training datasets
- Over-a-decade head start on DNN research means proprietary training pipelines and labeled datasets competitors lack
- BrainHearing philosophy drives a distinctive ML objective function: preserve acoustic richness vs. maximize speech SNR

## Competitive Dynamics
- **vs. Sonova/Phonak**: Single-chip (Oticon) vs. dual-chip (DEEPSONIC) architecture debate; Oticon rated #1 prescription HA despite Sonova's processing power advantage claim
- **vs. ReSound Vivia**: Both use 13M+ scene training; Oticon scenes vs. ReSound sentences (different training data framing)

## Related Pages
- [[sonova-ag]] — Primary competitor; dual-chip (DEEPSONIC) vs. integrated NPU (Sirius) architectural contrast
- [[on-device-ml-hearing-aids]] — Sirius integrated NPU as key example
- [[auracast-bluetooth-le-audio]] — Verit and Play SI are first Oticon products with Auracast
- [[ws-audiology-signia]], [[gn-hearing-resound]], [[starkey]] — Other major competitors

## Sources
- [Oticon Intent Launch 2024](../sources/oticon-intent-launch-2024.md) — Sirius platform, DNN 2.0, 4D sensors, SoundScore, Expert Choice Award
- [Oticon Verit Launch](../sources/oticon-verit-launch-april-2026.md) — 2nd-gen AI, Auracast, Google Fast Pair
- [Oticon Play SI Launch](../sources/oticon-play-si-pediatric-launch-april-2026.md) — Pediatric 2nd-gen AI with 4D sensors and Auracast
- Research notes on Intent miniBTE R launch, 2026 #1 rating, and Ohwerk acquisition
