# Wiki Log

Chronological record of all wiki operations.

---

## 2026-05-08 — INGEST (Daily hearing+AI digest)

**Operation:** INGEST (daily email digest research, hearing + AI)

**Sources added (3):**
- `spatial-magnifier-multichannel-se-arxiv-2026.md` — Lee, Pandey, Parekh, Wong, Donley, Xu, Azcarreta (Meta Reality Labs); learned spatial upsampling for multichannel SE on small wearable mic arrays. Tackles the mic-spacing wall that bounds wearable beamformer selectivity.
- `ndf-plus-neural-directional-filtering-arxiv-2026.md` — Huang, Huynh, Thiergart, Habets (Fraunhofer IIS / FAU Erlangen-Nürnberg); joint neural directional filtering + diffuse-sound extraction in a single network. Addresses cocktail-party scenes that are simultaneously directional + diffuse.
- `predictive-generative-drift-decomposition-arxiv-2026.md` — Richter, Masuyama, Boeddeker, Edo, Wichern, Le Roux (MERL / U Hamburg / Paderborn); decomposes SE into predictive (mask) + generative drift components. Addresses the "robotic over-suppression" failure mode of HA DNN noise reduction; gives a personalization knob between fidelity and comfort.

**Sources reused (no duplicates created):**
- `apple-hearing-study-results-may-2026.md` — May 1 Apple Hearing Study findings (n=160k, 16% perception gap in WHO-normal hearing, 57k mobility sub-analysis) already covered as a full source from a prior ingest.
- `codec-intelligibility-se-behringer-arxiv-2026.md` — Behringer et al. May 2026 codec/SE intelligibility paper already in wiki.
- `starkey-omega-ai-big-ai-awards-2026.md` — Starkey 2026 BIG Innovation Awards already covered.
- `aci-alliance-ci2026.md` (entity) — ACI Alliance / CI2026 entity page exists; Caraway Lifetime Achievement (May 7) noted in digest only, no source-file work needed for a single award announcement.

**Pages updated (2):**
- `concepts/speech-enhancement-neural-networks.md` — Added the 3 new arXiv-May-2026 papers to `sources:` frontmatter, expanded the "Recent Academic Advances (2024–2026)" section with three new subsections (Spatial-Magnifier, NDF+, Predictive-Generative Drift Decomposition), and appended source links. Updated date to 2026-05-08.
- `wiki/index.md` — New last-updated banner entry for today's digest ingest. Prior 2026-05-08 LinkedIn-drafts banner moved to "Earlier 2026-05-08 entry."

**Index/log:**
- Updated `wiki/index.md` last-updated banner.
- Appended this log entry.

**Underlying email digest (08 May 2026, sent to door.punch_4o@icloud.com):**
- 📄 Research: Spatial-Magnifier, NDF+, Predictive-Generative Drift Decomposition, Behringer codec-intelligibility paper.
- 📰 Industry: Apple Hearing Study May-1 findings (n=160k), Starkey 2026 BIG Innovation Awards (Omega AI + Sawalich), Caraway ACI Alliance Lifetime Achievement (CI2026, May 7).
- 🤖 AI/ML: Gemma 3n on-device multimodal SLM with native audio input.
- 💡 Worth Watching: Clarity Prediction Challenge 3 (CPC3) wave of submissions — non-intrusive intelligibility prediction is the missing piece for closed-loop on-device HA fitting.
- 📊 Quick Stats: Apple Hearing Study cohort numbers + CPC3 leaderboard RMSE.

**Notes:**
- Genuinely quiet day on the industry side; centre of gravity was the May-2026 arXiv eess.AS listing. Avoided repeating yesterday's items (Connect Hearing → AudioNova rebrand, AAA 2026 leadership panel, Phonak Virto R Infinio design awards, Liquid AI LFM2.5-Audio, Auracast UK rollout, FHH Conference) by cross-checking against the 2026-05-07 log entry.
- Three arXiv papers were verified via the May 2026 eess.AS listing page; specific arXiv IDs were not yet resolvable from the listing-page snapshot and are flagged for backfill.

---

## 2026-05-08 — INGEST (LinkedIn drafting research)

**Operation:** INGEST (LinkedIn post research, daily)

**Sources added (1):**
- `hearing-aid-cortical-reorganization-meg-frontiers-2026.md` — Becker, Voss, Martinez-Moreno, Prévost, Zeitouni, Lopez Valdes, de Villers-Sidani; *Frontiers in Aging Neuroscience*, 16 Apr 2026; n=12 older adults, MEG before/after 3 months bilateral HA wear; right-hemisphere cortical activity reduction (effect sizes 0.61–1.00) with left-hemisphere reductions correlating with individual speech-in-noise improvement.

**Sources expanded (1):**
- `remote-ci-programming-real-life-frontiers-2026.md` — Promoted from minimal stub to full extraction. Added authors (Snoeck, Brendel, Wasmann), publication date (22 Apr 2026), Radboud UMC affiliation, n=12 study design with 4-session protocol, COSI numbers (10 "much better" / 8 "better" / 4 "a little better" / 12 no improvement across 37 goals), satisfaction breakdown, Advanced Bionics Target CI v1.5 toolchain, and the ecological-validity reframing (clinic-equivalent → labeled triple of settings × in-situ context × COSI outcome).

**New wiki pages (1):**
- `concepts/cortical-reorganization-hearing-aids.md` — New concept page anchored on the Becker et al. headline result. Frames the cortex as the actual prosthetic target; outcome implications for audiogram and clinical-visit cadence; telemetry-as-cortical-efficiency-proxy hypothesis; open research questions on AI-fitting interaction with adaptation curve and DNN-noise-reduction timing.

**Pages updated (2):**
- `concepts/longitudinal-hearing-phenotyping.md` — Added new MEG source to `sources:`, `cortical-reorganization-hearing-aids.md` to `related:`, `neuroplasticity` tag, "Cortical efficiency proxies" bullet to Core Signals, and a Sources entry for the Becker paper. Updated date to 2026-05-08.
- `concepts/teleaudiology.md` — Replaced the prior thin Snoeck et al. summary with the full extraction: n=12, COSI numbers, ecological-validity reframing, labeled-triple data-science implication, and the 22 Apr 2026 publication date. Updated date to 2026-05-08.

**Index/log:**
- Updated `wiki/index.md` last-updated banner and appended new concept-page row.
- Appended this log entry.

**Underlying LinkedIn posts (08 May 2026):**
- Post 1: Remote CI programming in real-life environments — the labeled training set hiding inside ecological validity. Reframes the ~14% Dutch adoption flatline by showing that what makes in-situ remote care valuable is the (settings × context × COSI) triple it generates, not clinic-equivalence.
- Post 2: 12-week cortical reorganization from HA wear — outcome measurement is on the wrong variable. Argues the cortex is the prosthetic target, the audiogram is the wrong variable, and telemetry could approximate the MEG-measured cortical-efficiency signal at zero marginal cost.

**Notes:**
- Both papers are May-2026-fresh and complementary: one operations/data, one biology/measurement. Neither overlapped with prior posts on Apple Hearing Study, Pickleball, CI2026 Chicago, JAMA preimplant MRI, or digital phenotyping.
- General AI/ML angle (e.g., Karpathy nanochat, ElevenLabs, Phi-4 / Gemma) was researched but deliberately not forced into either post; the Becker MEG paper carried its own data-science framing on the brain side and the Snoeck CI paper carried it on the operational side.
- Discord confirmation message: 4 messages posted (2 meta + 2 body) to channel 1492462147127742565. Email sent to door.punch_4o@icloud.com.

---

## 2026-05-07 — INGEST (LinkedIn drafting research)

**Operation:** INGEST (LinkedIn post research, daily)

**Sources added (1):**
- `jmir-ai-wearables-cognitive-impairment-2026.md` — JMIR systematic review (Feb 23 2026, e86262); 49 studies on AI + wearables for early detection of cognitive impairment and dementia. Establishes the digital phenotyping framing as the field-defining shift.

**Sources reused (no duplicates created):**
- `ai-cochlear-implant-language-prediction-2025.md` and `ai-predicts-ci-language-outcomes.md` — both already cover the JAMA Otolaryngology / Northwestern preimplant-MRI deep-transfer-learning paper used for LinkedIn Post 1; no new source file needed.

**New wiki pages (1):**
- `concepts/digital-phenotyping-cognitive-decline.md` — Concept page covering the digital phenotyping framework, why hearing aids are an underused substrate (vs wrist devices), a hearing-aid-native feature set table, methodological challenges from the JMIR review, and the strategic choice facing manufacturers.

**Pages updated (2):**
- `concepts/hearing-loss-dementia-link.md` — Added JMIR source to `sources:`; added `digital-phenotyping-cognitive-decline.md` to `related:`; added `digital-phenotyping` tag.
- `concepts/longitudinal-hearing-phenotyping.md` — Added `digital-phenotyping-cognitive-decline.md` to `related:`.

**Index/log:**
- Updated `wiki/index.md` last-updated banner and added the new concept-page row.
- Appended this log entry.

**Underlying LinkedIn posts (07 May 2026):**
- Post 1: AI predicts cochlear implant language outcomes before surgery — JAMA Otolaryngology / Northwestern preimplant MRI study (timed to CI2026 Chicago opening today). 92% accuracy, deep transfer learning, "predict, then prescribe" workflow framing.
- Post 2: Hearing aids as the underused substrate for digital phenotyping — Feb 2026 JMIR systematic review (49 studies) reframed as a strategic opportunity for hearing-aid telemetry.

---

## 2026-05-05 — INGEST (LinkedIn drafting research)

**Operation:** INGEST (LinkedIn post research)

**Sources added (2):**
- `ci2026-chicago-robinson-keynote-may-2026.md` — ACI Alliance announcement of Dr. James A. Robinson (2024 Nobel laureate in Economic Sciences) as keynote speaker at CI2026 Chicago, May 7–9, 2026
- `phonak-pickleball-aaa-2026-deeper-coverage.md` — Hearing Review (Apr 27 2026) deeper coverage of Phonak × USA Pickleball "Hear to Win" campaign formally announced at AAA 2026; Sphere Sound Lab activation, executive quotes, ~20M player audience

**New wiki pages (2):**
- `entities/aci-alliance-ci2026.md` — American Cochlear Implant Alliance and CI2026 Chicago conference overview
- `syntheses/cochlear-implant-access-economics.md` — Synthesis on why institutions, not technology, are the binding constraint on CI utilization, and where data science can move the needle

**Pages updated (4):**
- `entities/phonak.md` — Expanded Hear to Win section with announcement date, audience scale, Sphere Sound Lab, executive quotes, and the underexplored data-science angle
- `concepts/cochlear-implant-ai.md` — Added cross-links to ACI Alliance and CI access economics synthesis
- `entities/cochlear-ltd.md` — Added cross-links to ACI Alliance and CI access economics synthesis
- `concepts/audiologist-workforce-shortage.md` — Added cross-link to CI access economics synthesis (workforce as shared bottleneck across hearing aids and CIs)

**Underlying LinkedIn posts:**
- Post 1: Phonak × USA Pickleball as a real-world acoustic benchmark suite
- Post 2: CI2026 Chicago keynote by Robinson — institutional economics applied to CI access

---

## 2026-04-26 — LINT PASS

**Operation:** LINT (comprehensive health check)

**Stats:**
- Total wiki pages: 62 (33 concepts, 20 entities, 4 comparisons, 5 syntheses)
- Total source files: ~130
- Broken cross-references: **0**
- Orphan pages found: **2** (fixed: 2)
- Stale sources flagged: **3 pages** (1 fast-moving topic source, 12 months old)
- Duplicate source files: **2 pairs**
- Potential concept merges: **2 pairs** (flagged for human review)
- Oversized pages (>15KB): **4** (flagged for possible splitting)

**Fixes applied (auto):**

1. **Orphan fixed — `entities/who-hearing-program.md`:**
   - Added incoming link from `concepts/audiologist-workforce-shortage.md` (related: + body mention)

2. **Orphan fixed — `syntheses/hearing-ai-research-landscape-2025.md`:**
   - Added incoming link from `syntheses/hearing-aid-ai-stack-2026.md` (related:)
   - Added incoming link from `entities/vcca-computational-audiology.md` (related: + body mention)

**Issues requiring human judgment:**

1. **Stale source on fast-moving topics:**
   - `tinyml-speech-recognition-arduino-2025.md` (April 2025, 12 months old) cited in:
     - `concepts/on-device-ml-hearing-aids.md`
     - `concepts/tinyml-edge-ai.md`
     - `syntheses/hearing-aid-ai-stack-2026.md`
   - Recommendation: ingest a more recent TinyML/edge-AI source (2026) to update these claims

2. **Potential concept merges:**
   - `concepts/dnn-in-hearing-aids.md` (17KB) vs `concepts/dnn-architectures-hearing-aids.md` (9.7KB)
     - Overlap: both cover DNN in hearing aids. Distinction: `dnn-in-hearing-aids` is broader (clinical evidence, applications, history); `dnn-architectures` focuses on specific architecture types (CRN, transformer, SSM). Currently cross-linked. Merge if the distinction collapses.
   - `concepts/state-space-models.md` vs `concepts/mamba-architecture.md`
     - Share all 4 source files. SSMs is the category; Mamba is the leading implementation. Keep separate but consider whether Mamba warrants its own page vs. a section in SSMs.

3. **Duplicate source files (sources/ directory):**
   - `sources/ai-audiology-scoping-review.md` + `sources/ai-audiology-scoping-review-2024.md`
   - `sources/signia-ix-platform.md` + `sources/signia-ix-platform-2024.md`
   - Recommendation: verify if these are the same source ingested twice under different names; consolidate if so.

4. **Oversized pages (candidates for splitting):**
   - `concepts/speech-enhancement-neural-networks.md` (19.7KB) — could split: "architectures" vs. "training/evaluation benchmarks"
   - `concepts/dnn-in-hearing-aids.md` (17.6KB) — could split: "clinical evidence/deployment" vs. "DNN applications"
   - `concepts/cochlear-implant-ai.md` (16.3KB) — could split: "AI for CI signal processing" vs. "CI ecosystem/companies"
   - `syntheses/hearing-aid-ai-stack-2026.md` (16.2KB) — synthesis pages can grow large; acceptable

---

## 2026-04-26 — LinkedIn Drafts Ingestion (1 source, 2 concepts, 1 entity)

**Operation:** INGEST (LinkedIn post draft research — 1 new source, 2 new concept pages, 1 new entity)

**Sources created (1 new):**
1. `cochlear-nucleus-nexa-smart-implant-2026.md` — World's first cochlear implant with upgradeable firmware and on-implant memory; Cochlear Ltd. (Aus); VA availability Jan 2026; AAA 2026 showcase

**Concept pages created (2 new):**
1. `wiki/concepts/software-defined-medical-implants.md` — New concept formalizing the post-implant updateability category; MLOps stack for in-vivo devices; FDA TPLC/PCCP framing; trajectory for hearing aids
2. `wiki/concepts/longitudinal-hearing-phenotyping.md` — New concept for the multi-modality measurement substrate (gene therapy, CIs, hearing aids); motivated by 2.5-year OTOF durability data

**Entity pages created (1 new):**
1. `wiki/entities/cochlear-ltd.md` — Largest CI manufacturer globally; Nucleus Nexa product line; competitive landscape

**Pages updated (3):**
1. `wiki/concepts/cochlear-implant-ai.md` — Added Nexa to Key Manufacturers section; added 3 cross-references and 1 new source link
2. `wiki/concepts/gene-therapy-hearing.md` — Added longitudinal-hearing-phenotyping cross-reference (measurement layer for durability)
3. `wiki/index.md` — Added 2 new concepts, 1 new entity to catalog; updated last-updated banner

**Driver:** Daily LinkedIn drafts (Apr 26) on (a) OTOF gene therapy 2.5-year durability and the longitudinal phenotyping problem; (b) Cochlear Nucleus Nexa as software-defined cochlear implant. Both posts emerge from this week's news (Nature paper Apr 22, AAA 2026 Apr 22-25). Existing source `harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md` was reused — the new concept pages provide the wiki layer above the raw sources.

---

## 2026-04-25 — Daily Hearing+AI Research Digest Ingestion (10 sources)

**Operation:** INGEST (daily digest — 10 sources)

**Sources created (10 new):**
1. `target-speaker-extraction-ultra-low-latency-2026.md` — Hsu et al., sub-5ms causal TSE using speaker embeddings for hearing assistive devices
2. `efficient-on-device-speech-enhancement-qat-2026.md` — INT8 QAT for speech enhancement, 3x ARM speedup, minimal quality loss
3. `ssl-pretraining-robust-ha-speech-enhancement-2026.md` — SSL pre-training on unlabeled audio improves generalization to unseen noise
4. `auracast-european-public-venue-rollout-2026.md` — Bluetooth SIG: European airports, transit, NHS clinics piloting Auracast 2026-2027
5. `eu-ai-act-medical-device-compliance-2026.md` — EU AI Act Class IIa provisions entering compliance period for AI hearing aids
6. `hearingtracker-2026-premium-rankings.md` — HearingTracker 2026 premium rankings: Phonak #1, Starkey #2, Oticon #3
7. `mamba-ssm-audio-traction-2026.md` — Mamba SSM adoption accelerating across audio/speech enhancement research
8. `qualcomm-s5-s3-gen3-sound-platforms-2026.md` — Transformer-based ANC at sub-3ms in premium TWS earbuds
9. `lc3plus-codec-broader-implementation-2026.md` — LC3plus codec broader adoption for LE Audio music streaming
10. `samsung-galaxy-buds-health-monitoring-ppg-2026.md` — Samsung Galaxy Buds in-ear PPG for HRV and stress tracking

**Pages created (1 new):**
- `wiki/concepts/eu-ai-act-medical-devices.md` — EU AI Act Class IIa regulation: compliance requirements, impact on OTA DNN updates, competitive effects, connection to existing MDR and European Accessibility Act

**Pages updated (15 existing):**
1. `wiki/concepts/speech-enhancement-neural-networks.md` — Added TSE (Hsu et al. sub-5ms), SSL pre-training, INT8 QAT sections; new sources and cross-refs
2. `wiki/concepts/auracast-bluetooth-le-audio.md` — European public venue rollout (airports, transit, NHS), LC3plus codec, updated venue adoption status
3. `wiki/concepts/model-compression.md` — QAT evidence for speech enhancement (3x ARM speedup), new source
4. `wiki/concepts/mamba-architecture.md` — Broader adoption momentum section, new source
5. `wiki/concepts/state-space-models.md` — Mamba adoption acceleration note, new source
6. `wiki/concepts/active-noise-cancellation.md` — Qualcomm S5/S3 Gen 3 transformer-based ANC at sub-3ms, new source
7. `wiki/concepts/hearing-aid-chip-architectures.md` — Qualcomm consumer chip benchmark section, new source
8. `wiki/concepts/on-device-ml-hearing-aids.md` — TSE as emerging capability, Samsung Galaxy Buds health monitoring, new sources
9. `wiki/concepts/hearing-aid-market-dynamics.md` — EU AI Act and HearingTracker sources, cross-ref
10. `wiki/concepts/dnn-in-hearing-aids.md` — EU AI Act cross-reference
11. `wiki/concepts/auditory-attention-decoding.md` — TSE source added (TSE + AAD connection)
12. `wiki/entities/phonak.md` — HearingTracker #1 ranking, EU AI Act cross-ref, new source
13. `wiki/entities/starkey.md` — HearingTracker #2 ranking, Samsung Galaxy Buds competitive context, new sources
14. `wiki/entities/demant-oticon.md` — HearingTracker #3 ranking, EU AI Act cross-ref, new source
15. `wiki/comparisons/ai-hearing-aid-platforms-2026.md` — HearingTracker rankings section, EU AI Act compliance section, new watch items, new sources
16. `wiki/syntheses/hearing-aid-ai-stack-2026.md` — Auracast EU rollout, Samsung health, EU AI Act, TSE, Qualcomm consumer chip pressure; 10 new sources
17. `wiki/index.md` — Added EU AI Act page, updated dates for 10 modified pages

**Key themes from this digest:**
- Speech enhancement research advancing on three fronts: target speaker extraction (personalized listening), SSL pre-training (better generalization), and QAT (efficient deployment)
- Auracast transitioning from individual venue pilots to systematic European public infrastructure deployment; NHS adoption is a major validation signal
- EU AI Act introduces first binding AI regulation for hearing aids — compliance burden but also clinical evidence catalyst
- Mamba/SSM adoption accelerating from proof-of-concept to emerging default for audio AI research
- Consumer chip parity pressure intensifying: Qualcomm transformer ANC at sub-3ms, Samsung earbud health monitoring — narrowing the gap with hearing aid capabilities from below
- HearingTracker 2026 rankings confirm AI is table stakes for premium hearing aids

---

## 2026-04-25 — LinkedIn Post Research Ingestion: Otarmeni Gene Therapy, Harvard/Fudan OTOF Study, Google Gemma 4

**Operation:** INGEST (LinkedIn post research — 3 sources)

**Sources created (3 new):**
1. `otarmeni-fda-gene-therapy-approval-april-2026.md` — FDA approved Otarmeni (Regeneron), first gene therapy for genetic hearing loss (OTOF mutations); 80% efficacy at 24 weeks; 61-day approval via National Priority Voucher; free in US
2. `harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md` — Nature study: 90% hearing improvement, 50% normal hearing at 2.5 years; Harvard/Mass Eye and Ear + Fudan; strongest gains in patients ≤18
3. `google-gemma-4-open-models-april-2026.md` — Gemma 4 family: E2B/E4B/26B MoE/31B Dense; Apache 2.0; native audio+vision; 140+ languages; runs on phones/Raspberry Pi/Jetson; Gemini Nano 4 built on it (4x speed, 60% less battery)

**Pages created (2 new):**
- `wiki/concepts/gene-therapy-hearing.md` — Gene therapy for hearing loss: OTOF paradigm, dual AAV mechanism, clinical results (Otarmeni + Harvard/Fudan), pipeline (~200 deafness genes), CI candidacy impact, AI/ML connections
- `wiki/entities/regeneron.md` — Regeneron Pharmaceuticals: Otarmeni manufacturer, first pharma entry into hearing loss treatment with approved gene therapy

**Pages updated (9 existing):**
- `wiki/entities/google-research.md` — Gemma 4 family details, Gemini Nano 4 efficiency gains, new source and cross-refs
- `wiki/concepts/precision-drug-delivery-inner-ear.md` — Gene therapy section (no longer speculative for OTOF), Otarmeni + Harvard/Fudan data, new sources and cross-refs
- `wiki/concepts/cochlear-implant-ai.md` — Gene therapy CI candidacy impact, Regeneron cross-ref, new sources
- `wiki/concepts/small-language-models-edge-ai.md` — Gemma 4 entry (E2B/E4B/26B MoE/31B, native audio, edge deployment), new source
- `wiki/concepts/mixture-of-experts.md` — Gemma 4 26B MoE variant, Google Research cross-ref, new source
- `wiki/concepts/model-compression.md` — Gemma 4 as distillation teacher source added
- `wiki/concepts/on-device-ml-hearing-aids.md` — Gemma 4 source added
- `wiki/concepts/hearing-aid-market-dynamics.md` — Gene therapy market impact section (Otarmeni, ~200 gene pipeline, CI volume implications), Regeneron cross-ref, new source
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — Gene therapy and Gemma 4 in "What's Coming Next," 3 new sources and cross-refs

**Index updated:** 2 new pages added (gene-therapy-hearing concept, regeneron entity); 9 existing pages updated with new dates

**Cross-references added:** ~25

**Key narrative threads:**
1. **Gene therapy enters hearing loss treatment:** Otarmeni's FDA approval marks the first curative therapy for any form of hearing loss. While near-term impact is limited to OTOF mutations (~2-8% of prelingual cases), the pipeline of ~200 deafness genes represents a paradigm shift from management to cure for genetic forms. The Harvard/Fudan 2.5-year data (50% achieving normal hearing) is remarkable.
2. **Pharma enters hearing ecosystem:** Regeneron is the first pharmaceutical company with an approved hearing loss treatment, introducing a new competitive axis alongside hearing aid manufacturers and consumer tech companies.
3. **Gemma 4 validates multimodal edge AI trajectory:** Native audio processing in a 2B-parameter Apache 2.0 model, running on Raspberry Pi, continues the compression trajectory toward hearing device-scale AI. The 26B MoE variant adds another MoE data point alongside Qwen3.6. Gemini Nano 4's 4x speed and 60% battery reduction on Android demonstrates that architecture improvements (not just compression) can dramatically reduce power — the key hearing device constraint.

**Disk space note:** Machine disk nearly full (290MB free). Cleared npm cache (+60MB). Further cleanup may be needed.

---

## 2026-04-24 — Batch Ingestion: AAA 2026 Full Program, Oticon Zeal Specs, Starkey AAA Showcase, Meta Synthetic Data, Phonak Pickleball

**Operation:** INGEST (batch — 5 sources)

**Sources created (5 new):**
1. `aaa-2026-convention-full-program-april.md` — AAA 2026 full program: 200+ sessions, 130+ exhibitors, 16 tracks, Dr. Hassan Tetteh keynote ("The Art of Human Care"), new "Amplify Your Value" track, Oticon $30K scholarship donation
2. `oticon-zeal-full-specs-aaa-2026.md` — Oticon Zeal complete specs: DNN 2.0 on Sirius chip, 20-hour battery, 15-min quick-charge, instant-fit + micro-earmold, tap controls, ~75 dB fitting range, Bluetooth LE Audio + Auracast
3. `starkey-omega-ai-aaa-2026-showcase.md` — Starkey Omega AI showcased at AAA 2026: Auracast, AI-driven sound processing, health/wellness integration (fall detection, activity, respiratory rate, heart rate)
4. `meta-synthetic-data-distillation-april-2026.md` — Meta synthetic data distillation: recursive large-model-to-small-model pipeline, distilled/quantized edge models for phones/AR/IoT, hearing AI implications for training data scarcity
5. `phonak-usa-pickleball-partnership-spring-2026.md` — Phonak "Hear to Win" campaign with USA Pickleball, spring 2026 tournament season, consumer-brand marketing strategy

**Pages created (1 new):**
- `wiki/concepts/synthetic-data-for-hearing-ai.md` — Synthetic data generation for hearing AI: training data bottleneck, Meta recursive distillation, privacy-preserving training, data moat disruption potential

**Pages updated (9 existing):**
- `wiki/entities/aaa-conference.md` — Updated dates (Apr 22-25), keynote (Dr. Tetteh), scale (200+ sessions, 130+ exhibitors, 16 tracks), Starkey Omega AI showcase, scholarship donation, new sources
- `wiki/entities/demant-oticon.md` — Zeal: DNN 2.0 confirmed on Sirius chip, 20hr battery, 15-min quick-charge, tap controls, ~75 dB range, instant-fit; $30K scholarship donation; new sources and cross-refs
- `wiki/entities/starkey.md` — AAA 2026 Showcase section (three pillars: Auracast + AI audio + health), new source
- `wiki/entities/phonak.md` — "Hear to Win" USA Pickleball partnership section, new source and cross-refs
- `wiki/concepts/on-device-ml-hearing-aids.md` — Synthetic data distillation entry in Training Data Scales, new source and cross-refs
- `wiki/concepts/dnn-in-hearing-aids.md` — DNN 2.0 in ITE section (Zeal), synthetic data moat disruption note, new sources and cross-refs
- `wiki/concepts/auracast-bluetooth-le-audio.md` — Zeal BLE Audio + Auracast confirmed, Starkey AAA showcase, new sources
- `wiki/concepts/model-compression.md` — Synthetic data cross-reference added
- `wiki/index.md` — 1 new concept page added; 9 existing pages updated with new dates

**Cross-references added:** ~25

**Key narrative threads:**
1. **DNN 2.0 achieves form-factor parity:** Oticon Zeal confirms the same Sirius chip and DNN 2.0 running in the smallest (ITE) form factor as in the flagship Intent BTE — validating Demant's single-chip efficiency for constrained designs
2. **AAA 2026 is the biggest yet:** 200+ sessions, 130+ exhibitors, 16 tracks; Dr. Tetteh's keynote explicitly addresses AI-empathy balance in healthcare
3. **Synthetic data could break the training data moat:** Meta's recursive distillation pipeline could enable smaller hearing aid companies to approach Big 6 training data scale (12M-22M scenes) without expensive real-world data collection
4. **Starkey three-pillar positioning solidified at AAA:** Connectivity (Auracast) + AI audio (G3 NPU) + health monitoring (4 biometrics) — showcased together at AAA 2026
5. **Consumer marketing enters hearing aids:** Phonak's USA Pickleball partnership represents a shift from clinical-channel-only marketing to lifestyle/sports brand awareness, targeting the 50+ demographic overlap

---

## 2026-04-23 — Digest Ingestion: CI Speech Enhancement (DAT-CFTNet, TokenSE/Mamba), ANC Smart Glasses, GAP-URGENet, Phonak/Starkey Updates, TinyML

**Operation:** INGEST (digest — 8 sources)

**Sources created (8 new):**
1. `dat-cftnet-ci-speech-enhancement-icassp-2026.md` — Mamun & Hansen (ICASSP 2026, arXiv:2604.06744): Attention-based dual-path RNN for CI speech enhancement; outperforms CFTNet/DCCRN, eliminates musical artifacts
2. `tokense-mamba-ci-speech-enhancement-2026.md` — Chiang & Hansen (arXiv:2604.12246): First Mamba-based discrete token speech enhancement for CI; O(n) linear complexity, subjective CI user validation
3. `anc-open-ear-smart-glasses-cmu-2026.md` — Yuan, Liu et al. (CMU, arXiv:2604.05519): First real-time ANC for open-ear smart glasses; 9.6 dB reduction, 8 distributed mics, 100-1000 Hz
4. `gap-urgenet-urgent-challenge-icassp-2026.md` — Won 1st place URGENT 2026 Challenge (ICASSP); generative-predictive fusion for universal speech enhancement
5. `oticon-zeal-aaa-2026-details.md` — Oticon Zeal ITE with encapsulation tech, rechargeable, Auracast demos at AAA 2026 (Apr 22-24, San Antonio)
6. `phonak-ai-excellence-award-march-2026.md` — Virto R Infinio and Infinio Ultra Sphere won 2026 AI Excellence Award; Ultra Sphere DNN direct speech/noise separation
7. `starkey-omega-ai-auracast-update-jan-2026.md` — Omega AI: Auracast Assistant, Google Fast Pair, Push to Talk, respiratory rate tracking (Jan 2026 rollout)
8. `tinyml-speech-recognition-arduino-2025.md` — Barovic & Moin (arXiv:2504.16213): 97% accuracy, 23 keywords on Arduino Nano 256KB RAM

**Pages created (3 new):**
- `wiki/concepts/mamba-architecture.md` — Mamba (selective SSM) for audio AI: TokenSE as first CI application, architectural comparison with Transformers/S4, CIM co-design trajectory
- `wiki/concepts/active-noise-cancellation.md` — ANC in hearing devices: dual-layer paradigm (physical ANC + computational DNN), Orka O1 Pro, CMU open-ear smart glasses
- `wiki/concepts/tinyml-edge-ai.md` — TinyML for hearing devices: 97% keyword spotting at 256KB, Aizip software-only AI, programmable accelerators

**Pages updated (14 existing):**
- `wiki/concepts/speech-enhancement-neural-networks.md` — DAT-CFTNet, TokenSE/Mamba, GAP-URGENet sections
- `wiki/concepts/state-space-models.md` — TokenSE Mamba section for CI SE
- `wiki/concepts/auracast-bluetooth-le-audio.md` — Starkey Auracast Assistant; 3 of 6 manufacturers Auracast-capable
- `wiki/concepts/cochlear-implant-ai.md` — DAT-CFTNet and TokenSE/Mamba sections
- `wiki/concepts/on-device-ml-hearing-aids.md` — TinyML and ANC sources and cross-refs
- `wiki/concepts/dnn-architectures-hearing-aids.md` — New architecture sources and cross-refs
- `wiki/concepts/small-language-models-edge-ai.md` — TinyML and Mamba cross-refs
- `wiki/entities/demant-oticon.md` — Zeal AAA details source
- `wiki/entities/starkey.md` — Auracast & Connectivity Update section (4 features)
- `wiki/entities/phonak.md` — AI Excellence Award details
- `wiki/entities/sonova-ag.md` — Phonak AI Award source
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — 7 new sources and cross-refs
- `wiki/comparisons/ai-hearing-aid-platforms-2026.md` — Phonak/Starkey sources
- `wiki/index.md` — 3 new concept pages added

**Cross-references added:** ~40

**Key narrative threads:**
1. **Mamba enters CI speech enhancement:** TokenSE is the first selective SSM applied to CI — O(n) complexity with subjective CI user validation
2. **CI-specific SE research accelerating:** Three distinct architectural advances (DAT-CFTNet, TokenSE, GAP-URGENet) in one digest
3. **ANC extends to new form factors:** CMU open-ear smart glasses (9.6 dB, 8 mics) expands ANC beyond earbuds/hearing aids
4. **Generative-predictive fusion is the new SE frontier:** GAP-URGENet winning URGENT 2026 validates combining predictive reliability with generative quality
5. **Auracast critical mass:** 3 of 6 major manufacturers now ship Auracast devices
6. **TinyML validates hearing aid-scale ML:** 97% keyword accuracy on 256KB Arduino validates keyword spotting on hearing aid memory budgets

---

## 2026-04-23 — Daily Digest Ingestion: AAA 2026, Oticon Zeal, Neurotone AI, Edge AI Audio, Convergence, arXiv Papers

**Operation:** INGEST (batch — 10 sources from daily digest)

**Sources created (7 new):**
1. `oticon-zeal-hearingreview-aaa-2026.md` — Hearing Review coverage of Oticon Zeal at AAA 2026: encapsulation tech, 2nd-gen AI confirmed, LE Audio/Auracast confirmed
2. `neurotone-ai-1000-clinics-april-2026.md` — Neurotone AI surpassed 1,000 clinic partners; Dr. Brian Taylor (ex-Signia) joined as VP Clinical Research; AI aural rehabilitation as standard of care
3. `aaa-2026-conference-april.md` — AAA 2026 "Amplify Your Value," Apr 22-24, San Antonio; Big 6 exhibitors; HearTECH Hub
4. `multi-stage-low-latency-enhancement-ha-arxiv-2026.md` — Multi-stage magnitude+complex domain system; asymmetric window pair for 5ms latency; head rotation integration
5. `end-to-end-audiovisual-ci-sound-coding-arxiv-2026.md` — Audio + lip-reading for CI electrodogram generation; noise-robust multimodal fusion
6. `hhtm-convergence-ai-audio-hearing-devices-2026.md` — HHTM analysis: on-device inference convergence, personalization as battleground, shrinking consumer-medical gap
7. `edge-ai-audio-embedded-world-2026.md` — Synaptics Astra SR80, AONDevices, Aizip+PYOUR Audio; edge AI audio supply chain maturation

**Sources updated (2 existing):**
- `wsa-sound-preference-program-april-2026.md` — Added HHTM URL, global rollout date (Apr 20, 2026), HCP framing
- `audien-target-expansion-april-2026.md` — Already complete; no update needed

**Sources skipped (1 already covered):**
- Oticon Play SI (source #2) — already fully covered by `oticon-play-si-pediatric-launch-april-2026.md` and `oticon-play-si-hearingreview-april-2026.md` with same URL and Boys Town data

**Pages created (2 new):**
- `wiki/entities/neurotone-ai.md` — AI aural rehabilitation platform; 1,000 clinics; Brian Taylor VP hire; beyond-the-device AI opportunity
- `wiki/entities/aaa-conference.md` — American Academy of Audiology conference; AAA 2026 details; product launch venue

**Pages updated (12 existing):**
- `wiki/entities/demant-oticon.md` — Zeal: encapsulation tech, 2nd-gen AI confirmed, Auracast confirmed, AAA 2026 context; new sources
- `wiki/entities/ws-audiology-signia.md` — Sound Preference global rollout date (Apr 20), AAA 2026 showcase, Neurotone cross-ref
- `wiki/entities/starkey.md` — AAA conference cross-reference
- `wiki/concepts/auracast-bluetooth-le-audio.md` — Zeal Auracast confirmed (full-lineup rollout complete); new source
- `wiki/concepts/on-device-ml-hearing-aids.md` — Edge AI supply chain maturation (Embedded World), consumer-medical convergence (HHTM), new sources
- `wiki/concepts/dnn-in-hearing-aids.md` — Multi-stage phase-aware enhancement section, AI aural rehabilitation section (Neurotone), new sources and cross-refs
- `wiki/concepts/speech-enhancement-neural-networks.md` — Multi-stage phase-aware system, end-to-end AV CI sound coding sections, new sources
- `wiki/concepts/cochlear-implant-ai.md` — End-to-end AV CI sound coding section updated with arXiv:2508.13576v1 details
- `wiki/concepts/hearing-aid-market-dynamics.md` — Convergence, AAA 2026, Neurotone cross-references
- `wiki/concepts/teleaudiology.md` — Neurotone cross-reference
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — All new sources added; Neurotone and AAA conference cross-references
- `wiki/index.md` — 2 new entity pages added; 8 existing pages updated with new dates

---

## 2026-04-23 — Batch Ingestion: DNN vs Natural Processing, Fully Implantable CIs, Sony OTC Update, Play SI Clinical Data

**Operation:** INGEST (batch — 4 sources)

**Sources created (4 new):**
1. `korhonen-natural-vs-dnn-hearing-aids-april-2026.md` — Korhonen et al. (Hearing Review, April 2026): 29 adults tested across 5 premium HAs; Widex Allure (no DNN, natural processing) outperformed 4 DNN competitors by up to 8.5 dB SNR for moderate HL; word recognition 80% vs 60-70%
2. `completely-implantable-cochlear-implants-april-2026.md` — Hamilton-Basich (Hearing Review, April 2026): Three companies developing fully implantable CIs (Envoy Medical Acclaim with piezoelectric incus sensor, Cochlear Ltd. 21 yr R&D, MED-EL TICI); Envoy anticipates FDA late 2027/early 2028
3. `sony-otc-discontinued-hearingtracker-april-2026.md` — HearingTracker coverage of Sony OTC discontinuation; adds 3.5 year partnership duration, #1 HearAdvisor ranking despite commercial failure, CRE-C20 also pulled, $700-$1,000 street pricing, WSA plans "different branding" for OTC
4. `oticon-play-si-hearingreview-april-2026.md` — Hearing Review coverage of Play SI; adds Boys Town clinical validation: 50% improved sentence recognition, 77% reduced listening difficulty for teens

**Pages created (2 new):**
- `wiki/entities/envoy-medical.md` — Envoy Medical: Acclaim fully implantable CI, piezoelectric incus sensor, no magnet/external components, chest battery 10-15 yr, FDA late 2027/2028; edge AI implications
- `wiki/comparisons/dnn-vs-natural-processing.md` — DNN vs natural processing comparison: Korhonen et al. study, approach tradeoffs, why natural processing can win, why DNN still matters, WSA dual-brand implications

**Pages updated (13 existing):**
- `wiki/concepts/dnn-in-hearing-aids.md` — Natural processing counter-evidence section (Korhonen et al.), pediatric clinical validation section (Boys Town), new sources and related pages
- `wiki/concepts/cochlear-implant-ai.md` — Fully implantable CI section (3 companies, AI implications), updated key manufacturers with Envoy/MED-EL TICI, new sources and related pages
- `wiki/concepts/otc-hearing-aids.md` — Sony discontinuation updated with HearingTracker details (3.5 yr, #1 HearAdvisor, CRE-C20, $700-$1,000, different branding plans), new source
- `wiki/concepts/on-device-ml-hearing-aids.md` — Fully implantable CI as extreme edge constraint section, new source and related pages
- `wiki/concepts/speech-enhancement-neural-networks.md` — Korhonen natural processing source added, dnn-vs-natural-processing cross-reference
- `wiki/concepts/hearing-aid-market-dynamics.md` — Sony details updated, fully implantable CI product category section, new sources and related pages
- `wiki/concepts/hearing-aid-chip-architectures.md` — Fully implantable CI source and cross-references added
- `wiki/entities/demant-oticon.md` — Play SI Boys Town clinical data (50% sentence recognition, 77% reduced listening difficulty), new source
- `wiki/entities/ws-audiology-signia.md` — Widex natural processing evidence section (Korhonen et al.), Sony details updated (3.5 yr, #1 HearAdvisor, different branding), new sources and related pages
- `wiki/comparisons/ai-hearing-aid-platforms-2026.md` — Widex Allure natural processing entry, Play SI Boys Town data, watch items updated, new sources and related pages
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — DNN vs natural processing, fully implantable CIs, Play SI clinical validation sections, new sources
- `wiki/syntheses/hearing-aid-market-outlook.md` — Sony 3.5yr details, Widex natural processing, Envoy fully implantable CI, new sources and related pages
- `wiki/index.md` — Added Envoy Medical entity and DNN vs Natural Processing comparison

**Cross-references added:** ~35

**Key narrative threads from this ingestion:**
1. **DNN is not always superior:** Korhonen et al. provides the first comparative evidence that classical DSP preserving temporal speech cues (Widex Allure) can outperform DNN-based competitors by significant margins (up to 8.5 dB SNR). This challenges the industry-wide "AI hearing aid" marketing narrative and validates WSA's dual-brand strategy (Widex natural / Signia enhanced).
2. **Fully implantable CIs approaching market:** With Envoy Medical anticipating FDA approval late 2027/2028, the hearing industry faces a new product category requiring extreme edge AI — sub-microwatt inference under skin with 10-15 year battery life. This makes CIM + SSM architectures not just academic but potentially necessary.
3. **Sony OTC failure deepens:** HearingTracker coverage adds nuance — despite #1 HearAdvisor ranking, 3.5 years of partnership, and Sony's brand trust, premium OTC pricing could not compete. The "quality was not the problem, price was" lesson is important for other consumer tech companies considering hearing aid entry.
4. **AI crosses pediatric trust threshold:** Boys Town validation of Oticon Play SI (50% improved sentence recognition, 77% reduced listening difficulty for teens) provides the strongest independent clinical evidence for AI in pediatric hearing aids — a population where conservative adoption is the norm.

---

## 2026-04-23 — LinkedIn Post Research Ingestion: OTC Mass Retail, Ceretone UK Expansion

**Operation:** INGEST (LinkedIn post research — 2 new sources, 1 page updated)

**Sources created (2 new):**
1. `audien-target-expansion-april-2026.md` — Audien surpasses 11,000 retail locations with Target nationwide rollout; population-scale usage data implications for hearing AI
2. `ceretone-uk-otc-expansion-april-2026.md` — Ceretone enters UK market following law change; global OTC regulatory convergence

**Pages updated (1):**
1. `wiki/concepts/otc-hearing-aids.md` — Added Audien as mass-retail OTC brand, new "OTC Distribution Inflection Point" section, updated UK international expansion with regulatory detail, added new sources

**LinkedIn posts drafted (2):**
1. Bose enters hearing aids via Orka O1 Pro — consumer audio meets clinical hearing (leveraging existing Orka/Bose source)
2. OTC hearing aids hit mass retail scale — Audien at 11,000+ stores including Target

---

## 2026-04-22 — Daily Digest Ingestion: ANC Hearing Aids, Sony OTC Exit, On-Device STT, Hearables Convergence, Conv-TasNet CI Evidence

**Operation:** INGEST (daily digest — 7 items, 3 new sources, 4 existing sources updated)

**Sources created (3 new):**
1. `orka-o1-pro-bose-anc-awe-2026.md` — World's first ANC RIC hearing aid; Orka + Bose QuietControl partnership, 3.5g, 35hr battery, AWE 2026 debut
2. `sony-otc-hearing-aids-discontinued-april-2026.md` — WSA ends Sony-branded OTC HA sales; premium OTC pricing ($999-$1,299) fails against AirPods Pro ($200) and budget OTC
3. `adobe-speechmatics-on-device-stt-april-2026.md` — On-device STT: 1hr audio in 55s, within 5% cloud accuracy, 12-16% better than Whisper, 55+ languages

**Sources updated (4 existing):**
1. `frontiers-ai-enabled-hearables-industry-2026.md` — Added Singh et al. authorship, 18 expert count, specific themes: ear as biometric sensor, AI agents, governance gaps, BCI by 2050
2. `dnn-noise-reduction-intelligibility-2026.md` — Added Schulz et al. authorship, Conv-TasNet architecture, CI +5.7 dB / HI +0.8 dB / NH degraded, inverse correlation finding
3. `oticon-verit-launch-april-2026.md` — Added HearingTracker URL, MoreSound Intelligence 3.0, BLE Audio detail
4. `hearing-aids-market-14b-by-2030-april-2026.md` — Added Sony discontinuation as headwind, updated growth drivers

**Pages created (1 new):**
- `wiki/entities/orka-bose-partnership.md` — Orka + Bose: first ANC RIC hearing aid, dual-layer noise management paradigm (ANC + DNN), consumer-medical bridge

**Pages updated (11 existing):**
- `wiki/concepts/dnn-in-hearing-aids.md` — Conv-TasNet listener group data (CI +5.7 dB), ANC + DNN dual-layer paradigm section, Orka reference
- `wiki/concepts/on-device-ml-hearing-aids.md` — Adobe/Speechmatics on-device STT benchmark (cloud parity, 65x real-time)
- `wiki/concepts/otc-hearing-aids.md` �� Sony discontinuation, Bose/Orka entry, premium OTC pricing failure section, ANC section
- `wiki/concepts/speech-enhancement-neural-networks.md` — Conv-TasNet listener group details, Adobe/Speechmatics source
- `wiki/concepts/hearing-aid-market-dynamics.md` — Sony exit headwind, consumer-audio partnership section (Orka+Bose vs Sony/WSA), Singh et al. source
- `wiki/concepts/cochlear-implant-ai.md` — Conv-TasNet CI benefit (+5.7 dB, largest of any group), product implication for CI processors
- `wiki/concepts/model-compression.md` — Adobe/Speechmatics source added
- `wiki/entities/demant-oticon.md` — MoreSound Intelligence 3.0 detail for Verit
- `wiki/entities/ws-audiology-signia.md` — Sony OTC partnership discontinued section, strategic implications
- `wiki/syntheses/hearing-aid-market-outlook.md` — Singh et al. detail (18 experts, BCI, governance), Sony exit, Orka+Bose, brand licensing vs partnership comparison
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — ANC+DNN dual-layer, Conv-TasNet CI evidence, sources updated

**Index updated:** Added Orka/Bose Partnership entity page

**Cross-references added:** ~25 (related: fields, inline [[links]], Sources sections)

**Key narrative threads from this digest:**
1. **ANC enters hearing aids:** Orka O1 Pro with Bose QuietControl creates a new dual-layer noise management paradigm (physical ANC + computational DNN). First-ever ANC RIC hearing aid.
2. **Premium OTC pricing failure:** Sony/WSA discontinuation validates the "middle squeeze" — growth at premium prescription ($4K+) and ultra-affordable ($200) ends, compression in between.
3. **Consumer partnership > brand licensing:** Orka+Bose (technology partnership) appears more viable than Sony+WSA (brand licensing) as a consumer-tech entry strategy for hearing aids.
4. **DNN benefit scales with deficit:** Schulz et al. Conv-TasNet data shows CI users gain +5.7 dB vs. normal-hearing slight degradation — strongest evidence that DNN should be prioritized for severe loss/CI.
5. **On-device ML approaching cloud parity:** Adobe+Speechmatics achieves within 5% of cloud accuracy on-device — trajectory validation for hearing aid industry's fully on-device approach.
6. **Hearables as biometric + BCI platform:** Singh et al.'s 18 experts envision ear as primary biometric sensor, AI agents for hearing support, and in-ear BCIs by 2050. Governance frameworks lagging.

---

## 2026-04-22 — Batch Ingestion: Compute-in-Memory, State Space Models, Open-Source Speech AI

**Operation:** INGEST (batch — 3 sources)

**Sources created (3 new):**
1. `michigan-compute-in-memory-rram-ssm-nature-2026.md` — Michigan CIM: first SSM-on-RRAM mapping, Nature Communications, DOI:10.1038/s41467-025-68227-w. Memristors with tungsten oxide, 4.6-bit accuracy, hearing aids as explicit target.
2. `applied-brain-research-ssm-edge-audio-2026.md` — Applied Brain Research: SSMs for streaming audio, TSP1 chip at <30mW, speech-to-text/TTS/speech-to-intent on-device.
3. `open-source-speech-ai-edge-native-april-2026.md` — Open-source speech models going edge-native: Mistral Voxtral 3B (Apache 2.0), Qwen3-ASR (52 languages, 0.6B/1.7B), Qwen3-TTS (zero-shot cloning, 97ms TTFA), Distil-Whisper (6.3x faster than Whisper Large V3).

**Pages created (2 new):**
- `wiki/concepts/compute-in-memory.md` — CIM architecture: RRAM crossbar arrays, analog computation, contrast with compression paradigm, hearing aid relevance and challenges
- `wiki/concepts/state-space-models.md` — SSMs for hearing AI: S4/Mamba architectures, comparison with CRN/transformers, CIM hardware co-design, ABR production validation

**Pages updated (7 existing):**
- `wiki/concepts/on-device-ml-hearing-aids.md` — CIM+SSM section, ABR TSP1 reference, new related pages and sources
- `wiki/concepts/hearing-aid-chip-architectures.md` — New "Approach 3: CIM" section with RRAM crossbar details, 3-way architecture comparison table
- `wiki/concepts/model-compression.md` — "CIM Alternative" section contrasting compress-to-fit vs redesign-hardware paradigms; open-source speech models as distillation teachers
- `wiki/concepts/small-language-models-edge-ai.md` — Open-source speech models table (Voxtral, Qwen3-ASR/TTS, Distil-Whisper) with hearing AI relevance
- `wiki/concepts/dnn-architectures-hearing-aids.md` — SSM section: architecture comparison, CIM co-design, CRN-SSM hybrid prospect
- `wiki/concepts/dnn-in-hearing-aids.md` — SSM row added to key architectures table, new related pages
- `wiki/index.md` — Added CIM and SSM concept pages

**Cross-references added:** ~30 (related: fields, inline [[links]], and Sources sections)

**Notes:** Three sources spanning two major paradigm shifts: (1) Hardware paradigm — compute-in-memory eliminates the von Neumann bottleneck by performing computation inside memory arrays; Michigan's Nature Communications paper is the first to map SSMs onto RRAM, explicitly naming hearing aids. (2) Model paradigm — state space models offer O(n) streaming inference that is inherently causal and fixed-memory, addressing transformer limitations for hearing aids; ABR validates this in production at 30mW. (3) Open-source speech ecosystem — production-quality edge-native speech models (Voxtral 3B, Qwen3-ASR at 0.6B with 52 languages, Distil-Whisper at 6.3x speedup) provide high-quality distillation teachers for hearing aid model development. The CIM+SSM combination is particularly significant: it pairs an efficient model architecture (linear recurrence) with hardware where that computation is physically native (analog crossbar), potentially enabling hearing aid AI at power levels not achievable with digital architectures.

---

## 2026-04-21 — Daily Digest Ingestion: Oticon Zeal, Starkey Awards, HIMSA Growth, Hearables Research, Aizip, Samsung Audio Eraser

**Operation:** INGEST (daily digest — 9 items, 6 new sources, 1 updated, 2 skipped as duplicates)

**Sources created (6 new):**
1. `oticon-zeal-ite-launch-aaa-2026.md` — Oticon Zeal rechargeable ITE with streaming, debuting AAA 2026 (Apr 22)
2. `starkey-omega-ai-big-ai-awards-2026.md` — Starkey wins two 2026 BIG AI Excellence Awards for Omega AI platform
3. `frontiers-ai-enabled-hearables-industry-2026.md` — Qualitative study: industry leaders on AI-enabled hearables convergence (Frontiers 2026)
4. `wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md` — Programmable speech AI accelerator with mixed-precision quantization, 28-participant evaluation (arXiv:2503.18698v2)
5. `aizip-tiny-ai-hearing-devices-2026.md` — Aizip platform for AI noise reduction on standard hearing device hardware
6. `samsung-galaxy-s26-audio-eraser-realtime-2026.md` — Samsung Galaxy S26 real-time sound separation (Audio Eraser transition from post-production)

**Sources updated (1):**
- `noah-es-5000-subscribers-april-2026.md` — Added HearingHealthMatters URL, updated to 5,400+ users doubled YoY

**Sources skipped (2 — already existed):**
- Low-latency DNN noise reduction (Frontiers 2025, DOI:10.3389/fauot.2025.1746635) — already ingested as 3 source files
- Hearing aids market $14.42B (GlobeNewsWire) — already ingested as `hearing-aids-market-14b-by-2030-april-2026.md`

**Pages created (2 new):**
- `wiki/entities/himsa.md` — HIMSA organization, Noah ES cloud platform, 5,400+ subscribers, AI infrastructure significance
- `wiki/syntheses/hearing-aid-market-outlook.md` — Cross-cutting market outlook: convergence thesis, democratization of AI audio, competitive signals

**Pages updated (13 existing):**
- `wiki/entities/demant-oticon.md` — Oticon Zeal ITE section, product timeline updated
- `wiki/entities/starkey.md` — Omega AI platform section, BIG AI Excellence Awards, updated tags
- `wiki/concepts/on-device-ml-hearing-aids.md` — Programmable speech AI accelerators, Aizip TinyML platform sections
- `wiki/concepts/hearing-aid-market-dynamics.md` — Noah ES updated to 5,400+/doubled YoY, HIMSA cross-reference
- `wiki/concepts/auracast-bluetooth-le-audio.md` — Oticon Zeal likely Auracast-compatible noted in device support
- `wiki/concepts/speech-enhancement-neural-networks.md` — Samsung real-time Audio Eraser, programmable accelerators sections
- `wiki/concepts/hearing-aid-chip-architectures.md` — Programmable accelerators and Aizip software-only AI sections
- `wiki/concepts/model-compression.md` — Added accelerator and Aizip sources
- `wiki/comparisons/ai-hearing-aid-platforms-2026.md` — Starkey Omega AI / BIG AI Awards update
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — Programmable accelerators, Aizip, Oticon Zeal, Starkey G3 NPU entries
- `wiki/syntheses/ai-understanding-gap-hearing-industry.md` — Starkey awards source added
- `wiki/index.md` — Added HIMSA entity and hearing-aid-market-outlook synthesis

**Cross-references added:** ~25
**Notes:** Nine digest items covering six themes: (1) Demant's spring 2026 product blitz now includes a third product (Zeal ITE) alongside Verit and Play SI — broadest form factor coverage in the industry. (2) Starkey's dual BIG AI awards validate that hearing aid AI is recognized by the broader tech community. (3) HIMSA Noah ES doubling to 5,400+ subscribers provides the cloud data infrastructure prerequisite for AI-driven audiology at scale. (4) Frontiers qualitative study of industry leaders confirms the hearing aid / consumer hearables convergence thesis with interview evidence. (5) Aizip and programmable accelerators represent two paths to democratizing AI: software-only (Aizip on commodity DSPs) and hardware-flexible (programmable custom silicon). (6) Samsung Galaxy S26 real-time Audio Eraser shows consumer phones achieving hearing-aid-like source separation, raising consumer expectations. Two items skipped as duplicates (low-latency DNN already had 3 source files; market $14.42B already ingested).

---

## 2026-04-21 — Batch Ingestion: Apple CEO, WSA Sound Preference, Ternary Bonsai, Noah ES, Deezer AI Audio, Kimi K2.6

**Operation:** INGEST (batch — 6 sources)

**Sources ingested:**
1. Apple CEO Transition — John Ternus becomes CEO; Tim Cook to Executive Chairman. Ternus led AirPods Pro hardware and Apple Silicon. Signals hearing health is Apple strategic priority. (Apr 21, 2026)
2. WS Audiology Sound Preference Program — free tool using randomized audio comparisons; ~40% of users have consistent natural vs. enhanced sound preference. Structured data collection for personalization. (Apr 20, 2026)
3. PrismML Ternary Bonsai — 1.58-bit {-1, 0, +1} language models; 8B model at 1.75 GB (9x smaller than FP16); 82 tok/sec on M4 Pro; runs on iPhone via MLX. Eliminates multiplications. (Apr 16, 2026)
4. Noah ES Surpasses 5,000 Subscribers — HIMSA cloud hearing care platform milestone; prerequisite for AI-driven audiology at scale. (Apr 16, 2026)
5. Deezer 44% AI-Generated Audio — 44% of daily uploads AI-generated; 85% flagged fraudulent. Generative audio shares tech roots with speech enhancement. (Apr 20, 2026)
6. Kimi K2.6 Open-Source Agentic Model — 300 sub-agent swarm, 4,000 steps, SWE-Bench 80.2%. Frontier agentic AI. (Apr 2026)

**Pages created:** 0 new wiki pages (all updates to existing pages)

**Pages updated:** 19 existing pages
- wiki/entities/apple-hearing-features.md — Ternus CEO section, leadership signal for hearing health
- wiki/entities/ws-audiology-signia.md — Sound Preference Program section, 40% preference data, dual-brand alignment
- wiki/concepts/model-compression.md — Ternary Bonsai 1.58-bit section, no-multiply inference, Apple MLX pipeline
- wiki/concepts/on-device-ml-hearing-aids.md — Ternary 1.58-bit entry in compression section, sub-2-bit convergence
- wiki/concepts/small-language-models-edge-ai.md — Ternary Bonsai in quantization techniques, ternary MoE trajectory
- wiki/concepts/otc-hearing-aids.md — Apple CEO leadership signal
- wiki/concepts/closed-loop-data-flywheel.md — WSA Sound Preference Program as software-defined flywheel model
- wiki/concepts/hearing-aid-chip-architectures.md — Ternary-native compute units in future directions
- wiki/concepts/speech-enhancement-neural-networks.md — Generative audio AI section (Deezer 44%), speech reconstruction
- wiki/concepts/teleaudiology.md — Noah ES 5,000 subscribers section, cloud data infrastructure
- wiki/concepts/hearing-aid-market-dynamics.md — Noah ES cloud infrastructure, Apple CEO signal
- wiki/concepts/mixture-of-experts.md — Ternary quantization in compression relationship section
- wiki/concepts/dnn-architectures-hearing-aids.md — Added ternary source, updated timestamp
- wiki/concepts/automated-audiometry.md — Updated timestamp
- wiki/comparisons/ai-hearing-aid-platforms-2026.md — WSA Sound Preference, Apple CEO signal, new watch item
- wiki/comparisons/on-device-vs-cloud-ml.md — Ternary Bonsai 1.58-bit entry in compression section
- wiki/syntheses/hearing-aid-ai-stack-2026.md — Apple CEO, Ternary Bonsai, WSA Sound Preference across multiple layers
- wiki/syntheses/vertical-integration-trend.md — WSA software-defined data flywheel note
- wiki/syntheses/ai-understanding-gap-hearing-industry.md — Kimi K2.6 agentic frontier section

**Sources created:** 6 new
- sources/apple-ceo-transition-ternus-april-2026.md
- sources/wsa-sound-preference-program-april-2026.md
- sources/prismml-ternary-bonsai-158bit-april-2026.md
- sources/noah-es-5000-subscribers-april-2026.md
- sources/deezer-44pct-ai-generated-audio-april-2026.md
- sources/kimi-k26-agentic-model-april-2026.md

**Cross-references added:** ~30
**Notes:** Six sources covering five themes: (1) Apple CEO transition to John Ternus signals hearing health as strategic priority — the architect of AirPods Pro hearing features now runs the company. (2) WSA Sound Preference Program introduces structured data collection for personalization — 40% of users have measurable, consistent preferences for natural vs. enhanced sound, creating a software-defined data flywheel alternative to M&A-driven vertical integration. (3) PrismML Ternary Bonsai pushes model compression to 1.58-bit ternary weights with no-multiply inference — directly relevant to hearing aid chip constraints where multipliers dominate power budgets. The 3-bit to 1.58-bit trajectory within one month suggests sub-2-bit on-device inference is converging fast. (4) Noah ES at 5,000 subscribers provides cloud data infrastructure prerequisite for AI audiology at scale. (5) Deezer's 44% AI-generated audio demonstrates production-scale neural audio generation sharing technology roots with speech enhancement. (6) Kimi K2.6 agentic swarm (300 sub-agents) represents the frontier of agentic AI relevant to complex audiological workflows. No new wiki pages created — all six sources enriched existing pages, consistent with the preference for updating over creating.

---

## 2026-04-20 — LinkedIn Post Research Ingestion (6 sources)

**Operation:** INGEST (batch — 6 sources from daily LinkedIn post research)

**Sources ingested:**
1. Qwen3.6-35B-A3B MoE model (updated) — added Simon Willison URL, ~21GB quantized, MacBook Pro M5 via LM Studio details (Apr 16, 2026)
2. Auracast in UK Live Theaters — Everyman Theatre (Cheltenham) and Contact (Manchester) using Auri Bluetooth Auracast, replacing 20-year-old infrared (Apr 2026)
3. Oticon Play SI Pediatric Launch (updated) — added Hearing Review URL, 12dB noise suppression, 80Hz-10kHz bandwidth, IP68, miniRITE R/miniBTE R styles, EduMic compatible (Apr 17, 2026)
4. Oticon Verit Launch (updated) — added Hearing Review URL, Sirius platform confirmed, 12dB NR (2dB > Real, 3dB > Opn S), zinc-air battery, SuddenSound Stabilizer (Apr 2026)
5. Advanced Bionics + Spiral Therapeutics (updated) — added Hearing Review URL as additional coverage (Apr 15, 2026)
6. Claude Opus 4.7 Release — improved agentic tasks, higher-res image processing, real-time cyber safeguards, new tokenizer, same pricing as 4.6 (Apr 16, 2026)

**Pages created:** 1 new wiki page
- wiki/concepts/mixture-of-experts.md — MoE architecture, scene-specific expert networks for hearing aids, Qwen3.6 as key example, capacity vs compute tradeoff, deployment approaches

**Pages updated:** 11 existing pages
- wiki/concepts/auracast-bluetooth-le-audio.md — First UK live theater deployments (Everyman + Contact), Auri system, infrared replacement, sub-lip-reader latency
- wiki/entities/demant-oticon.md — Verit 12dB NR details, Sirius platform, zinc-air, SuddenSound Stabilizer; Play SI 12dB NR, IP68, bandwidth, styles, EduMic
- wiki/concepts/small-language-models-edge-ai.md — Updated Qwen3.6 entry with hardware details, MoE cross-reference
- wiki/concepts/on-device-ml-hearing-aids.md — MoE cross-reference added
- wiki/concepts/model-compression.md — MoE cross-reference added
- wiki/concepts/dnn-architectures-hearing-aids.md — MoE cross-reference added
- wiki/concepts/hearing-aid-chip-architectures.md — MoE cross-reference added
- wiki/concepts/dnn-in-hearing-aids.md — Verit/Play SI 12dB noise suppression quantified, SuddenSound Stabilizer
- wiki/comparisons/ai-hearing-aid-platforms-2026.md — Verit row updated with Sirius, 12dB NR, SuddenSound Stabilizer
- wiki/entities/sonova-ag.md — Updated timestamp (AB source coverage expanded)
- wiki/entities/advanced-bionics.md — Updated timestamp (Hearing Review URL added to source)
- wiki/syntheses/hearing-aid-ai-stack-2026.md — Added Auracast UK theaters and Qwen MoE sources

**Sources created:** 2 new
- sources/auracast-uk-live-theaters-april-2026.md — First real-world Auracast assistive listening in UK theaters
- sources/claude-opus-4-7-release-april-2026.md — Anthropic frontier model update

**Sources updated:** 4 existing
- sources/qwen3-6-35b-a3b-open-source-april-2026.md — Simon Willison URL, ~21GB quantized, MacBook Pro M5
- sources/oticon-verit-launch-april-2026.md — Hearing Review URL, Sirius platform, 12dB NR, zinc-air, SuddenSound Stabilizer
- sources/oticon-play-si-pediatric-launch-april-2026.md — Hearing Review URL, 12dB NR, bandwidth, IP68, styles, EduMic
- sources/advanced-bionics-research-collaboration-ci-april-2026.md — Hearing Review URL added

**Cross-references added:** ~20
**Notes:** Six sources covering four themes: (1) MoE as an architectural paradigm for scene-specific hearing aid AI — new concept page created connecting Qwen3.6 to hearing aid expert routing, (2) Auracast moves from trade show to real-world venue deployment in UK theaters replacing 20-year-old infrared, (3) Oticon Verit/Play SI specs now quantified with 12dB noise suppression benchmarks vs predecessors, (4) Claude Opus 4.7 as frontier model evolution relevant to agentic audiology workflows. The Auracast UK theater deployment is a milestone — first documented audience-facing Auracast assistive listening replacing legacy infrared.

---

## 2026-04-19 — LINT Pass

**Operation:** LINT (full health check)

**Scope:** 42 wiki pages (22 concepts, 13 entities, 3 comparisons, 4 syntheses), 87 source files

### Findings Summary
- **Index coverage:** ✅ Complete — all 42 pages listed in index.md; no missing or phantom entries
- **Broken cross-references:** 8 found → 8 fixed
- **Near-orphan pages:** 2 found → 2 improved (added incoming links)
- **Empty sources fields:** 2 found → flagged for human attention
- **Stale source flags:** 3 flagged for human attention
- **Duplicates:** 1 potential overlap flagged for human attention
- **Total fixes applied:** 12 edits across 9 files

### Broken Cross-References Fixed (8)

All were references to planned-but-never-created product detail pages or synthesis stubs:

| File | Broken Link | Action |
|------|------------|--------|
| `entities/demant-oticon.md` | `oticon-intent.md` | Removed from `related:` and Related Pages body |
| `entities/gn-hearing-resound.md` | `resound-vivia.md` | Removed from `related:` and Related Pages body |
| `entities/sonova-ag.md` | `phonak-audeo-sphere-infinio.md` | Removed from `related:` and Related Pages body |
| `entities/starkey.md` | `starkey-omega-ai.md` | Removed from `related:` |
| `entities/starkey.md` | `med-el.md` | Removed from `related:` |
| `entities/ws-audiology-signia.md` | `signia-ix.md` | Removed from `related:` |
| `comparisons/otc-vs-prescription-hearing-aids.md` | `consumer-hearing-tech-convergence.md` | Removed from `related:`, body link replaced with `[[otc-hearing-aids]]` |
| `syntheses/hearing-ai-research-landscape-2025.md` | `dementia-prevention-hearing-care.md` | Removed from `related:`, body link replaced with `[[hearing-loss-dementia-link]]` |

### Near-Orphan Pages Fixed (2)

Pages with only 1 incoming link, improved with additional cross-references:

- **`concepts/world-models-hearing-ai.md`** (was only referenced by `on-device-ml-hearing-aids.md`): Added incoming link from `concepts/large-sensor-models.md` (bidirectional — LSMs and world models are complementary approaches to transfer learning for hearing AI)
- **`concepts/audio-reasoning-chain-of-thought.md`** (was only referenced by `on-device-ml-hearing-aids.md`): Added incoming link from `concepts/auditory-attention-decoding.md` (complementary — neural attention decoding vs. chain-of-thought audio reasoning)

### Requires Human Attention

**Empty `sources:` fields (pages not backed by any ingested source):**
1. `concepts/dnn-architectures-hearing-aids.md` — `sources: []`; content appears synthesized from general knowledge rather than an ingested document. Recommend ingesting a relevant DNN architecture paper (e.g., one from the VCCA2024/2025/2026 proceedings or Frontiers).
2. `entities/who-hearing-program.md` — `sources: []`; WHO World Hearing Day source (`who-hearing-day-2026.md`) exists in `sources/` but was never linked. Add that source to the frontmatter and sources section.

**Stale sources on fast-moving topics (>3 months old, dated before 2026-01-19):**
1. `concepts/hearing-aid-market-dynamics.md` — Also references `hearing-aid-market-2025-2029.md` (2025); largely superseded by `hearing-aids-market-14b-by-2030-april-2026.md` (Apr 2026) which projects more conservative $14.42B figure vs older $22B estimate. The page has been updated with new data; old source can remain as historical baseline.
2. `entities/gn-hearing-resound.md` — `updated: 2026-04-15`; only updated once since creation despite major developments (Amplifon acquisition progress, Vivia clinical data). Consider refreshing.
3. `syntheses/hearing-ai-research-landscape-2025.md` — Title says "2025" but we are now in mid-2026; the forward-looking projections (2025–2027, 2027–2030, 2030+) should be reviewed for accuracy given 14+ months of subsequent developments.

**Potential concept overlap (human judgment required):**
- `concepts/dnn-architectures-hearing-aids.md` vs `concepts/dnn-in-hearing-aids.md`: These are distinct (architectures focuses on model types/chip-level architecture; dnn-in-hearing-aids focuses on commercial deployment and clinical outcomes) but are cited together constantly and the distinction is subtle. Consider: (a) merging into one page, (b) adding a note to each clarifying the scope split, or (c) keeping as-is. Currently `dnn-architectures-hearing-aids.md` has no source backing, which weakens it relative to `dnn-in-hearing-aids.md`.

### Index Status
`wiki/index.md` is complete and accurate. All 42 content pages are listed; no phantom entries.

---

## 2026-04-19 — Batch Ingestion: AB + Spiral Therapeutics, Audiologist Shortage, MCP Dev Summit, Market Data, Karpathy Idea Files

**Operation:** INGEST (batch — 5 sources)

**Sources ingested:**
1. Advanced Bionics + Spiral Therapeutics collaboration — equity investment + R&D for precision drug delivery during CI surgery, part of Spiral's $27M Series B (Apr 14, 2026)
2. Hearing Aids Market $14.42B by 2030 — updated with AI-driven growth drivers, wireless connectivity, real-time customization (Apr 16, 2026)
3. Audiologist workforce shortage — 75% US counties shortage areas, 68 min rural travel, 9% decade growth vs 3%/yr aging population (ASHA + ScienceDirect)
4. MCP Dev Summit + 97M monthly SDK downloads — first North America summit NYC Apr 2-3, 95+ sessions, Linux Foundation governance (Apr 2-3, 2026)
5. Karpathy "Idea Files" concept — updated with core philosophy "share the idea, not the code," personal wiki scale details (Apr 4, 2026)

**Pages created:** 3 new pages
- wiki/concepts/precision-drug-delivery-inner-ear.md — Inner ear drug delivery challenges, Spiral Therapeutics platform, CI surgery synergy, AI connection
- wiki/concepts/audiologist-workforce-shortage.md — 75% county shortage, travel disparities, structural mismatch, technology implications, policy dimensions
- wiki/concepts/model-context-protocol.md — MCP protocol overview, 97M downloads, governance, hearing AI applications, Karpathy idea files connection

**Pages updated:** 10 existing pages
- wiki/entities/advanced-bionics.md — Spiral Therapeutics collaboration details ($27M Series B, equity investment, drug delivery)
- wiki/entities/sonova-ag.md — Triple-track strategy (hearing aid AI + CI electronics + CI pharmacotherapy), Spiral partnership
- wiki/concepts/cochlear-implant-ai.md — AB + Spiral drug delivery section, triple-track Sonova strategy
- wiki/concepts/hearing-aid-market-dynamics.md — Audiologist shortage data (75% counties, travel gaps), workforce source added
- wiki/concepts/teleaudiology.md — Workforce imperative section, MCP agent infrastructure section
- wiki/concepts/otc-hearing-aids.md — Workforce shortage as access driver, audiologist shortage cross-reference
- wiki/concepts/automated-audiometry.md — Workforce shortage source, cross-references to new pages
- wiki/concepts/on-device-ml-hearing-aids.md — MCP cross-reference
- wiki/syntheses/ai-understanding-gap-hearing-industry.md — Karpathy idea files section, MCP infrastructure section, new sources
- wiki/index.md — 3 new concept pages added

**Sources created:** 2 new (audiologist-shortage-asha-sciencedirect-2025.md, mcp-dev-summit-97m-installs-april-2026.md)
**Sources updated:** 2 (advanced-bionics-research-collaboration-ci-april-2026.md — Spiral Therapeutics details, karpathy-idea-files-april-2026.md — core philosophy and wiki scale)
**Cross-references added:** ~35
**Notes:** Five sources covering four themes: (1) AB + Spiral Therapeutics opens a new device+drug convergence axis for CI innovation, (2) Audiologist workforce shortage data quantifies the structural imperative for AI/teleaudiology/OTC solutions, (3) MCP at 97M downloads provides the infrastructure layer for agentic hearing AI, (4) Karpathy's idea files paradigm connects to this wiki's own methodology and the broader AI agent ecosystem. The audiologist shortage (75% of US counties) emerges as a critical connective thread linking market dynamics, OTC, teleaudiology, and automated audiometry.

---

## 2026-04-18 — Batch Ingestion: Model Compression, AirPods Pro 3, Market Update, AI Agent Patterns

**Operation:** INGEST (batch — 4 sources)

**Sources ingested:**
1. Google TurboQuant (ICLR 2026) — 6x KV cache compression, 3-bit quantization, zero accuracy loss, no retraining (Mar 24, 2026)
2. AirPods Pro 3 hearing health + heart rate — $200 FDA-cleared hearing aid, 256 Hz PPG, 67% battery improvement (Apr 14, 2026)
3. Hearing Aids Market $14.42B by 2030 — Updated with $10.35B (2025), 6.8% CAGR, 1.5B hearing impaired, workforce shortage (Apr 16, 2026)
4. Karpathy CLAUDE.md template viral (5,828 stars) — Structured AI agent behavioral principles (Apr 13, 2026)

**Pages created:** 2 new pages
- wiki/concepts/model-compression.md — Quantization, distillation, pruning, NAS pipeline for hearing AI
- wiki/entities/google-research.md — Google's role as infrastructure/research provider to hearing AI ecosystem

**Pages updated:** 11 existing pages
- wiki/entities/apple-hearing-features.md — AirPods Pro 3 detailed specs ($200, 256 Hz PPG, 67% battery, active protection)
- wiki/concepts/on-device-ml-hearing-aids.md — Model compression section, TurboQuant reference, health monitoring update
- wiki/concepts/hearing-aid-market-dynamics.md — $10.35B baseline, 6.8% CAGR, 1.5B impaired, 700M by 2050, workforce gap
- wiki/concepts/small-language-models-edge-ai.md — TurboQuant 3-bit quantization, Google Research cross-reference
- wiki/concepts/dnn-architectures-hearing-aids.md — Model compression cross-reference
- wiki/concepts/otc-hearing-aids.md — AirPods Pro 3 at $200, updated price table, health monitoring convergence
- wiki/comparisons/on-device-vs-cloud-ml.md — Model compression section, TurboQuant closing the gap
- wiki/comparisons/otc-vs-prescription-hearing-aids.md — AirPods Pro 3 source added
- wiki/syntheses/hearing-aid-ai-stack-2026.md — Apple chip update, AirPods Pro 3 specs, TurboQuant in "What's Coming Next"
- wiki/syntheses/ai-understanding-gap-hearing-industry.md — Karpathy CLAUDE.md template, structured agent instructions for hearing AI

**Sources created:** 3 new (google-turboquant-iclr-2026.md, airpods-pro-3-hearing-health-april-2026.md, karpathy-claude-md-template-viral-april-2026.md)
**Sources updated:** 1 (hearing-aids-market-14b-by-2030-april-2026.md — added $10.35B baseline, CAGR, global burden, workforce gap)
**Cross-references added:** ~25
**Notes:** Four sources covering three themes: (1) Model compression advances (TurboQuant) that could enable more powerful on-device hearing AI, (2) Apple AirPods Pro 3 deepening the consumer-medical device convergence at $200 with health monitoring, (3) Market fundamentals (workforce shortage as structural driver for AI-assisted fitting), (4) AI agent development patterns (CLAUDE.md template) as meta-reference for this wiki's own methodology.

---

## 2026-04-17 — Batch Ingestion: Product Launches, Clinical Trial, Market Data, AI Trends

**Operation:** INGEST (batch — 10 sources)

**Sources ingested:**
1. Oticon Verit launch — premium adult HA with 2nd-gen AI, Auracast, Google Fast Pair (Apr 15, 2026)
2. Oticon Play SI launch — pediatric HA with 2nd-gen AI, 4D sensors, Auracast (Apr 16, 2026)
3. Phonak DNN noise reduction clinical trial NCT07526428 — interventional study for moderate-severe HL (Apr 14, 2026)
4. Starkey CTO Achin Bhowmik inducted into AIMBE — AI-driven hearing innovation recognition (Apr 16, 2026)
5. Hearing aids market $14.42B by 2030 — MarketsandMarkets report (Apr 16, 2026)
6. Ceretone OTC hearing aids UK launch at £129.99 — ultra-affordable OTC disruption (Apr 15, 2026)
7. Auracast "Ready vs Enabled" clarification + venue installation guides — consumer education, infrastructure deployment (Apr 14-16, 2026)
8. Advanced Bionics research collaboration for next-gen cochlear implants — Sonova CI innovation (Apr 14, 2026)
9. Qwen3.6-35B-A3B open-source release — MoE model, 35B total / 3B active, runs on laptop (Apr 16, 2026)
10. Karpathy "AI Psychosis" concept — AI understanding gap between tech workers and public (Apr 9-11, 2026)

**Pages created:** 5 new pages
- wiki/entities/ceretone.md — Ultra-affordable OTC brand
- wiki/entities/advanced-bionics.md — Sonova CI subsidiary
- wiki/concepts/hearing-aid-market-dynamics.md — Market sizing, forecasts, structural forces
- wiki/syntheses/ai-understanding-gap-hearing-industry.md — Karpathy AI Psychosis applied to hearing industry

**Pages updated:** 14 existing pages
- wiki/entities/demant-oticon.md — Verit + Play SI products, Auracast connectivity, product timeline
- wiki/entities/starkey.md — Achin Bhowmik leadership section, AIMBE recognition
- wiki/entities/phonak.md — DNN clinical trial NCT07526428, clinical evidence building
- wiki/entities/sonova-ag.md — Phonak clinical trial, AB CI collaboration, Advanced Bionics link
- wiki/concepts/auracast-bluetooth-le-audio.md — Ready vs Enabled distinction, venue deployment, Oticon products
- wiki/concepts/otc-hearing-aids.md — Ceretone, international OTC expansion
- wiki/concepts/dnn-in-hearing-aids.md — Phonak clinical trial, Oticon 2nd-gen AI
- wiki/concepts/cochlear-implant-ai.md — AB next-gen CI research, manufacturer section
- wiki/concepts/small-language-models-edge-ai.md — Qwen3.6 MoE, open-source trajectory
- wiki/concepts/speech-enhancement-neural-networks.md — Phonak clinical trial
- wiki/comparisons/ai-hearing-aid-platforms-2026.md — Oticon Verit row, April 2026 developments
- wiki/comparisons/otc-vs-prescription-hearing-aids.md — Ceretone pricing, market projection update
- wiki/syntheses/hearing-aid-ai-stack-2026.md — Verit, clinical trial, Auracast updates
- wiki/syntheses/hearing-ai-research-landscape-2025.md — Clinical evidence, open-source AI sections
- wiki/syntheses/vertical-integration-trend.md — Market data source update

**Sources created:** 10
**Cross-references added:** ~45
**Notes:** Major batch covering three key themes: (1) Demant product launches with 2nd-gen AI and Auracast across adult+pediatric lines, (2) Sonova dual-track clinical evidence building (Phonak DNN trial) and CI innovation (AB collaboration), (3) broader AI ecosystem developments (Qwen MoE, Karpathy AI Psychosis) connected to hearing industry implications. The Ceretone UK launch at £130 represents a new price floor for OTC. The Auracast Ready vs Enabled distinction emerged as a concrete example of the AI understanding gap concept.

---

## 2026-04-16 — LinkedIn Post Research Ingestion

**Operation:** INGEST (batch)
**Sources ingested:**
- Interspeech 2026 Audio Reasoning Challenge (arXiv:2602.14224) — chain-of-thought evaluation for audio AI
- 2026 World Models & Continual Learning Breakthroughs (NextBigFuture, April 14 2026)
- Karpathy "Idea Files" paradigm for AI agent development (SimpleNews.ai, April 4 2026)

**Pages created:** 2 concepts (audio-reasoning-chain-of-thought.md, world-models-hearing-ai.md)
**Pages updated:** on-device-ml-hearing-aids.md (added cross-references to new pages)
**Sources created:** 3 (interspeech-2026-audio-reasoning-challenge.md, world-models-continual-learning-2026.md, karpathy-idea-files-april-2026.md)
**Cross-references added:** 6
**Notes:** Research conducted for daily LinkedIn posts. Audio reasoning and world models represent two emerging paradigms that could transform hearing aid AI from reactive classification to proactive comprehension.

---

## 2026-04-15 — Initial Seeding

**Operation:** INGEST (batch)
**Sources ingested:**
- Amplifon acquires GN Hearing for $2.6B (HearingTracker, Bloomberg)
- "Wearable AI in the Era of Large Sensor Models" (arXiv:2604.10172, April 11 2026)
- HearingTracker Auracast analysis + Bluetooth SIG forecast
- Gartner SLM prediction (Dell report) + SmartWear edge AI (Taylor & Francis)
- The Rise of Small AI (dev.to)

**Pages created:** 18 (6 concepts, 7 entities, 1 comparison, 2 syntheses, 2 source files initial batch)
**Cross-references added:** ~30
**Notes:** Wiki bootstrapped from LinkedIn post research conducted 2026-04-14 and 2026-04-15. All sources verified at time of original research.

---

## 2026-04-15 — Academic Resources & VCCA Expansion

**Operation:** INGEST (batch — academic papers and VCCA conferences)

**Sources ingested (22 new):**
- VCCA2024 Conference (June 2024) — 89 abstracts, keynotes by Başkent, Bance, Ferguson, Bramsløw
- VCCA2025 Conference (June 2025) — keynotes by Di Liberto, Hickson, Kolossa, Edwards; AI clinical implementation panel
- VCCA2026 Conference (June 2026) — programme with pre-conference ML workshops, synaptopathy session
- Computational Audiology foundational paper (Wasmann et al., 2021, Ear and Hearing)
- Real-time EEG neurosteering of hearing instrument (J. Neural Engineering, Feb 2025)
- TSF-AADNet short-window auditory attention decoding (ScienceDirect, 2025)
- Wireless 2-node EEG sensor network for AAD (bioRxiv, Feb 2026)
- Scalp vs. around-ear vs. in-ear EEG comparison for AAD (Nature Sci Rep, 2025)
- Deep CNN AAD in hearing-impaired listeners (PubMed, 2024)
- HA noise reduction improves selective attention tracking (eNeuro, Feb 2025)
- Low-latency DNN noise reduction intelligibility study (Frontiers Audiol Otol, 2026)
- Sub-millisecond latency speech enhancement on hearables (arXiv, 2025)
- Multichannel binaural deep speech enhancement (IEEE/ACM TASLP, 2024)
- Speech foundation models for HI intelligibility prediction (arXiv, 2024)
- SSL loss functions for HA speech enhancement (arXiv, 2024)
- ACHIEVE trial secondary analysis — cognitive benefits stratified by risk (PMC, 2025)
- Hearing aid cognitive outcome prediction model (Frontiers Aging Neurosci, 2025)
- Framingham Heart Study — hearing loss, brain structure, dementia (JAMA Network Open, 2024)
- ML pure-tone audiometry with automated masking (World J ORL-HNS, 2025)
- Deep learning audiogram classification (Clin Otolaryngol, 2024)
- Hearing loss type classification from audiometry (Nature Sci Rep, 2024)
- ML for Meniere's disease diagnosis from audiometry (Otolaryngol-HNS, 2025)
- KDE/VAE audiometric data synthesis (Applied Sciences, 2025)
- DL framework for CI with 3D-printed cochleae (PMC, 2025)
- AVSE-ECS audio-visual CI sound coding (arXiv, 2025)
- ML CI speech perception — 4,046 patients, 32 institutions (Ear & Hearing, 2025)
- Pediatric CI language prediction via transfer learning (PMC, 2025)
- Digital hearing health editorial (Frontiers Neurosci, 2024)

**Pages created:** 2 new wiki pages (VCCA entity, Automated Audiometry concept)
**Pages updated:** 4 concept pages (AAD, speech enhancement, hearing-loss-dementia, CI-AI) + index
**Cross-references added:** ~25
**Notes:** Major expansion of academic sources. VCCA conferences (2024-2026) now fully documented with programmes, keynotes, and session details. Neurosteering/AAD section dramatically expanded with 6 new papers. Speech enhancement section updated with sub-ms latency and foundation model research. CI section updated with largest outcome study (4,046 patients) and audio-visual coding.

## 2026-04-26 — Daily Hearing+AI Digest Ingestion

**Trigger:** Daily 08:45 Zurich digest run

**Sources added (7):**
- envoy-acclaim-activations-april-2026.md — All 56 patients activated in Envoy fully-implanted CI pivotal trial (2026-04-22)
- pas-se-icassp-2026.md — Personalized Auxiliary-Sensor Speech Enhancement (ICASSP 2026)
- nal-nl3-fitting-protocol-2026.md — NAL-NL3 prescriptive fitting update with comfort/intelligibility tradeoff
- sonova-silentcloud-acquisition-2026.md — Sonova folds digital tinnitus therapy into hearing-care stack
- phonak-infinio-if-design-award-2026.md — Phonak Infinio Ultra Sphere & Virto R Infinio win 2026 iF Design Awards
- signia-insio-charge-go-cic-ix-2026.md — WSA's rechargeable custom CIC IX launches in US
- cearvol-neuroflow-ai-2-ces-2026.md — OTC DNN platform: vendor-reported +24% SE / 20 dB NR
- nyu-langone-ai-cochlear-programming-trial-2026.md — Multi-site AI-driven CI mapping clinical trial

**Pages updated:** index.md header
**Pages created:** 0 (existing concept/entity pages — speech-enhancement-neural-networks, gene-therapy-hearing, cochlear-implant-ai, otc-hearing-aids, sonova-ag, phonak, ws-audiology-signia, auracast — already cover today's themes)
**Notes:** Big news of the day = OTOF gene-therapy 2.5y Nature paper + FDA approval (already covered by harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md and otarmeni-fda-gene-therapy-approval-april-2026.md). 7 new sources fill gaps for industry product launches, NAL-NL3, and the PAS-SE paper. Email digest was 667 words, sent successfully to door.punch_4o@icloud.com.

## 2026-05-04 — Apple Hearing Study May 2026 Results Ingestion
Source: 9to5Mac (1 May 2026) + U-M School of Public Health study page

**Operations:**
- Created source: `sources/apple-hearing-study-results-may-2026.md` — n=160K cohort, 16% perception gap among 85K WHO-normal listeners, walking-speed correlation in n=57,183 sub-analysis
- Created concept: `wiki/concepts/subjective-objective-hearing-gap.md` — formalizes the audiogram-vs-experience gap as a personalization and outcome-measurement problem
- Updated entity: `wiki/entities/apple-hearing-features.md` — added "Apple Hearing Study — May 2026 Findings" section; positions Apple as population-scale longitudinal hearing data generator (not just hardware disruptor)
- Updated concept: `wiki/concepts/longitudinal-hearing-phenotyping.md` — added population-scale exemplar section; Apple study as first operationalization of the framework at scale
- Updated concept: `wiki/concepts/hearing-loss-dementia-link.md` — added "Hearing and Mobility" section; walking-speed correlation as second hard biomarker (after cognition) for hearing-as-healthspan thesis
- Updated cross-references across all four pages
- Updated `wiki/index.md` with new concept page and refreshed dates

**Connected to LinkedIn drafts (2026-05-04):**
- Post 1: "The 16% gap" — perception vs measurement; implications for hearing aid personalization loss functions
- Post 2: "57,183 people, one finding" — hearing loss → slower walking; hearing aids as healthspan/longevity intervention

**Pages touched:** 5 (1 source created, 1 concept created, 1 entity updated, 2 concepts updated)

## 2026-05-04 — Daily Hearing+AI Digest Ingestion (PM)

**Trigger:** Daily hearing+AI digest run (post-email)

**Sources added (6):**
- llm-pure-tone-audiogram-chatgpt5-gemini25-2026.md — Springer, ChatGPT-5.0 Plus outperforms Gemini 2.5 on PTA interpretation; useful as triage adjunct, not standalone diagnosis
- bisgaard-audiogram-loudness-scaling-ml-2026.md — Int J Audiology (Apr 2026); ACALOS loudness scaling → Bisgaard archetypes via Logistic Regression; calibration-independent self-fitting path
- remote-ci-programming-real-life-frontiers-2026.md — Frontiers Audiol & Otol 2026; CI remote fitting in real-life environments — feasible, UX is the bottleneck (connectivity, A/V desync, non-verbal cues)
- phonak-virto-r-infinio-red-dot-april-2026.md — 2026 Red Dot Award (29 Apr 2026); second 2026 design award after iF
- knipper-hidden-hearing-loss-dementia-may-2026.md — Tübingen researcher Knipper public statement (1 May 2026); standard audiometry misses suprathreshold range where cognitive risk first appears
- tinyml-stm32-hearing-aid-speech-enhancement-2026.md — STM32 TinyML SE: 47% memory reduction, 4.26 ms latency (vs 10 ms ceiling) — neural SE within MCU budget

**Already-ingested in earlier run today:** apple-hearing-study-results-may-2026.md (covered separately AM)

**Email:** 662 words, 8 items, sent to door.punch_4o@icloud.com.
**Discord:** confirmation posted.

**Notes:** Today's threads: (1) consumer-grade longitudinal hearing data is now real (Apple n=160K) and is reframing outcome measures away from pure-tone thresholds; (2) the Knipper statement reinforces that critique mechanistically; (3) LLMs as audiology screeners are converging on triage-grade — not diagnosis-grade — usefulness; (4) TinyML continues to push neural SE down into MCU budgets, opening the OTC + budget-hearing-aid path for DNN noise reduction without proprietary chips.

## 2026-05-05 — Daily Hearing+AI Digest Ingestion (AM)

**Trigger:** Daily 06:50 Zurich digest run (post-email)

**Sources added (4):**
- fhh-2026-virtual-conference-may.md — Future of Hearing Healthcare 6th annual virtual conference (May 13/20/27, 2026); 23+ sessions; AI in hearing care as thematic pillar.
- oticon-va-portfolio-zeal-intent-verit-may-2026.md — Demant rolls Zeal (ITE), Intent miniBTE R, and Verit into U.S. VA supply schedule; broadest Oticon form-factor range on the VA channel to date.
- mdpi-speech-separation-survey-2026.md — Big Data and Cognitive Computing (MDPI) survey traces the U-Net→Conv-TasNet→Transformer→Mamba arc; identifies lightweight time-domain Mamba designs as the live front for hearing-aid SE.
- world-congress-audiology-seoul-may-2026.md — ISA's WCA 2026 in Seoul, May 24–27; non-Western health-system priorities (universal newborn screening, mobile audiometry, OTC adoption in LMIC) typically more prominent here.

**Pages updated:** 4
- wiki/concepts/speech-enhancement-neural-networks.md — added MDPI survey to sources; appended Mamba/state-space variant as architecture step #6 with U-Net→Wave-U-Net→Conv-TasNet→Transformer→Mamba arc.
- wiki/concepts/mamba-architecture.md — added MDPI survey to sources list.
- wiki/entities/demant-oticon.md — added VA portfolio expansion to Corporate Developments; updated sources list.
- wiki/index.md — refreshed "Last updated" header.

**Pages created:** 0 (existing concept/entity pages — speech-enhancement-neural-networks, mamba-architecture, demant-oticon, aaa-conference, aci-alliance-ci2026, auracast-bluetooth-le-audio — already cover today's themes).

**Email digest:** 617 words, 8 items, sent to door.punch_4o@icloud.com at 06:50 CEST.

**Notes:** Quieter day after the Apple Hearing Study news cycle. Today's threads: (1) the May conference calendar — CI2026 Chicago starts tomorrow (May 6–9), FHH virtual runs May 13/20/27, WCA Seoul May 24–27 — three different audiences in three weeks. (2) Mamba/state-space architectures are now formally validated as the next step in the speech-separation evolutionary arc per the MDPI survey, consistent with TokenSE-Mamba and the Applied Brain Research SSM-edge-audio work already in the wiki. (3) Oticon's VA channel expansion is structural, not flashy — but it's how unit volume actually shifts in this industry.

---

## 2026-05-06 — LinkedIn Drafts Ingest

**Operation:** ingest sources researched for daily LinkedIn post drafts.

**Sources added (1 new):**
- sources/karpathy-sequoia-ascent-2026.md — Karpathy fireside at Sequoia AI Ascent 2026 (recap published end of April 2026); Software 3.0 / agentic engineering framing; "you can outsource your thinking, but you can't outsource your understanding."

**Sources reused (existing, no edits):**
- sources/frontiers-ai-enabled-hearables-industry-2026.md — Frontiers AudioOto 2026 thematic study (already ingested; used as basis for Post 2). No content drift; existing summary already matches the public abstract on the six global themes.

**Pages created (1):**
- wiki/concepts/agentic-engineering-hearing-rd.md — new concept page applying Karpathy's Software 3.0 / "outsource thinking, not understanding" framing to hearing-aid R&D specifically (bounded search spaces, taste arbitrage, regulatory boilerplate, the specific judgments that still require human understanding).

**Pages updated:**
- wiki/syntheses/ai-understanding-gap-hearing-industry.md — added Sequoia source to frontmatter; added new section "The R&D-Side Counterpart: 'Outsource Thinking, Not Understanding'" linking to the new concept page; added cross-link to agentic-engineering-hearing-rd in Related Pages.
- wiki/index.md — refreshed "Last updated" header; added agentic-engineering-hearing-rd row to Concepts table.

**LinkedIn posts drafted (sent to Discord channel 1492462147127742565 + emailed to door.punch_4o@icloud.com):**
- Post 1: Karpathy's Sequoia Ascent 2026 — "outsource thinking, not understanding" applied to hearing R&D. Hook quote, four concrete judgment examples (SII leakage, audiogram selection, 70 vs 65 dB SPL failure modes, bandwidth/power budget violations), call to engagement on what young hearing scientists should still learn deeply.
- Post 2: Frontiers AudioOto 2026 thematic study — 18 industry leaders, six global themes (technology advancement, technical limitations, biometric sensors, AI agents, governance & ethics, society & behavior); three data-science angles: convergence, manipulation risk beyond clinical safety, governance gap vs FDA AI/ML SaMD scope.

**Notes:** 
- Post 2 framing of "just published" is slightly generous — the Frontiers paper was published 20 March 2026 (~6 weeks ago). Acceptable for a draft for user review; user can soften to "recently published" before posting to LinkedIn if desired.
- Today's posts continue the Karpathy thread as a recurring lens but with a fresh, distinct angle: prior posts covered LLM Wiki, autoresearch, idea files, CLAUDE.md, AI Psychosis. The Sequoia Ascent fireside introduces the explicit Software 3.0 / agentic engineering vocabulary and the "understanding > thinking" maxim — neither of which appears in earlier posts.
- The new agentic-engineering-hearing-rd concept page is the engineering-side counterpart to the existing ai-understanding-gap-hearing-industry synthesis (consumer side); the two now cross-reference each other.

## 2026-05-06 — Daily Hearing+AI Digest Ingest

**Operation:** ingest sources researched for the 6 May 2026 daily Hearing + AI email digest.

**Sources added (3 new):**
- sources/codec-intelligibility-se-behringer-arxiv-2026.md — Behringer et al., arXiv:2605.03776 (5 May 2026). Classical vs. neural speech codecs in clean/noisy conditions; SE preprocessing improves intelligibility + listening effort. Submitted to Interspeech 2026.
- sources/e2e-cfg-transformer-anc-yang-arxiv-2026.md — Yang et al., arXiv:2605.00494 (1 May 2026). Unsupervised transformer that directly generates ANC control filters end-to-end from accumulated error signals; departure from GFANC sub-filter decomposition.
- sources/brian-taylor-neurotone-rationale-april-2026.md — HearingTracker interview (27 Apr 2026) where Brian Taylor articulates the "post-fitting gap" rationale for moving from Signia to Neurotone AI; complements the prior 22 Apr PRWeb announcement.

**Sources reused (existing, no edits):**
- sources/apple-hearing-study-results-may-2026.md — already comprehensive on the 1 May 2026 findings (16% perception gap, walking-speed correlation, n=160K).
- sources/sony-otc-discontinued-hearingtracker-april-2026.md — already covers WSA/Sony partnership end (17 Apr 2026).
- sources/neurotone-ai-1000-clinics-april-2026.md — referenced as the prior milestone source for the Taylor narrative.
- sources/gap-urgenet-urgent-challenge-icassp-2026.md — used as referenced background for the URGENT 2026 challenge mention.

**Pages updated (3):**
- wiki/concepts/active-noise-cancellation.md — added new section "E2E-CFG: Unsupervised Transformer ANC (May 2026)" summarizing Yang et al.; added e2e-cfg-transformer-anc-yang-arxiv-2026.md to frontmatter sources and to the Sources list; added end-to-end-control-filter tag; bumped updated date.
- wiki/entities/neurotone-ai.md — added Taylor's stated rationale quote ("Hearing aids restore access to sound, but rehab can help people get a lot more benefit from that access") to the Brian Taylor Hire section; added the rationale source to frontmatter and Sources list; bumped updated date.
- wiki/concepts/auracast-bluetooth-le-audio.md — added new section "Codec Intelligibility under Noise (May 2026)" summarizing the Behringer et al. findings as they apply to LE Audio / Auracast (LC3 vs neural codec, SE co-evaluation, listening-effort metrics); added codec-intelligibility-se-behringer-arxiv-2026.md to frontmatter and Sources list; bumped updated date.

**Pages created (0):** Existing pages already covered the relevant concepts (ANC, Auracast, Neurotone AI, Apple hearing features, OTC market dynamics) — preferred updating in place rather than spawning near-duplicate pages.

**Email sent:** door.punch_4o@icloud.com — "🎧 Hearing + AI Daily Digest — 06 May 2026" — 7 items: 2 papers (Behringer codec, Yang ANC transformer), 3 industry news (Apple Hearing Study, Brian Taylor → Neurotone, Sony OTC exit), 1 AI/ML (Google AI Edge Eloquent), 1 worth-watching (ICASSP 2026 URGENT challenge).

**Notes:**
- Genuinely thin 48-hour window; the only strict-48h item was the Behringer arXiv paper. Stretched window to ~1 week; called this out honestly in the email rather than padding with filler.
- Discord confirmation message: "✅ Daily hearing+AI digest sent to door.punch_4o@icloud.com — 7 items covered."

---

## 2026-05-07 — Daily Hearing + AI Digest Ingest

**Operation:** ingest sources researched for the 7 May 2026 daily Hearing + AI email digest.

**Sources added (4 new):**
- sources/connect-hearing-audionova-rebrand-may-2026.md — Sonova rebrands US Connect Hearing chain (~160 centres) into AudioNova over a 2-year transition (announced 1 May 2026). Completes worldwide retail unification under one banner; coupled with the Sennheiser consumer-hearing divestiture.
- sources/liquid-ai-lfm25-audio-2026.md — Liquid AI LFM2.5-Audio-1.5B: 1.5B-parameter native audio-in/audio-out LLM running fully on-device, ~8x faster than predecessor. Targets phones/vehicles/IoT — the same compute envelope as a phone-paired hearable.
- sources/aaa-2026-leadership-panel-may.md — AAA 2026 industry leaders panel (Sonova, Demant NA, GN/ReSound, Starkey, Cochlear America). Two defining issues: AI integration as table-stakes; structural audiologist workforce shortage. Consensus push to reframe hearing loss as a core health issue.
- sources/ihs-better-hearing-month-2026.md — IHS Better Hearing Month 2026 campaign cites a 2026 study supporting a *causal* (not just correlational) hearing-loss → cognitive-decline link. Caveat noted: verify underlying study before external citation.

**Sources reused (existing, no edits):**
- sources/dnn-noise-reduction-intelligibility-2026.md / low-latency-dnn-noise-reduction-frontiers-2025.md — already cover the Frontiers low-latency DNN noise reduction for HI/CI listeners.
- sources/ai-cochlear-implant-language-prediction-2025.md / ai-predicts-ci-language-outcomes.md — already cover Northwestern's deep transfer learning model predicting pediatric CI language outcomes.
- sources/phonak-virto-r-infinio-red-dot-april-2026.md / phonak-infinio-if-design-award-2026.md — already cover Phonak Virto R Infinio's 2026 design awards sweep.
- sources/fhh-2026-virtual-conference-may.md — already covers the 13/20/27 May FHH conference.
- sources/auracast-european-public-venue-rollout-2026.md / auracast-uk-live-theaters-april-2026.md — already cover the UK theatre/station Auracast rollouts.

**Pages updated (6):**
- wiki/entities/sonova-ag.md — added "Recent Developments (May 2026)" section for the Connect Hearing → AudioNova rebrand; added bullet to Brands list; added connect-hearing-audionova-rebrand-may-2026 + sonova-silentcloud-acquisition-2026 to frontmatter sources; added vertical-integration-trend to related; bumped updated date.
- wiki/entities/aaa-conference.md — added "Industry Leaders Panel (May 2026 coverage)" section summarizing the cross-manufacturer panel framing AI + workforce as defining issues; added aaa-2026-leadership-panel-may to frontmatter sources and Sources list; added ai-understanding-gap-hearing-industry to related; bumped updated date.
- wiki/concepts/small-language-models-edge-ai.md — added Liquid AI LFM2.5-Audio row to the Open-Source Speech Models table (note: vendor license, not open); added source to frontmatter and Sources list; bumped updated date.
- wiki/concepts/audiologist-workforce-shortage.md — added aaa-2026-leadership-panel-may to frontmatter sources; bumped updated date.
- wiki/concepts/hearing-loss-dementia-link.md — added ihs-better-hearing-month-2026 to frontmatter sources; bumped updated date.
- wiki/syntheses/vertical-integration-trend.md — added entry #5 to the Timeline ("Connect Hearing → AudioNova US rebrand, May 2026"); added connect-hearing-audionova-rebrand-may-2026 to frontmatter sources; bumped updated date.

**Pages created (0):** All four ingested items mapped cleanly to existing pages — preferred in-place updates over near-duplicate pages, per wiki conventions.

**Email sent:** door.punch_4o@icloud.com — "🎧 Hearing + AI Daily Digest — 07 May 2026" — 9 items: 2 papers (Frontiers low-latency DNN for CI; Northwestern JAMA Oto AI predicts CI language outcomes), 4 industry news (Connect Hearing → AudioNova; AAA 2026 leadership panel; Phonak Virto R Infinio design awards; IHS Better Hearing Month proactive-care push), 1 AI/ML (Liquid AI LFM2.5-Audio-1.5B), 2 worth-watching (Auracast deployment progress; FHH Conference 13/20/27 May).

**Notes:**
- Industry-heavy news cycle today (consolidation + AAA fallout); arXiv 48-hour window was thin so used recent (2026) Frontiers and JAMA Oto papers that hadn't been featured in the prior digest.
- Avoided overlap with 6 May digest (Apple Hearing Study, Behringer codec paper, Yang ANC, Brian Taylor / Neurotone, Sony OTC exit, ICASSP URGENT) — none repeated.
- Discord confirmation message: "✅ Daily hearing+AI digest sent to door.punch_4o@icloud.com — 9 items covered (2 papers, 4 industry, 1 AI/ML, 2 worth-watching)."
