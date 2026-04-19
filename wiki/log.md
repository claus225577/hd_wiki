# Wiki Log

Chronological record of all wiki operations.

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
