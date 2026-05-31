---
title: Demant / Oticon
type: entity
created: 2026-04-15
updated: 2026-05-28
sources: [oticon-intent-launch-2024.md, oticon-verit-launch-april-2026.md, oticon-play-si-pediatric-launch-april-2026.md, oticon-zeal-ite-launch-aaa-2026.md, oticon-play-si-hearingreview-april-2026.md, oticon-zeal-hearingreview-aaa-2026.md, aaa-2026-conference-april.md, oticon-zeal-aaa-2026-details.md, oticon-zeal-full-specs-aaa-2026.md, aaa-2026-convention-full-program-april.md, hearingtracker-2026-premium-rankings.md, oticon-va-portfolio-zeal-intent-verit-may-2026.md, demant-q1-2026-zeal-results-may-2026.md]
related: [sonova-ag.md, ../concepts/on-device-ml-hearing-aids.md, ws-audiology-signia.md, gn-hearing-resound.md, starkey.md, ../concepts/auracast-bluetooth-le-audio.md, aaa-conference.md, ../concepts/synthetic-data-for-hearing-ai.md, ../concepts/eu-ai-act-medical-devices.md, ../concepts/hearing-aid-market-dynamics.md]
tags: [company, manufacturer, oticon, denmark, dnn, brainhearing, single-chip, npu, auracast, le-audio, pediatric, encapsulation, ite, dnn-2-0, earnings, share-shift]
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
- New premium adult hearing aid on **Sirius platform**
- **Second-generation AI sound processing** — successor to DNN 2.0 in Intent
- **MoreSound Intelligence 3.0** — latest generation of AI scene classification and sound processing
- **12dB noise suppression** — 2dB better than Oticon Real, 3dB better than Opn S
- **SuddenSound Stabilizer** — manages sudden loud sounds
- **Bluetooth LE Audio with Auracast** broadcast support
- **Google Fast Pair** for seamless Android pairing
- **Zinc-air disposable battery** styles — differentiator vs rechargeable-only Intent; serves users who prefer traditional batteries
- First Oticon product with both Auracast and Google Fast Pair
- Signals Demant's commitment to LE Audio ecosystem and cross-platform (iOS + Android) connectivity

### Oticon Play SI (Apr 2026)
- **Pediatric hearing aid** with second-gen AI sound processing
- **4D user-intent sensors** — previously exclusive to adult Intent, now brought to pediatric line
- **12dB noise suppression** — same level as adult Verit
- **Bandwidth:** 80Hz–10kHz
- **IP68 rated** — dust and water resistant; critical for pediatric durability
- **Styles:** miniRITE R and miniBTE R
- **Bluetooth LE Audio with Auracast** — first pediatric hearing aid with Auracast; critical for classroom accessibility
- **Made for iPhone (MFi) + Android Fast Pair** — cross-platform connectivity
- **EduMic compatible** — works with Oticon's classroom microphone system alongside Auracast
- Significance: brings flagship-level AI and sensor technology to children for the first time
- **Boys Town Clinical Validation:**
  - **50% improved sentence recognition** in noise (Boys Town National Research Hospital)
  - **77% reduced listening difficulty** for teenagers
  - Study conducted at one of the most respected pediatric audiology research centers
  - Strongest clinical evidence to date for AI in pediatric hearing aids

### Oticon Zeal (Apr 2026 — AAA 2026 debut)
- **"World's most discreet, complete hearing aid"** — nearly invisible rechargeable ITE
- **DNN 2.0 always-on AI on Sirius chip** — same silicon as flagship Intent; full AI processing parity with BTE/RIC despite tighter ITE power/thermal constraints
- **Encapsulation technology** — novel manufacturing/sealing approach for ITE durability; addresses moisture/cerumen ingress challenges
- **Bluetooth LE Audio + Auracast-ready** — completes Oticon's full-lineup Auracast rollout across all form factors
- **20-hour battery life** with quick-charge (15 min = 4 hours) — addresses historical battery anxiety of rechargeable ITEs
- **Fitting options:** Instant-fit option (enables same-day dispensing) + micro-earmold custom option
- **Tap controls via motion sensor** — eliminates physical buttons for discreet form factor
- **Fitting range:** Rated up to ~75 dB hearing loss (mild to moderately severe)
- Debuting at the **AAA 2026 conference** (April 22-25, San Antonio, TX). See [[aaa-conference]].
- Complements the BTE/RIC lineup (Intent, Verit) and pediatric (Play SI) with an ITE option for users who prefer in-ear cosmetics
- Most technologically advanced ITE hearing aid to date (DNN 2.0 + Auracast + encapsulation + 20hr battery in ITE form)

## Product Timeline
| Year | Product | Key Technology |
|------|---------|----------------|
| 2020 | Oticon More | First Oticon DNN hearing aid |
| Feb 2024 | Oticon Intent | Sirius platform, 4D sensors + DNN 2.0, 35% more speech cues |
| Nov 2025 | Intent miniBTE R | Intent platform, smaller form factor |
| Apr 2026 | Oticon Verit | Sirius, 2nd-gen AI, 12dB NR, Auracast, zinc-air, SuddenSound Stabilizer |
| Apr 2026 | Oticon Play SI | Pediatric, 2nd-gen AI, 4D sensors, 12dB NR, Auracast, IP68, EduMic |
| Apr 2026 | Oticon Zeal | Rechargeable ITE, DNN 2.0 on Sirius, 20hr battery, Auracast, tap controls — AAA 2026 debut |

## Corporate Developments
- **Feb 2025** — Acquired **Ohwerk Group** (77 audiology clinics across Germany), expanding Demant's retail footprint in the German market.
- **Apr 2026** — Oticon donating **$30K to AAA Foundation** for student scholarships, investing in the audiology workforce pipeline.
- **May 2026** — **VA portfolio expansion** ([[../sources/oticon-va-portfolio-zeal-intent-verit-may-2026]]): Zeal (ITE), Intent miniBTE R, and Verit added to the U.S. Department of Veterans Affairs supply schedule. Material distribution win — VA is the world's second-largest hearing-aid dispenser after the UK NHS, and the largest single US payer — and gives VA audiologists the broadest Oticon form-factor range to date. Part of a structural three-OEM convergence (Oticon + Signia + Starkey) on the VA contract within seven days in mid-May 2026; see [[../syntheses/va-as-hearing-ai-dataset-may-2026]] for the closed-loop dataset framing.
- **May 2026 — Q1 2026 results** ([[../sources/demant-q1-2026-zeal-results-may-2026]]): Total revenue **+16%** (vs. consensus +13.5%) = **+6% organic + +10% acquisitions**. Hearing Aids organic growth from external customers **+9%**, driven by the global Zeal rollout. Gross margin expanded on higher ASPs and mix. Shares jumped **~11%** on the print. **2026 outlook held at 3–6% organic growth / DKK 4.1–4.5B EBIT before specials**, with management noting results at the low end now look "less likely" — implicit upward skew within the band. On track for DKK 250M cost savings in 2026 (DKK 500M total by 2028). Demant's reported world-market read: **HA market +4% value (+3% units, +1% ASP)** — at the **top end** of their 2–4% 2026 range. With 9% organic vs. 3% global units, **Demant took share in Q1**. Combined with Sonova's FY 2025/26 print two weeks prior, this is the second consecutive top-of-band data point on the 2026 HA value cycle — see [[../concepts/hearing-aid-market-dynamics]] and [[../syntheses/hearing-aid-market-outlook]].

## Market Position
- #1 or #2 globally (neck and neck with Sonova)
- Rated **#1 prescription hearing aid 2026** (industry/consumer ratings)
- **HearingTracker 2026 premium ranking: #3** (Oticon Intent) — behind Phonak Infinio Sphere (#1) and Starkey Genesis AI (#2). Note: Oticon Verit and Zeal (both April 2026) may not yet be reflected in these rankings
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
- [[auracast-bluetooth-le-audio]] — Verit, Play SI, and Zeal all ship with Auracast — full-lineup rollout
- [[aaa-conference]] — Zeal debut at AAA 2026 (San Antonio, Apr 22-25); $30K scholarship donation
- [[synthetic-data-for-hearing-ai]] — Synthetic data distillation could expand Oticon's 13M scene training corpus
- [[ws-audiology-signia]], [[gn-hearing-resound]], [[starkey]] — Other major competitors

## Sources
- [Oticon Intent Launch 2024](../sources/oticon-intent-launch-2024.md) — Sirius platform, DNN 2.0, 4D sensors, SoundScore, Expert Choice Award
- [Oticon Verit Launch](../sources/oticon-verit-launch-april-2026.md) — 2nd-gen AI, Auracast, Google Fast Pair
- [Oticon Play SI Launch](../sources/oticon-play-si-pediatric-launch-april-2026.md) — Pediatric 2nd-gen AI with 4D sensors and Auracast
- [Oticon Play SI — Hearing Review](../sources/oticon-play-si-hearingreview-april-2026.md) — Boys Town: 50% improved sentence recognition, 77% reduced listening difficulty
- [Oticon Zeal ITE Launch (HHTM)](../sources/oticon-zeal-ite-launch-aaa-2026.md) — Rechargeable ITE with streaming at AAA 2026
- [Oticon Zeal at AAA 2026 (Hearing Review)](../sources/oticon-zeal-hearingreview-aaa-2026.md) — Encapsulation tech, 2nd-gen AI confirmed, Auracast confirmed
- [AAA 2026 Conference](../sources/aaa-2026-conference-april.md) — Conference context for Zeal debut
- [AAA 2026 Full Program](../sources/aaa-2026-convention-full-program-april.md) — $30K scholarship donation, 200+ sessions
- [Oticon Zeal Full Specs](../sources/oticon-zeal-full-specs-aaa-2026.md) — DNN 2.0, Sirius chip, 20hr battery, 75 dB range, tap controls
- [HearingTracker 2026 Premium Rankings](../sources/hearingtracker-2026-premium-rankings.md) — Oticon Intent ranked #3
- Research notes on Intent miniBTE R launch, 2026 #1 rating, and Ohwerk acquisition
- [Demant Q1 2026 Results (May 2026)](../sources/demant-q1-2026-zeal-results-may-2026.md) — 16% total / 6% organic / 9% HA organic ex-customers; outlook held, low-end "less likely"; market read +4% value at top of band; share taken vs. global units
