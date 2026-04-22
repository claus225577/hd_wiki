# Wiki Log

Chronological record of all wiki operations.

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
