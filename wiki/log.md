# Wiki Log

Chronological record of all wiki operations.

---

## Digest — 2026-06-22
**Operation:** Daily hearing+AI digest compiled and sent to door.punch_4o@icloud.com.
**Items covered:** 11 (2 papers, 5 industry, 2 AI/ML, 2 worth-watching) + 5 quick stats.
**Word count:** 608 (under 800-word cap).

**Sources referenced (all already ingested — no new wiki pages or source files needed):**
- `dal-differentiable-auditory-loop-google-june-2026.md` — DAL framework, arXiv:2606.04103
- `ai-cochlear-implant-language-prediction-2025.md` / `pediatric-ci-language-prediction-transfer-learning-2025.md` — CUHK + Lurie / Northwestern pediatric CI MRI predictor
- `phonak-ai-excellence-award-march-2026.md` — Phonak Virto R + Infinio Ultra Sphere 2026 AI Excellence Awards
- `airpods-hearing-aid-country-expansion-may-2026.md` / `apple-airpods-india-italy-taiwan-may-21-2026.md` — Apple AirPods Hearing Aid 100+ country footprint
- `veterans-hearing-aid-improvement-act-house-jun-2026.md` — VA 2-year OTC HA pilot bill
- `signia-insio-charge-go-cic-ix-2026.md` — Signia Insio Charge&Go CIC IX US launch
- `elehear-delight-cic-otc-ces-2026.md` — Elehear Delight CIC at CES 2026
- `tiny-ml-to-tiny-dl-survey-acm-2026.md` — TinyML → Tiny DL survey, arXiv:2506.18927
- `tinyml-stm32-hearing-aid-speech-enhancement-2026.md` — SSIES emergency-sound TinyML (Internet of Things)
- `auracast-uk-live-theaters-april-2026.md` / `auracast-rollout-2025-2026.md` — Auracast UK venue + station deployments
- `orka-o1-pro-bose-anc-awe-2026.md` — ORKA × Bose RIC w/ ANC at AWE 2026

**New source file:** `hearing-ai-digest-2026-06-22.md` (digest record only; no concept/entity page changes).

**Action:** No new wiki pages or new external-source files created — today's research fully overlapped with existing wiki coverage. Logged for traceability.

---

## Digest — 2026-06-20
**Operation:** Daily hearing+AI digest compiled and sent to door.punch_4o@icloud.com.
**Items covered:** 12 (3 papers, 5 industry, 2 AI/ML, 2 worth-watching).

**Sources referenced (all already ingested — no new source files created):**
- `arxiv-2507-07043-selective-noise-cancellation-review-2026.md` — Advances in Intelligent Hearing Aids review
- `dal-differentiable-auditory-loop-google-june-2026.md` — DAL framework for hyper-personalized fitting
- `gap-urgenet-urgent-challenge-icassp-2026.md` — ICASSP 2026 URGENT SE Challenge
- `widex-allure-ai-launch-june-2026.md` — Widex Allure AI RIC launch
- `orka-o1-pro-bose-anc-awe-2026.md` — ORKA × Bose ANC RIC at AWE 2026
- `veterans-hearing-aid-improvement-act-house-jun-2026.md` — bipartisan VA OTC HA pilot bill
- `airpods-hearing-aid-country-expansion-may-2026.md` — AirPods Hearing Aid country expansion
- `hlaa-2026-convention-louisville-june-2026.md` — HLAA 41st convention
- `ai-predicts-ci-language-outcomes.md` — CUHK/Lurie predict-to-prescribe pediatric CI
- `tiny-ml-to-tiny-dl-survey-acm-2026.md` — TinyML → Tiny DL survey

**Action:** No new wiki pages or sources created; today's research overlapped fully with existing wiki coverage. Logged for traceability only.

---

## Lint — 2026-06-07
**Pages scanned:** 103
**Issues found:** 30
**Auto-fixed:** 27

### Orphans
- `syntheses/clinical-ml-convergence-june-2026.md` — not referenced by any other page. Fixed by adding to `hearing-aid-ai-stack-2026.md` related field.
- `concepts/continual-learning-hearing-ai.md` — was listed as orphan by bash check; confirmed referenced by `training-deployment-distribution-gap.md` (false positive from grep).
- `concepts/non-intrusive-intelligibility-prediction.md` — was orphan; fixed by updating `speech-enhancement-evaluation-stack-cracks-may-2026.md` related links.
- `entities/clarity-prediction-challenge.md` — was orphan; fixed by correcting path in `non-intrusive-intelligibility-prediction.md` and `speech-enhancement-evaluation-stack-cracks-may-2026.md`.

### Broken links (related: fields)
Before fixes, 26 broken related: entries found across 5 pages. All resolved:

- `concepts/acoustic-feedback-cancellation.md` → `dsp-classical-vs-deep-learning.md` (file does not exist). Fixed: replaced with `speech-enhancement-neural-networks.md`; also removed duplicate `dnn-architectures-hearing-aids.md` entry.
- `entities/clarity-prediction-challenge.md` → 4 concept entries missing `../concepts/` prefix. Fixed.
- `concepts/non-intrusive-intelligibility-prediction.md` → `clarity-prediction-challenge.md` missing `../entities/` prefix. Fixed.
- `syntheses/clinical-ml-convergence-june-2026.md` → `../concepts/differentiable-cochlea.md` (wrong filename; correct is `differentiable-cochlear-models.md`). Fixed. Also `../concepts/speech-enhancement-evaluation-stack-cracks-may-2026.md` (is a synthesis, not concept). Fixed.
- `syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md` → 12 entries missing `../concepts/` or `../entities/` prefix. Fixed.
- `syntheses/va-as-hearing-ai-dataset-may-2026.md` → 6 entries missing `../entities/` or `../concepts/` prefix. Fixed.

### Missing source files
- `syntheses/pretraining-corpus-as-moat-hearing-ai.md` references `autoresearch-karpathy-april-2026.md` which does not exist in `sources/`. Needs human review — either the file was not ingested or was ingested under a different name.

### Stale sources (before 2026-03-07, fast-moving topics)
The following sources are older than 3 months and cover fast-moving AI/ML/hardware topics where claims may have aged:
- `starkey-genesis-ai-health.md` (2023) — 3-year-old product page; Omega AI has since superseded Genesis AI.
- `ai-audiology-scoping-review.md` (2024) — AI landscape survey; field has shifted materially.
- `ai-predicts-ci-language-outcomes.md`, `auditory-attention-decoding-2025.md`, `cochlear-implant-ai-innovations.md`, `dnn-hearing-aids-frontiers-2025.md`, `low-latency-dnn-noise-reduction.md` (all 2025 undated) — early 2025 sources; specific benchmarks may be superseded.
- `marketrak-2025.md` (2025 annual survey) — market data; 2026 update expected.
- `phonak-deepsonic-ai-chip.md` (2025-10) — chip specs may be superseded by Infinio Sphere updates.
- `eurotrak-uk-2025-adoption-aug-2025.md` (2025-08) — annual survey; BIHIMA Q1 2026 now available as more recent market data.
- `interspeech-2026-audio-reasoning-challenge.md` (2026-02) — benchmark challenge still active; no results yet.

### Potential duplicates
- No clear duplicate concept pages found. `dnn-in-hearing-aids.md` and `dnn-architectures-hearing-aids.md` cover overlapping territory but serve distinct purposes (practical application vs architectural taxonomy).

### Missing cross-references
- All orphan pages now have at least one incoming link. No additional missing cross-references flagged.

### Too-large pages (>500 lines)
- None found. Largest page is `concepts/speech-enhancement-neural-networks.md` at 313 lines — within acceptable range.

### Index issues fixed
- Index already contained all 103 wiki pages. No additions or removals needed.
- Note: `comparisons/ai-hearing-aid-platforms-2026.md`, `entities/aci-alliance-ci2026.md`, and 6 synthesis pages that appeared missing were actually present in the index table — an earlier grep false-negative due to the table format.

### Needs human judgment
- `syntheses/pretraining-corpus-as-moat-hearing-ai.md` → missing source `autoresearch-karpathy-april-2026.md`. Investigate whether this source exists under a different name or needs to be created.
- `starkey-genesis-ai-health.md` (2023) — consider whether to update or archive, given Omega AI has replaced Genesis AI as Starkey's flagship.
- `entities/who-hearing-program.md` has an empty `sources: []` field — needs at least one source file to be properly grounded.
- Consider creating `concepts/clinician-ai-consent-and-trust.md` (flagged in log 2026-05-27 as pending) once a second corroborating data point is available.

---

## 2026-06-07 — Daily Hearing+AI Digest Ingest

**Operation:** Ingested net-new sources from the 7 Jun 2026 hearing+AI digest into the wiki.

**New source files (2):**
1. `cilcare-cil001-massgeneral-tinnitus-may-2026.md` — Cilcare announced (SelectUSA Summit, early May 2026) US tinnitus trial preparation of CIL001 at Mass General with Maison's auditory neuroscience group + CBSET partnership. CIL001 targets cochlear synaptopathy — the mechanism implicated in tinnitus, hyperacusis, and "hidden hearing loss." Disease-modifying lane parallel to behavioural DTx.
2. `bihima-q1-2026-uk-sales-jun-2026.md` — UK private-sector Q1 2026 sales 145,575 units (+12.5% QoQ); rechargeable share 93%. Disposable-battery models a residual 7% niche. Rechargeable lock-in as precondition for sustained on-device DNN inference budgets.

**Wiki pages updated (2):**
- `concepts/digital-therapeutics-tinnitus.md` — added Cilcare CIL001 to Competitive Landscape (pharma lane); added source to frontmatter + Sources; bumped updated to 2026-06-07.
- `concepts/hearing-aid-market-dynamics.md` — added "UK Private Channel — Q1 2026 (BIHIMA, Jun 2026)" subsection under Global Hearing Burden; added source to frontmatter; bumped updated to 2026-06-07.

**No new wiki pages created** — both items fit existing concept pages cleanly.

**Skipped (already in wiki):**
- arXiv:2606.04221 (FPGA SE feasibility, Olalere et al.) — covered by `sources/fpga-sudormrf-feasibility-radboud-june-2026.md` (ingested 4 Jun).
- Veterans Hearing Aid Improvement Act (5 Jun 2026) — covered by `sources/veterans-hearing-aid-improvement-act-house-jun-2026.md` (ingested 5 Jun).
- Apple AirPods country expansion — covered by `sources/airpods-hearing-aid-country-expansion-may-2026.md` + variants.
- Auracast venue rollout — covered by `sources/auracast-*` set.
- TytoCare De Novo AI otoscopy — outside core hearing-aid scope per 5 Jun policy; left as digest "Worth Watching" only.

**Pages touched this ingest: 4** (2 sources created, 2 pages updated, plus this log entry).

---

## 2026-06-05 — Daily Hearing+AI Digest Ingest

**Operation:** Ingested new sources from the 5 Jun 2026 hearing+AI digest into the wiki.

**New source files (3):**
1. `arxiv-2606-05575-sbrf-schrodinger-bridge-jun-2026.md` — Lu, Lv, Hu, Xu (4 Jun 2026). SB-RF combines rectified flow with Schrödinger bridge theory for one-step generative SE; competitive on VoiceBank-DEMAND and a low-SNR set with single-pass inference.
2. `arxiv-2606-05911-dbhn-net-snn-ann-fan-jun-2026.md` — Fan, Liu, Zhou et al. (4 Jun 2026; accepted IEEE TPAMI). Dual-branch hybrid SNN + ANN for monaural SE; 7.5x avg compute reduction vs strong baselines.
3. `nuance-audio-western-univ-clinical-study-2026.md` — Western University National Centre for Audiology clinical validation of Nuance Audio Glasses (improved speech-in-noise, reduced listening effort, mild-to-moderate loss).

**New wiki pages (1):**
- `entities/essilorluxottica.md` — First entity page for EssilorLuxottica, framed around Nuance Audio Glasses and the optical-retail distribution disruption thesis.

**Wiki pages updated (4):**
- `concepts/speech-enhancement-neural-networks.md` — added SB-RF and DBHN-Net sources; bumped `last_change` and `updated`.
- `concepts/probabilistic-generative-models-hearing-ai.md` — added SB-RF source (one-step generative SE).
- `concepts/tinyml-edge-ai.md` — added DBHN-Net source (SNN+ANN low-compute hybrid).
- `concepts/otc-hearing-aids.md` — added Nuance source and cross-link to EssilorLuxottica entity.
- `entities/apple-hearing-features.md` — added EssilorLuxottica to `related:` (other major non-OEM consumer channel).
- `index.md` — added EssilorLuxottica row to Entities table.

**Skipped (already in wiki):**
- arXiv:2606.04221 (FPGA SE feasibility, Olalere et al.) — covered by `sources/fpga-sudormrf-feasibility-radboud-june-2026.md`.
- arXiv:2606.04103 (DAL, Google) — covered by `sources/dal-differentiable-auditory-loop-google-june-2026.md`.
- arXiv:2606.03832 (DFC-IL, Voit/Doclo) — covered by `sources/arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md`.
- ORKA × Bose RIC w/ ANC at AWE 2026 — covered by `sources/orka-o1-pro-bose-anc-awe-2026.md`.
- Phonak 2026 AI Excellence Award — covered by `sources/phonak-ai-excellence-award-march-2026.md`.
- Apple AirPods Hearing-Aid country expansion — covered by `sources/airpods-hearing-aid-country-expansion-may-2026.md` (+ India/Italy/Taiwan and Philippines variants).
- TytoCare FDA De Novo for AI Otoscopy — surfaced today but outside core hearing-aid scope; left as digest "Worth Watching" only.

**Pages touched this ingest: 9** (3 sources created, 1 new entity, 5 pages updated, plus this log entry).

---

## 2026-05-31 — Lint Pass

**Operation:** Automated lint audit of the full wiki. Checked index completeness, orphan status, broken cross-references, broken source links, stale pages, duplicate concepts, and missing cross-links.

**Scope:** 57 concept pages, 24 entity pages, 4 comparison pages, 10 synthesis pages, 400+ source files.

---

### Fixes Applied (3 automatic)

**1. Missing index entry — `concepts/lalm-selective-auditory-attention.md`**
- Page existed (created 2026-05-22) but was never added to wiki/index.md.
- Not orphaned: had 1 incoming link from `auditory-attention-decoding.md`.
- Fixed: added row to Concepts table in wiki/index.md, between cross-lifespan-speech-models and listening-effort-evaluation.

**2. Broken source links — `concepts/lalm-selective-auditory-attention.md` Sources section**
- `../../sources/l3-se-linguistic-hallucination-arxiv-may-2026.md` → corrected to `l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md`
- `../../sources/cross-lifespan-speaker-diarization-arxiv-may-2026.md` → corrected to `cross-lifespan-diarization-usc-may-2026.md`
- Note: frontmatter `sources:` field was already correct; only the inline markdown links at page bottom were wrong.

**3. Missing cross-links to `lalm-selective-auditory-attention.md`**
- `linguistic-hallucination-speech-enhancement.md` — added lalm page to `related:` (sibling evaluation-stack failure mode)
- `syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md` — added lalm page to `related:` (multilingual source confusion is the fourth crack in that series)

---

### Issues Requiring Human Judgment

**Stale pages (fast-moving topics, not updated in 6+ weeks as of 2026-05-31):**
- `syntheses/hearing-ai-research-landscape-2025.md` — last updated 2026-04-17 (44 days). Title says "2025" but content draws on April 2026 sources. Consider: rename to `hearing-ai-research-landscape-2026.md` or add a prominent "snapshot" note.
- `concepts/audio-reasoning-chain-of-thought.md` — last updated 2026-04-16 (45 days). Fast-moving topic (Interspeech 2026 Audio Reasoning Challenge launched since). Flag for update next relevant ingest.
- `concepts/world-models-hearing-ai.md` — last updated 2026-04-16 (45 days). Closely related to continual-learning-hearing-ai (created 2026-05-27) — consider whether they should cross-link or partially merge.
- `concepts/dnn-architectures-hearing-aids.md` — last updated 2026-04-21 (40 days). Foundation-model-fusion and LALM developments since are material.

**Carry-forward flags (from log, repeated for visibility):**
1. `concepts/auditory-attention-decoding.md` — needs methodology asterisk: LOPEO paper (Zhang/Liang et al., arXiv:2605.25605, ~26 May 2026) shows DNN AAD decoders systematically overestimate accuracy on unbalanced EEG datasets. Existing claims rest on potentially inflated numbers. Add asterisk on next corroborating replication ingest.
2. `concepts/clinician-ai-consent-and-trust.md` — ready to create pending a second corroborating data point (regulator statement, professional-body position, or second on-record clinician quote). AAA 2026 + WCA 2026 + FHH 2026 all surfaced this theme; three conferences may now be sufficient trigger.
3. `comparisons/cocktail-party-stack-front-to-back.md` — log flagged this as "one more entry triggers" on 2026-05-27. The LALM/MUSA page (`lalm-selective-auditory-attention.md`, created 2026-05-22) provides exactly that fourth anchor. Consider creating this comparison page now.

**Orphan analysis:**
- No true orphans found (all pages have at least one incoming link from another wiki page).
- `lalm-selective-auditory-attention.md` was the least-connected page (1 incoming link before this lint); now has 3 with the cross-links added above.

**Duplicate concept check:**
- No duplicate concepts requiring merge found. `world-models-hearing-ai.md` and `continual-learning-hearing-ai.md` have overlapping scope (personalization, adaptation) but are structurally distinct enough to keep separate; a `related:` link between them would help (currently absent).
- `dnn-in-hearing-aids.md` and `dnn-architectures-hearing-aids.md` cover adjacent ground; both are well-linked to each other. No merge recommended.

**Pages that could benefit from splitting (>150 lines):**
- `concepts/on-device-ml-hearing-aids.md` — 162 lines. Dense hub page; splitting would harm navigation. Recommend adding internal section anchors instead.
- `syntheses/hearing-aid-ai-stack-2026.md` — 156 lines. Consider a "What Changed in 2026" addendum rather than a split.
- `concepts/dnn-architectures-hearing-aids.md` — 164 lines. Most overdue for update anyway; a refresh would naturally right-size it.

**Index size:** wiki/index.md front-matter summary section is very long (the rolling log of operations embedded in italics). This is intentional per schema but makes the file large. No action required — the schema calls for it.

---

### Stats

| Category | Files on disk | In index |
|---|---|---|
| Concepts | 57 | 57 (was 56 before this lint) |
| Entities | 24 | 24 |
| Comparisons | 4 | 4 |
| Syntheses | 10 | 10 |
| **Total wiki pages** | **95** | **95** |
| Sources | 400+ | n/a |

---

## 2026-05-27 — LinkedIn drafts ingest: Nakazawa CPC3 fusion + Xiao et al. representation-centric continual learning

**Operation:** Ingested today's LinkedIn drafts research into the wiki. Two arXiv papers from the past five days that together address the constructive side of the May 19 "three cracks" synthesis: (1) Nakazawa (22 May) shows what the *replacement evaluator* is starting to look like — frame-aligned mid-fusion of two frozen foundation-model encoders on CPC3; (2) Xiao, Wang, Holden & Dang (24 May) reframes hearing-aid *personalization* as a continual-learning problem at the representation-geometry layer rather than the parameter-handle layer the OEM industry has used for two decades.

**Sources added (2):**
- `frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md` — Nakazawa, arXiv:2605.23619 (22 May 2026). Attacks CPC3 (3rd Clarity Prediction Challenge — real measured HA signals, dynamic environments, hearing-impaired listener panel) with two frozen speech foundation models: **Nvidia Canary** (ASR-side, lexical-content-compressing) × **Microsoft WavLM** (SSL-side, paralinguistic-preserving). Compares uniform score averaging, late-pool, cross-attention, frame-aligned, reverse-aligned under a left/right-preserving **binaural** framework. Best result: prepare WavLM with a learnable strided convolution to land on Canary's coarser timeline → concatenate frame-aligned → pool → small trainable head. **Eval RMSE 24.96 / Eval Corr 0.796.** Headline inductive bias: coarse local temporal correspondence before pooling.
- `continual-learning-speech-audio-representation-may-2026.md` — Xiao, Wang, Holden & Dang, arXiv:2605.24863 (24 May 2026). Argues that standard CL methods (rehearsal, EWC, parameter isolation, adapters with clean task labels) assume cleanly separable tasks, but speech foundation models encode **highly entangled, continuous representations that jointly carry linguistic, speaker, and paralinguistic factors in a shared latent space**. The right unit of analysis is **how representation geometry evolves under non-stationary acoustic conditions**, not which "task" the system is on. Calls for a representation-centric taxonomy. Hearing aids are the canonical commercial deployment target: non-stationarity is the baseline, entanglement is constitutive, continuous supervision is available, every fitting is structurally an update.

**Wiki pages created (3 concepts + 1 entity):**
- `concepts/non-intrusive-intelligibility-prediction.md` — The metric class that takes audio + audiogram and predicts hearing-impaired intelligibility without a clean reference. Anchored by CPC and the post-HASPI evaluator stack the field is building on top of foundation-model fusion.
- `concepts/foundation-model-fusion-speech.md` — The methodology winning on CPC3 today: combine two or more frozen encoders with complementary inductive priors (typically one ASR-trained and one SSL-trained) and train a small head over the fused representation. Documents the fusion-strategy table (uniform / pool-late / cross-attention / frame-aligned / reverse-aligned), names the encoder-pair × fusion-architecture open search space, and locates where this can deploy (server-side viable today, companion-phone borderline, on-chip out of reach).
- `concepts/continual-learning-hearing-ai.md` — Maps the Xiao et al. argument onto the hearing-aid stack. Industry has called this problem "personalization" for two decades (gain values, scene-classifier weights, user-toggled boosts like Widex Clarity Boost, Signia Assistant). ML calls it continual learning. The two communities have never seriously talked. Documents the entanglement-vs-task-separation mismatch, names the unit-of-personalization shift from parameter-handle to representation-geometry, and lays out where the update runs (companion-phone consolidation tier), the telemetry / privacy implications (DP, federated, secure aggregation as natural pairing), and the regulatory implications (CL-aware predetermined change control plan with representation-level update bounds).
- `entities/clarity-prediction-challenge.md` — The CPC1/CPC2/CPC3 challenge entity. CPC3 (deadline 31 Jul 2025, results presented at ISCA workshop satellite of Interspeech 2025 Rotterdam, 22 Aug 2025) — fully dynamic listening environments, real backgrounds, measured hearing-aid signals, 21 submissions from 14 teams, both tracks populated. Documents how CPC3 has become the *de facto* benchmark for follow-up papers in 2026, and how the competitive design choice has shifted from "which single foundation model" to "which encoder pair, and where do they meet."

**Existing pages updated (1 synthesis + 1 index):**
- `syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md` — Bumped updated to 2026-05-27. Added new source row in frontmatter (Nakazawa) and new related cross-link (clarity-prediction-challenge). Added new section **"Update — 27 May 2026: What the Replacement Architecture Is Starting to Look Like"** documenting the Nakazawa CPC3 result, what it tells the field (lever moved up one layer; binaural preservation as design constant; server-side compact-head frozen-backbone deployment shape; CPC3 becoming the training set for evaluation models), and what is still missing (axes 2 and 3 — linguistic faithfulness and listening effort — remain unbuilt as deployable foundation-model-fusion-class metrics). New source row added in Sources.
- `wiki/index.md` — Added 2026-05-27 entry at top documenting today's ingest (2 sources, 3 new concept pages, 1 new entity page, 1 updated synthesis). Previous 2026-05-26 entry preserved below as "Earlier 2026-05-26 entry."

**Underlying LinkedIn posts:**
1. Frame-aligned fusion of Canary + WavLM on CPC3 — the next hearing-aid intelligibility metric is a fusion-architecture search, not a new encoder; the lever moves from "which encoder" to "where do they fuse"; binaural preservation is now a design constant; server-side / compact-head / frozen-backbone is the deployment shape; CPC3 is becoming the field's training set for evaluation models.
2. Representation-centric continual learning — hearing-aid personalization is the canonical commercial deployment target the field hasn't claimed yet; industry calls it "personalization," ML calls it "continual learning," and the two communities have never seriously talked; unit of personalization shifts from "what slider moved" to "what shifted in the latent representation"; companion phone is the natural consolidation tier; regulator-facing predetermined change control plan is the missing artifact.

**Underlying angle:** The two papers, eight days apart, complete a pattern. The May 5–12 trio (Behringer / Wang / de Oliveira) said the *evaluation stack* was structurally inadequate for the modern generative-SE regime. Nakazawa (22 May) is the first concrete look at what the *replacement evaluator* is — multi-encoder mid-fusion on listener-grounded CPC3 labels, binaural-preserving, server-side. Xiao et al. (24 May) names the parallel reframe on the *learning* side — the static-model assumption that underlies both the locked-medical-device regulatory frame and the parameter-handle personalization tradition is mismatched against representation entanglement in the foundation models the field is now fine-tuning on. Together: the field is migrating to a foundation-model-fusion evaluation tier and a representation-centric continual-learning training tier in the same quarter. The OEM that ships both first owns the next decade.

---

## 2026-05-26 — LinkedIn drafts ingest: Apple May 21 multi-modal / LMIC wave + Pichora-Fuller Aram Glorig Award

**Operation:** Ingested today's LinkedIn drafts research into the wiki. Two structurally novel events in the past five days — Apple's 21 May rollout of hearing-test screening into India alongside multi-modal Apple Watch screening into India/Taiwan, and the ISA's award of its highest honor to Kathy Pichora-Fuller at WCA 2026 Seoul on 26 May with a keynote naming communication accessibility as the missing outcome construct.

**Sources added (2):**
- `apple-airpods-india-italy-taiwan-may-21-2026.md` — On 21 May 2026 Apple pushed three different health-screening modalities into two new countries in a single iOS rollout: AirPods Pro Hearing Test → **India** (first launch at scale in an LMIC of this size; audiologist density ~1 per 500K-6M vs ~1 per 25K in the U.S.); AirPods Hearing Aid Mode → **Italy** (mode upgrade beyond 12 May EU wave); Apple Watch Sleep Apnea notifications → **India**; Apple Watch Hypertension notifications → **Taiwan**. Apple Health features now active in **160+ countries**. Structurally distinct from the 12 May wave because (a) India is the first LMIC of this scale, and (b) it is the first time three screening modalities (hearing + sleep + cardiac) shipped to two new countries in a single push — a sensor-fusion deployment cadence no traditional medical-device OEM can match.
- `wca-2026-pichora-fuller-aram-glorig-may-26-2026.md` — 37th World Congress of Audiology (Seoul, 24-27 May 2026); on 26 May the International Society of Audiology presented its highest honor — the **Aram Glorig Award** — to **M. Kathleen (Kathy) Pichora-Fuller** (Professor Emerita Toronto, Adjunct SFU Gerontology) with the lecture **"Hearing and Healthy Aging: The Imperative for Communication Accessibility."** Pichora-Fuller is co-author of the **FUEL framework** (Pichora-Fuller, Kramer et al., Eriksholm 2015 / *Ear and Hearing* 2016) operationalizing listening as **demand × resources × motivation**, and active ISA representative on the WHO World Rehabilitation Alliance working group on primary care leading the Hearing in Later Life working group. ISA recognition is the most senior endorsement to date that the hearing-AI evaluation construct has outrun its measurement stack.

**Wiki pages created (3):**
- `entities/kathy-pichora-fuller.md` — Researcher entity page documenting four structural contributions (FUEL framework, three decades of cognitive-audiology work, WHO Rehabilitation Alliance role, healthy-aging framing). Includes a full table mapping the four existing hearing-AI evaluation layers (signal / lexical / neural attention / effort) to her proposed interactional fifth layer (communication accessibility). Names three concrete consequences for ML-side R&D: unit of evaluation shifts from signal to conversation; FUEL is already the operational specification (motivation × demand × resources); first OEM that ships a HASPI-equivalent for communication accessibility owns the next-decade outcome conversation.
- `concepts/communication-accessibility-metric.md` — The fifth-axis hearing-AI evaluation primitive named at the field's flagship congress in May 2026. Documents where it sits in the five-layer stack and why it cannot be reduced to intelligibility / WER / AAD / effort. Lays out what "built" would look like (standardized scoring framework, wearable telemetry primitives for FUEL components, conversation as unit of evaluation, HASPI-equivalent for accessibility, regulatory acceptance). Argues three of the five required pieces are squarely in the AI/ML wheelhouse (continuous telemetry inference, multi-speaker conversation parsing, longitudinal outcome modeling). Documents the structural May 2026 alignment across Mesgarani / Behringer / Wang / de Oliveira / Gijbels / Pichora-Fuller papers and the Aram Glorig keynote. Open questions covering composite-vs-vector, telemetry sufficiency, regulatory taxonomy, LMIC implications.
- `syntheses/lmic-screening-platform-asymmetry-may-2026.md` — Unifies the 21 May Apple wave into three compounding structural events: (1) screening-layer collapse to near-zero marginal cost in a 1.4 billion-person market; (2) three screening modalities + same wearer + same day as the first deployed substrate for cross-modal health-phenotyping at consumer scale; (3) the audiogram corpus India will generate within 24 months as the missing piece for the pre-training-corpus-as-moat thesis. Strategic implications for market sizing, competitive positioning (verification specialist / premium moat / platform partnership), LMIC healthcare governance asymmetry, and the question of whether the audiogram is the right primary outcome at all when no audiologist is in the loop. Watch-list for CDSCO guidance, WHO statement, OEM India responses, Apple India-cohort publication, Apple Watch hearing-related sensor feature, second-platform analog launch.

**Existing pages updated (4):**
- `entities/apple-hearing-features.md` — Added 21 May 2026 multi-modal wave bullet under Software Requirements naming India/Italy/Taiwan + sleep + cardiac modalities + 160+ countries footprint and explicit linkage to the new synthesis. Added new source to frontmatter sources. Added 5 new concept/synthesis cross-links to related: hearing-care-funnel-attribution, audiologist-workforce-shortage, lmic-screening-platform-asymmetry-may-2026 synthesis (plus existing kept). Added new tags lmic / india / multi-modal-screening. Added new source row in Sources list. Bumped updated to 2026-05-26.
- `entities/vcca-computational-audiology.md` — Added new "Aram Glorig Award — Kathy Pichora-Fuller (26 May 2026)" subsection under the WCA 2026 CAN programming section with the keynote title, FUEL framing, the field's evaluation gap argument, and cross-links to the new entity + concept pages. New source added to frontmatter. Related fields expanded with kathy-pichora-fuller entity + listening-effort-evaluation + communication-accessibility-metric concepts. Added aram-glorig-award + pichora-fuller tags. New source row in Sources. Bumped updated to 2026-05-26.
- `concepts/listening-effort-evaluation.md` — Added new "FUEL — The Operational Specification (Pichora-Fuller 2016)" section as the operational substrate for the listening-effort concept, explicitly naming demand × resources × motivation with motivation as the first-class variable distinction. Cross-linked kathy-pichora-fuller entity + communication-accessibility-metric concept. New source added to frontmatter. fuel-framework + communication-accessibility tags added. New source row in Sources. Bumped updated to 2026-05-26; last_change note updated to reflect the FUEL operationalization addition and the Aram Glorig Award framing.
- `concepts/subjective-objective-hearing-gap.md` — Added cross-link to communication-accessibility-metric as the longitudinal interactional layer that aggregates the subjective signal into an outcome. Cross-linked listening-effort-evaluation as the cognitive-cost primitive underneath the subjective experience. Cross-linked kathy-pichora-fuller entity. New source added to frontmatter. fuel-framework + communication-accessibility tags added. New source row in Sources. Bumped updated to 2026-05-26.

**Index updates:**
- New top entry on `wiki/index.md` documenting today's ingest.
- Added 2 new concept rows: listening-effort-evaluation (previously orphaned from the Concepts table; surfaced during this ingest) and communication-accessibility-metric.
- Added 1 new entity row: kathy-pichora-fuller.
- Added 1 new synthesis row: lmic-screening-platform-asymmetry-may-2026.
- Bumped apple-hearing-features entity row (date + tags), vcca-computational-audiology entity row (date + tags), subjective-objective-hearing-gap concept row (date + tags).

**Underlying LinkedIn posts:**
1. Apple AirPods Pro hearing test launches in India — the LMIC inflection point for the hearing-care funnel; screening layer collapses to near-zero marginal cost in a 1.4B-person market; multi-modal sensor-fusion deployment cadence no traditional OEM can match; competitive question shifts from "best on-chip algorithm" to "best partnership with the platform that owns the screening funnel."
2. Pichora-Fuller wins the Aram Glorig Award at WCA 2026 Seoul — communication accessibility as the objective function ML still has not built for; FUEL framework (demand × resources × motivation) is already the operational specification, the telemetry stack to instrument it on a real wearer over a real day is the missing piece; first OEM to ship a HASPI-equivalent for communication accessibility owns the outcome conversation for a decade.

**Underlying angle:** The May 2026 alignment is structural — Mesgarani (Columbia ECoG closed-loop AAD, *Nat Neurosci* 11 May) / Behringer (codec listening effort, arXiv 5 May) / Wang et al. (L3-SE linguistic hallucination, arXiv 9 May) / de Oliveira/Peer/Gerkmann (ASR too good to be true, arXiv 12 May) / Gijbels (multimodal hearing assessment, *FAuOt* March 2026) / Pichora-Fuller (Aram Glorig Award keynote, 26 May) — point at a **five-axis evaluation reframe**: signal × lexical × neural × effort × **interactional / communication accessibility**. The fifth axis is being named at the field's flagship congress this week. Simultaneously, Apple's 21 May LMIC wave generates the demographic and audiogram-corpus substrate the new metric layer needs. The OEM (or platform) that ships the missing fifth axis first will own the next decade's outcome conversation — clinical, regulatory, reimbursement.

**Lint note:** `concepts/listening-effort-evaluation.md` was missing from the Concepts table in `wiki/index.md` since its creation on 2026-05-18 — fixed in this ingest.

---

## 2026-05-21 — Ad-hoc ingest: Widex Allure AI RIC + USC cross-lifespan diarization

**Operation:** Ingested two ad-hoc sources surfaced on May 20-21, 2026 — Widex Allure AI RIC product launch + Compass Cloud 2.0 (Hearing Review, May 20) and the USC cross-lifespan speaker-diarization paper (arXiv:2604.05201 v2, May 19).

**Sources added (2):**
- `widex-allure-ai-may-2026.md` — Widex (WSA) launched the Allure AI RIC on May 20 2026: first commercial HA with a **user-toggled** AI co-processor on the proprietary W1 chip; default mode is Widex's classical PureSound + ZeroDelay pipeline, AI engaged on demand via "Clarity Boost" button; manufacturer-claimed up to 6 dB higher output SNR vs competitor AI HAs when engaged; 32 h total battery / up to 6 h AI-on or streaming; mFi/ASHA/LE Audio/telecoil/hands-free; standard + Charge & Clean + Qi portable charging. Announced alongside **Compass Cloud 2.0**, billed as world's first cloud-based fitting software (Adaptation Manager, SmartSpeak, expanded Data Logging, Sound Class Adjustments, Transfer Settings, 99.9%+ uptime, 4/5 HCP satisfaction). Staged market launch — 5 markets June 1 2026, US November 1 2026. Executive quote from Ngozi Amobi: "preserving natural sound as the foundation and introducing AI processing only when it adds value."
- `cross-lifespan-diarization-usc-may-2026.md` — Anfeng Xu, Tiantian Feng, Shrikanth Narayanan (USC); arXiv:2604.05201 v2 posted May 19 2026; eess.AS. "Exploring Speech Foundation Models for Speaker Diarization Across Lifespan." End-to-end neural diarization built on speech foundation models, evaluated across children, adults, older adults under zero-shot cross-age inference / joint multi-age training / domain-specific adaptation. Headline finding: foundation models trained on adult-skewed corpora fail predictably at the lifespan edges; domain adaptation closes most of the gap.

**Concept pages created (2):**
- `concepts/user-controlled-on-demand-ai-hearing-aids.md` — Treats the user-toggled AI design pattern as a labeled-training-signal generator distinct from always-on AI. Documents the Widex Allure AI RIC as the reference implementation. Counter-positioning table against Phonak Sphere Infinio / ReSound Vivia / Oticon Zeal/Intent / Starkey Omega. Structural argument: every button press is a positive scene label, every non-press in a similar scene is an implicit negative — toggle architectures surface the negative class continuously while always-on AI cannot. Compass Cloud 2.0 framed as the cloud substrate that closes the loop at the platform layer rather than the chip layer. Tradeoffs section covers cognitive load, scene-class coverage skew, comparability to always-on benchmarks, and generalization beyond Widex. Implications-for-data-science section reframes the on-demand button as a zero-cost annotation interface running 24/7 on every device.
- `concepts/cross-lifespan-speech-models.md` — Age-domain-shift in foundation models as a new dimension of training-data moat alongside acoustic-scene diversity and audiogram+telemetry corpora. Documents the USC seed result and walks through why it matters for hearing aids: customer base over-65-weighted; pediatric platforms now shipping at scale (Oticon Play SI April 2026, pediatric softband BCD database May 2026); diarization foundational for downstream HA tasks; all major foundation models (Whisper, Voxtral, Qwen3-ASR, QVAC MedPsy) inherit adult-skewed pre-training. Names the older-adult / hearing-impaired-speech confound. Argues the natural deployment surface for an age-conditioned adapter is the paired smartphone (companion-phone-speech-pipeline tier), not the HA SoC.

**Existing pages updated (4):**
- `entities/ws-audiology-signia.md` — Added Widex Allure AI RIC (May 2026) subsection under the Widex / Technology cluster covering W1 chip + dedicated AI co-processor, user-toggled Clarity Boost, 6 dB SNR vs competitor AI HAs claim, 32 h / 6 h AI-on battery accounting (AI explicitly power-budgeted as minority mode), Compass Cloud 2.0 cloud-based fitting platform with full feature list and operational claims, June 1 / November 1 staged market launch, Ngozi Amobi quote, counter-positioning vs always-on AI race, labeled-telemetry framing connecting to Compass Cloud as cloud substrate, limits/open-questions. Added `widex-allure-ai-may-2026.md` to frontmatter sources. Added `../concepts/user-controlled-on-demand-ai-hearing-aids.md` to related. Added on-demand-ai / clarity-boost / compass-cloud / hybrid-ai tags. Added two-row update to Related Pages and Sources sections. Bumped updated to 2026-05-21.
- `concepts/closed-loop-data-flywheel.md` — Added new "Button-Press Telemetry + Cloud Fitting Substrate — Widex Allure AI + Compass Cloud 2.0 (May 2026)" section between the WSA Sound Preference Program section and the Pre-Training-Aware Flywheel section. Framed as the fifth flywheel architecture alongside M&A (Amplifon-GN) / software-defined data collection (WSA Sound Preference) / Bayesian (AIDA-2) / pre-training-aware (Karpathy-Anthropic). Distinguishes per-wearer intent labels from per-wearer telemetry; documents the toggle architecture's ability to surface the negative class continuously; pipeline diagram. Cross-links user-controlled-on-demand-ai-hearing-aids and ws-audiology-signia. Added source / related / tags. Bumped updated to 2026-05-21.
- `concepts/dnn-in-hearing-aids.md` — Added "On-Demand AI / Dedicated Co-Processor — Widex Allure AI RIC (May 2026)" subsection before the existing Korhonen et al. natural-processing counter-evidence section. Documents the dedicated AI co-processor as a power-budgeted minority-mode pattern (32 h total / up to 6 h AI-on). Counter-positions against Phonak/GN/Demant/Starkey always-on AI flagships. Cross-links user-controlled-on-demand-ai-hearing-aids and closed-loop-data-flywheel concept pages. Stacks with Korhonen + Sound Preference Program into the dual-brand framing. Added source / related / tags. Bumped updated to 2026-05-21.
- `wiki/index.md` — Added two new concept rows (User-Controlled On-Demand AI in Hearing Aids, Cross-Lifespan Speech Models). Bumped ws-audiology-signia entity row, closed-loop-data-flywheel concept row, and dnn-in-hearing-aids concept row dates and tags. Added top-of-file ingest entry above the May 20 LinkedIn drafts entry.

**Underlying ingest angle:** Two structurally novel datapoints in 48 h. (1) WSA's Allure AI RIC is a deliberate counter-positioning move against the always-on AI race led by the other four Big-Six flagships. The user-controlled AI button is a labeled-training-signal generator that always-on systems cannot produce — every press is a wearer-intent annotation paired with the full acoustic feature vector — and pairs with Compass Cloud 2.0 as the cloud substrate that materializes the closed loop at the platform layer. (2) The USC paper opens a third dimension of training-data moat (lifespan-stratified speech corpora and age-conditioned adapters) alongside the acoustic-scene-diversity moat documented in dnn-in-hearing-aids and the audiogram+telemetry+fitting-outcome corpora documented in the pre-training-corpus-as-moat synthesis. The pediatric platforms now shipping at scale (Oticon Play SI) make the lifespan-edge degradation in foundation models a product-level concern rather than a research curiosity.

---

## 2026-05-19 — LinkedIn drafts ingest

**Operation:** Ingested today's LinkedIn drafts research into the wiki.

**Sources added (1):**
- `asr-too-good-to-be-true-arxiv-may-2026.md` — de Oliveira, Peer & Gerkmann, arXiv:2605.12107, 12 May 2026, submitted to Interspeech 2026. Argues that modern ASR systems with embedded LMs are structurally inadequate for SE evaluation: noise robustness and contextual reconstruction that drive correlation with human WER are precisely the properties that hide acoustic SE damage.

**Synthesis pages created (2):**
- `syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md` — Unifies three May 2026 papers (Behringer May 5 listening effort, L3-SE May 9 linguistic hallucination, de Oliveira May 12 ASR-as-evaluator) into a single argument that the current hearing-aid SE evaluation stack systematically flatters models the wearer will still struggle with. Names three unbuilt evaluation primitives (acoustic faithfulness, linguistic faithfulness, effort), explains why the cracks compound, lays out implications for OEM R&D, companion-phone pipelines, regulators, and researchers.
- `syntheses/va-as-hearing-ai-dataset-may-2026.md` — Reframes the Oticon (Zeal/Intent miniBTE R/Verit) + Signia (Active Mini IX/CIC Rechargeable Custom IX/Silk IX/Active Pro IX) + Starkey (Omega AI Government Services) VA-contract cluster of May 12-19 2026 as a structural data-science event. Documents the VA's data-science properties (single EHR, standardized fitting, structured outcome instruments, comorbidity linkage, longitudinal continuity), identifies three barriers to closed-loop telemetry (regulatory, technical, incentive), and argues the next 5 years of VA-channel competition will be decided by who builds an audit-clean telemetry+outcome bridge, not by portfolio breadth.

**Existing pages updated (5):**
- `concepts/listening-effort-evaluation.md` — Added `asr-too-good-to-be-true-arxiv-may-2026.md` to frontmatter sources; noted in the ASR-derived-proxy row that the noise-robustness that helps the effort proxy also hides acoustic damage when ASR is reused as an intelligibility metric; cross-linked the synthesis; bumped updated to 2026-05-19.
- `concepts/linguistic-hallucination-speech-enhancement.md` — Added new "The Evaluator Problem (May 2026)" section arguing the standard ASR-WER fallback is itself broken from the opposite direction; added the new source to frontmatter; cross-linked synthesis and listening-effort-evaluation; bumped updated to 2026-05-19.
- `entities/demant-oticon.md` — Corrected "single largest hearing-aid purchaser globally" claim under May 2026 VA portfolio expansion to "world's second-largest dispenser after the UK NHS, and the largest single US payer"; added three-OEM convergence note cross-linking the VA-dataset synthesis.
- `entities/ws-audiology-signia.md` — Added VA Channel — IX Portfolio Expansion subsection under IX Form Factor section naming Active Mini IX / CIC Rechargeable Custom IX / Silk IX / Active Pro IX VA availability and cross-linking the synthesis.
- `entities/starkey.md` — Added three-OEM convergence note under Government Services Portfolio Expansion subsection cross-linking the synthesis.

**Index updates:**
- New top entry on `wiki/index.md` documenting the day's ingest.
- Added both new synthesis pages to the Syntheses table.

**Underlying LinkedIn posts:**
1. Third crack in the hearing-aid speech-enhancement evaluation stack in twelve days — ASR-based WER joins PESQ/STOI/HASPI as a yardstick that flatters generative SE failures.
2. Three OEMs plugged premium AI hearing aids into the VA contract in one week — and the closed-loop data layer underneath is still unbuilt.

**Verification note:** VA volume claim corrected this ingest. Search returned: "VA is the second largest dispenser of hearing aids in the world after England's National Health System (NHS), and constituted 18% of all U.S. hearing aids dispensed in 2022." Earlier source files (oticon-va-portfolio... and starkey-omega-ai-government...) had "largest single hearing-aid purchaser globally" and "~700,000 hearing aids per year" — left intact (surgical-change principle) but the corrected framing now lives in the new synthesis and the Demant entity update.

---

## 2026-05-17 — Lint Pass

**Operation:** Comprehensive wiki lint pass. Checked index completeness, cross-reference integrity, orphan pages, duplicates, stale sources, page sizes, and missing links.

**Stats at time of lint:**
- Total wiki pages (excluding index/log): 81
- Concepts: 51 | Entities: 22 | Comparisons: 4 | Syntheses: 6
- Total sources: 196

**Index completeness:**
- 2 pages existed on disk but were missing from `wiki/index.md`:
  - `concepts/hearing-care-funnel-attribution.md` (created 2026-05-16, never added to index)
  - `concepts/multimodal-hearing-assessment.md` (created 2026-05-16, never added to index)
- **Fixed:** Both rows added to the Concepts table in `wiki/index.md`.

**Cross-references fixed (22 broken refs → 0):**
All 22 broken references were path-prefix errors — bare filenames used where a directory prefix was required. Fixed across 7 files:
1. `concepts/auditory-attention-decoding.md` — `vcca-computational-audiology.md` → `../entities/vcca-computational-audiology.md`
2. `concepts/automated-audiometry.md` — same `vcca` fix
3. `concepts/cochlear-implant-ai.md` — same `vcca` fix
4. `concepts/longitudinal-hearing-phenotyping.md` — same `vcca` fix
5. `concepts/speech-enhancement-neural-networks.md` — same `vcca` fix
6. `concepts/hearing-aid-prescription-formulas.md` — 7 refs fixed: removed non-existent `ml-personalized-fitting.md`, removed source-file ref `wsa-sound-preference-program-april-2026.md`, added `../entities/` prefix to `gn-hearing-resound`, `phonak`, `demant-oticon`, `starkey`, `vcca-computational-audiology`
7. `entities/cochlear-ltd.md` — added `../concepts/` prefix to `cochlear-implant-ai` and `software-defined-medical-implants`
8. `entities/fortell.md` — added `../concepts/` prefix to 4 concept refs
9. `entities/vcca-computational-audiology.md` — added `../concepts/` prefix to 5 concept refs

**Orphan pages fixed (2 → 0):**
- `concepts/passive-acoustic-metamaterials.md` — added as related in `concepts/hearing-aid-chip-architectures.md`
- `concepts/predictive-pediatric-earmolds.md` — added as related in `concepts/teleaudiology.md`

**Missing cross-references fixed (3):**
- `entities/sonova-ag.md` → added link to `concepts/digital-therapeutics-tinnitus.md` (Sonova owns SilentCloud tinnitus DTx)
- `concepts/small-language-models-edge-ai.md` → added link to `concepts/companion-phone-speech-pipeline.md` (SLMs run on the phone tier)
- `concepts/passive-acoustic-metamaterials.md` already links to `concepts/companion-phone-speech-pipeline.md` via its own related field (no fix needed there, the body mention is peripheral)

**Stale fast-moving sources (14, no wiki fix required — informational):**
Sources pre-dating 2026-02-17 tagged with AI/ML topics. Most are foundational references (Starkey Genesis AI 2023, Lancet hearing-dementia 2024, early auracast 2025). The wiki pages citing them also cite fresher 2026 sources, so no content is stale-only. Notable:
- `starkey-genesis-ai-health.md` (2023-02-01) — still valid as historical context
- `ai-audiology-scoping-review.md` (2024-01-01) — foundational, not fast-moving in content
- `phonak-deepsonic-ai-chip.md` (2025-10-01) — superseded by Sphere Infinio coverage; flag for future update
- `interspeech-2026-audio-reasoning-challenge.md` (2026-02-16) — just at cutoff, still valid

**Page size (no splits needed):**
- Largest content page: `concepts/speech-enhancement-neural-networks.md` at 304 lines — large but coherent; monitor for split after next major ingest
- `wiki/log.md` at 1,658 lines — expected for append-only log; no action required

**Potential duplicates flagged (needs human judgment — no automatic merge):**
- `concepts/dnn-in-hearing-aids.md` vs `concepts/dnn-architectures-hearing-aids.md` — 80% title overlap; dnn-in-hearing-aids is the clinical/product page, dnn-architectures is the architecture-taxonomy page; distinct enough to keep separate but should stay cross-linked
- `concepts/hearing-aid-market-dynamics.md` vs `syntheses/hearing-aid-market-outlook.md` — 75% title overlap; dynamics is the live-updated concept, outlook is the periodic synthesis; keep separate
- `concepts/state-space-models.md` vs `concepts/mamba-architecture.md` — SSMs is the general taxonomy, Mamba is the specific architecture; keep separate
- `comparisons/ai-hearing-aid-platforms-2026.md` vs `syntheses/hearing-aid-ai-stack-2026.md` — comparison is OEM-by-OEM table, synthesis is architectural stack analysis; keep separate
- `concepts/on-device-ml-hearing-aids.md` vs `concepts/tinyml-edge-ai.md` — on-device-ml is the broad hearing-device ML page, tinyml is sub-MCU keyword-spotting; keep separate

**What needs human judgment:**
1. `concepts/hearing-aid-prescription-formulas.md` — removed link to non-existent `ml-personalized-fitting.md`. If a dedicated personalized-fitting ML concept page is warranted, it should be created and cross-linked back.
2. Stale source `phonak-deepsonic-ai-chip.md` (2025-10-01) — the Phonak entity page should be updated with Sphere Infinio as the current chip story; the DeepSonic source is superseded but kept for history.
3. `concepts/speech-enhancement-neural-networks.md` at 304 lines — candidate for split into (a) architecture taxonomy and (b) recent advances, if it crosses ~400 lines after next major ingest.

---

## 2026-05-17 — INGEST (LinkedIn drafts)

**Operation:** Ingested two news items underlying today's LinkedIn drafts: (1) the **AAA 2026 leadership panel** (Hearing Review coverage, May 6 2026) reframed through the specific cited back-office AI wins — already in wiki as a source, updated with concrete quotes today; and (2) **DiffVQE** — first reproducible diffusion-based acoustic echo control (Lugo Girao et al., arXiv:2605.08189, 12 May 2026), framed as a companion-phone-tier story rather than an on-chip story.

**New source files (1):**
- `diffvqe-diffusion-aec-arxiv-may-2026.md` — DiffVQE; arXiv 2605.08189; hybrid score-based diffusion topology adapted for joint AEC + denoising; trained on Interspeech 2025 URGENT Challenge data; outperforms Microsoft's DeepVQE on both echo control AND noise control simultaneously while being smaller, less complex, faster, and single-step. Third 2026 datapoint extending the single-step / efficient generative-SE wave (after predictive-generative drift decomposition and DriftSE). Hearing-aid relevance: companion-phone-tier VoIP pipeline (Teams / Zoom / iOS-VoIP / Android-telephony → LE Audio handoff), not on-chip. Implies the HA's role shifts from "clean the signal" to "decide how much to trust what arrived." Trust-calibration metric is undefined.

**Updated source files (1):**
- `aaa-2026-leadership-panel-may.md` — added **Concrete AI Wins Cited (Back-Office, Not Product-Page)** section with named-quote citations: Mike O'Neil (WSA) cut new-rep training by 2 months with internal chatbots; Mikkel Knudsen (ReSound) AI assistants in fitting software deflect customer-service calls; Kyle Acker (Starkey) frames clinicians as "reactive to predictive"; Nicholai Dessypris (Sonova) patient-journey framing; Patti Trautwein (Cochlear) "stage 1 vs mild" terminology proposal. Added strategic-read bullet: cited wins are unglamorous internal productivity multipliers, not signal-path features — different "AI in hearing aids" story than the on-chip-DNN product launches.

**New concept pages (1):**
- `wiki/concepts/companion-phone-speech-pipeline.md` — formalizes the paired-smartphone audio pipeline as a distinct compute tier between HA SoC and cloud. ~4 orders-of-magnitude compute advantage over HA SoC. Workload-map table across HA-SoC / phone / cloud with latency budgets. Argues the HA's role shifts from "clean the signal" to "decide how much to trust what arrived" when upstream audio is generatively reconstructed. Names the missing **trust-calibration metric** and **mode-arbitration** problem. OEM-vs-platform divide: Apple controls the AirPods Pro 2/3 phone-pipeline end-to-end; medical-device OEMs do not. Cross-links DiffVQE / QVAC MedPsy / Samsung Audio Eraser / Adobe-Speechmatics as datapoints already in wiki demonstrating phone-tier maturity.

**Updated existing pages (2):**
- `wiki/concepts/speech-enhancement-neural-networks.md` — added **DiffVQE — Single-Step Diffusion AEC + Denoising (Lugo Girao et al., May 12 2026)** subsection under Recent Academic Advances, positioning as third datapoint in the single-step generative-SE wave; cross-linked companion-phone-speech-pipeline as the deployment substrate; added trust-calibration-metric-missing call-out. Frontmatter: added diffvqe source, companion-phone-speech-pipeline relation, and `diffusion-aec` / `companion-phone` tags; bumped updated date to 2026-05-17.
- `wiki/concepts/audiologist-workforce-shortage.md` — added **Back-Office AI as the Highest-Leverage Bet (AAA 2026 Panel, May 2026)** section under Implications for Technology, listing the four named-quote back-office AI wins and arguing the AI-vs-audiologist framing is conceded by industry leadership; operative question becomes which back-office workflows scale fastest. Bumped updated date.

**Index update:** Prepended a "Last updated: 2026-05-17" stanza; added Companion-Phone Speech Pipeline row to the Concepts table; bumped Speech Enhancement Neural Networks tag list and updated date.

**Underlying LinkedIn posts:**
1. *AAA 2026 industry panel — AI as the only realistic answer to the audiology workforce shortage.* Reframes the AI-in-hearing narrative from on-chip DNN to back-office productivity multipliers; names three specific industry cited-wins (WSA / ReSound / Starkey) as the actual signal of where 2026-2027 R&D leverage is.
2. *DiffVQE — diffusion-based AEC beats SOTA at smaller size.* Names the companion-phone-pipeline tier as the deployment substrate; identifies the missing trust-calibration layer as the next interesting hearing-aid R&D problem.

**Watchlist for follow-up:**
- Whether any HA OEM publishes a "trust-calibration" or "faithfulness-to-truth" outcome metric for upstream-cleaned audio handed off via LE Audio.
- Whether any OEM acknowledges back-office-AI (training / customer-service / fitting-software) as a strategic R&D track in 2026/27 product communications.
- Whether DiffVQE-class single-step generative SE shows up in any consumer-VoIP product (Teams successor, iOS-VoIP, Android Phone, Zoom) within 12 months.

---

## 2026-05-16 — INGEST (Daily hearing+AI digest)

**Operation:** Compiled and sent today's daily hearing+AI digest to door.punch_4o@icloud.com (654 words, 9 items). Posted Discord confirmation to channel 1490303675648970823 (HTTP 200). Ingested 2 genuinely new sources; 7 of 9 items were already in the wiki.

**New source files (2):**
- `eargo-8-launch-may-2026.md` — Eargo 8 OTC launch mid-May 2026; first product post-Eargo×LXE-Hearing merger; $2,699 MSRP CIC, FDA-cleared. Smart Sound Adjust = environmental classification with auto-program-switching (prescription-tier feature in an OTC). Device Scan = patented in-canal acoustic-signature self-check for wax/occlusion using existing speaker–microphone path — first OTC to market telemetry-through-transducers as a wellness feature. 16 h battery / ~14 case recharges.
- `driftse-equilibrium-se-arxiv-2026.md` — DriftSE; arXiv 2604.24199; submitted to Interspeech 2026. Equilibrium-style generative SE that evolves the pushforward distribution of a mapping function to converge directly onto the clean-speech distribution; **single-step inference** matches multi-step diffusion baselines on VoiceBank+DEMAND. Latency unlock for generative SE in HA budgets — categorically different route from predictive-generative drift decomposition. Streaming stability and hallucination-surface vs L3-SE both open.

Plus digest record: `hearing-ai-digest-2026-05-16.md`.

**Updated existing pages (2):**
- `wiki/concepts/otc-hearing-aids.md` — Added "Premium-OTC Self-Fitting + Auto-Scene: Eargo 8 (May 2026)" subsection under Premium OTC Pricing Failure section, framing the upper-OTC viability test ($2,699) as complementary to the Lexie B3 mid-tier test ($999). Smart Sound Adjust collapsed one of the prescription tier's marketing differentiators; Device Scan introduced canal-as-passive-sensor pattern. Source added to frontmatter; updated date bumped.
- `wiki/concepts/speech-enhancement-neural-networks.md` — Added "DriftSE — Single-Step Equilibrium Generative SE" subsection under Recent Academic Advances; contrasted with predictive-generative drift decomposition (Richter et al.) as a parallel route to single-step inference. Flagged the hallucination-surface question relative to L3-SE / linguistic-hallucination-speech-enhancement concept as unverified. Source added to frontmatter; tags expanded with single-step-generative-se, equilibrium-model; updated date bumped to 2026-05-16.

**Items in digest already in wiki (no duplicate ingest):**
- Brain-controlled hearing aid (Mesgarani/Choudhari, Nature Neuroscience 11 May 2026) — `brain-controlled-hearing-nature-neuroscience-may-2026.md` (ingested 12 May; NPR 14 May follow-on coverage adds press-cycle context but no new technical claim).
- Framingham hearing-aid → 20-yr dementia risk (61% reduction in under-70s) — `framingham-hearing-aid-dementia-jaman-2025.md` (the Aug 2025 JAMA Neurology Letters + May 2026 PR resurfacing both captured).
- Northwestern AI for cochlear-implant language prediction (92.4% accuracy from preimplant MRI) — `pediatric-ci-language-prediction-transfer-learning-2025.md` plus `ai-cochlear-implant-language-prediction-2025.md` and `ai-predicts-ci-language-outcomes.md`.
- Phonak Virto R Infinio / Infinio Ultra Sphere 2026 AI Excellence Award — `phonak-ai-excellence-award-march-2026.md` (announced March 24 2026; same award).
- Starkey Brandon Sawalich / Omega AI BIG Innovation — `starkey-omega-ai-big-ai-awards-2026.md`.
- Interspeech 2026 Audio Reasoning Challenge — `interspeech-2026-audio-reasoning-challenge.md`.
- Ultra-low-power MCU / TinyML 2026 roadmap — `tiny-ml-to-tiny-dl-survey-acm-2026.md` and adjacent TinyML sources.

**Strategic threads reinforced:**
- **Generative-SE latency wall is breaking.** Third paper in 8 days from the "single-step / efficient generative SE" line (DriftSE today; L3-SE 14 May with its categorically-new linguistic-hallucination failure mode; predictive-generative drift decomposition 8 May). 2026 is the year generative SE either ships in HAs or hits a faithfulness ceiling that blocks it. Both branches of that fork are now wiki-tracked.
- **OTC scene-classification convergence at premium tier.** Eargo 8 ports prescription-tier auto-scene-classification into a $2,699 self-fitting OTC. The "premium prescription justifies its price via AI features" narrative has now lost one of its strongest individual claims.
- **Telemetry-through-existing-transducers as a category.** Eargo Device Scan + pediatric softband BCD telemetry + in-ear PPG = third 2026 datapoint suggesting the device's own transducers double as cheap clinical sensors. Worth a dedicated synthesis page in Q3 2026 if the pattern recurs.
- **Press-cycle persistence of AAD/brain-controlled hearing.** Third digest in a row featuring the Columbia paper (with the May 14 NPR explainer extending coverage). The narrative has not exhausted itself; expect OEM "attention-aware" feature-marketing pressure into H2 2026.

---

## 2026-05-16 — INGEST (LinkedIn drafts)

**Operation:** Ingested two news items underlying today's LinkedIn drafts: (1) **Listen Up Kentucky** state-level public-awareness campaign (ADA + WSA + KAA, surfaced 11 May 2026 for Better Hearing Month) framed as the missing top-of-funnel data layer for hearing-care AI; and (2) **Gijbels, Anderson, Miller, Johnson, Lunner** (Frontiers in Audiology and Otology, March 30 2026; DOI 10.3389/fauot.2026.1772008) ecological-validity protocol with the headline that audiovisual intelligibility and listening comprehension outperform audio-only assessments, plus a negative result that vocal-intensity changes do NOT reliably track hearing-loss severity.

**New source files (2):**
- `listen-up-kentucky-may-2026.md` — Kentucky-wide PSAs (TV + radio) + audiologist outreach toolkits across Kentucky DMAs; WSA is the **sole OEM partner**, ADA + KAA co-lead; explicitly designed as a scalable template for additional state rollouts.
- `gijbels-ecological-validity-fauot-mar-2026.md` — n=26 (11 dyads + 4 individuals with research-assistant partners); 2-3 hour test battery spanning audio-only / audiovisual / dyadic conversation; headline: audiovisual intelligibility + listening comprehension beat audio-only at predicting real-world function; negative: vocal-intensity-as-hearing-loss-biomarker fails.

**New concept pages (2):**
- `wiki/concepts/hearing-care-funnel-attribution.md` — Data-science framing of the awareness → search → screening → fitting funnel. 80% of people with hearing loss never seek care; the demand-side measurement layer is structurally under-instrumented. Listen Up Kentucky positioned as a natural A/B framework (DMA-level exposure). Model classes that apply: geo-uplift / synthetic-control / Bayesian MMM / causal forests / propensity-weighted conversion modeling. Argument: the OEM with the best top-of-funnel attribution model wins the next decade because every other AI claim (DNN SNR, dyad enhancement, etc.) is downstream of fitting volume.
- `wiki/concepts/multimodal-hearing-assessment.md` — Synthesizes Gijbels et al. with Apple Hearing Study (16% audio-vs-subjective gap) and the AVSE work. Argues the audio-only loss function (PESQ/STOI/HASPI) is misspecified for hearing-aided populations because the device is multimodal in deployment but evaluated as audio-only. Concrete proposal: HASPI-AV outcome variant; paired smartphone camera as the cheapest visual sensor for ecologically-valid evaluation. Adjacent-negative section: vocal-intensity tracking does NOT scale (Gijbels), narrowing the dyadic feature set.

**Updated existing pages (5):**
- `wiki/concepts/subjective-objective-hearing-gap.md` — Added "Clinical-Cohort Confirmation (Gijbels et al., March 2026)" section linking the Apple-population-scale finding to the clinical-cohort finding. Bumped frontmatter sources/related/tags; added multimodal-hearing-assessment cross-link; fixed entity paths.
- `wiki/concepts/audiologist-workforce-shortage.md` — Added "Pairing With the Demand-Side Constraint" section. Frames Listen Up Kentucky as the demand-side companion to the supply-side workforce gap; joint supply-demand model would predict where the next bottleneck migrates if either lever moves first. Added source row + hearing-care-funnel-attribution related.
- `wiki/entities/ws-audiology-signia.md` — Added "Listen Up Kentucky — State-Level Awareness Pilot (May 2026)" subsection between Lexie B3 and Sam's Club. WSA as sole OEM = first manufacturer with a state-scale demand-side dataset; competitive variable if WSA installs the measurement plumbing.
- `wiki/concepts/speech-enhancement-neural-networks.md` — Added "The Audio-Only Loss-Function Gap (Gijbels et al., March 2026)" subsection under Evaluation Metrics; argues that PESQ/STOI/HASPI systematically undersell multimodal devices because the metric ignores the visual channel that subjects actually use in deployment. Frontmatter tags now include multimodal/audiovisual.
- `wiki/concepts/care-partner-dyad-models.md` — Added "Negative Result: Vocal-Intensity Tracking (Gijbels et al., March 2026)" section. Constrains the dyad-aware feature set: Lombard-effect-as-biomarker is out; partner-side visual channel (face visibility, gaze direction) and turn-taking/repair-frequency signals remain candidates.

**Index update:** Prepended a "Last updated: 2026-05-16" stanza covering the 2 new sources, 2 new concept pages, and 5 updated pages; demoted prior 2026-05-15 entry to "Earlier."

**Underlying LinkedIn posts:**
1. *Listen Up Kentucky — public-health awareness as the missing top-of-funnel data layer for hearing-care AI.* Reframes a Better Hearing Month state PSA as a state-level A/B framework, names the missing pipeline (PSA exposure → search lift → screening → fitting), and argues the attribution model is a competitive variable hard to replicate without a state-scale dataset.
2. *Audiovisual intelligibility outperforms audio-only assessments.* Summarizes Gijbels et al. n=26; argues audio-only loss functions are misspecified for multimodal deployment; proposes paired-phone camera as the cheapest visual sensor for ecologically-valid evaluation.

**Watchlist for follow-up:**
- Whether other states adopt the Listen Up template; whether ADA + WSA publish PSA-exposure → fitting-conversion attribution data.
- Whether any OEM publishes HASPI-AV or other multimodal outcome metrics in 2026 product literature.
- Whether independent labs replicate the Gijbels vocal-intensity negative result before any product team commits to Lombard-effect-as-biomarker.

---

## 2026-05-15 — INGEST (Daily hearing+AI digest)

**Operation:** Ingested today's hearing+AI digest. Quiet news cycle after Monday's brain-controlled-hearing splash; three genuinely new sources mapped, plus a new concept page for the predictive pediatric earmold pattern.

**New source files (3):**
- `allears-ai-pediatric-earmolds-april-2026.md` — Western University × Boys Town National Research Hospital project; PIs Scollie / Nikan / Pearce / McCreery; Oberkotter Foundation $4.4M / 4 yrs; ML-predicted ear-canal growth + mirroring + 3D-printed earmolds in advance of fit drift; software to be open-sourced.
- `aondevices-edge-ai-ces-2026.md` — AONDevices × P-Logic CES 2026 microwatt-class always-on multi-modal inference silicon for hearables; adds another commercial-stage entrant to the dedicated-AI-silicon column alongside Phonak Sphere Infinio and Fortell Spatial AI.
- `tiny-ml-to-tiny-dl-survey-acm-2026.md` — ACM Computing Surveys 2026 taxonomy of TinyML → Tiny Deep Learning; on-device-training treatment names the missing rung between factory-trained DNN deployment and in-situ adaptation in HAs.

**New concept pages (1):**
- `wiki/concepts/predictive-pediatric-earmolds.md` — ML shape-prediction + 3D-printing pipeline as a planned manufacturing flow rather than a reactive impression-and-refit cycle; critical-window optimization framing for prelingual hearing-aided children; open-source pediatric stack as a structural counter to OEM-bundled fit software; mirroring symmetry assumption may break for syndromic populations where intervention is most acute.

**Updated existing pages (2):**
- `wiki/concepts/tinyml-edge-ai.md` — Added Tiny ML → Tiny DL survey subsection (anchor reference for future scope), AONDevices × P-Logic CES 2026 subsection (microwatt always-on); bumped frontmatter sources/related/dates.
- `wiki/concepts/on-device-ml-hearing-aids.md` — Added two new sources to frontmatter; bumped updated date.

**Index update:** added new concept row, bumped on-device-ml-hearing-aids row, added today's daily-digest entry.

**Already-in-wiki digest items:** Fortell Spatial AI study (sources/fortell-spatial-ai-ija-may-2026.md from 13 May), Apple Hearing Study findings (sources/apple-hearing-study-results-may-2026.md), Apple AirPods country expansion (sources/airpods-hearing-aid-country-expansion-may-2026.md from 13 May), Phonak Virto R Infinio Red Dot (sources/phonak-virto-r-infinio-red-dot-april-2026.md), Starkey Omega AI BIG Innovation (sources/starkey-omega-ai-big-ai-awards-2026.md), NPR brain-controlled hearing coverage (already mapped to sources/brain-controlled-hearing-nature-neuroscience-may-2026.md from 12 May).

---

## 2026-05-15 — INGEST (LinkedIn drafts)

**Operation:** Ingested two news items underlying today's LinkedIn drafts: (1) Tether QVAC MedPsy on-device medical LLM release (May 7 2026), framed as the substrate for hearing-care **companion-phone** apps (distinct from the on-chip lane); and (2) JASA paper on meta-earplugs with Helmholtz resonators (Apr 28 2026), framed as a passive-metamaterial counter-narrative to AI maximalism in hearing protection.

**New source files (2):**
- `qvac-medpsy-edge-medical-llm-may-2026.md` — Tether AI Group QVAC MedPsy 1.7B + 4B (Hugging Face, May 7 2026); Apache 2.0; 4B beats Google MedGemma-27B at 7× smaller on 7-task closed-ended medical benchmark; Q4_K_M ≈ 1.28 / 2.72 GB; smartphone-class deployment; SFT+RL on AlphaMedQA pipeline; Baichuan-M3-235B teacher.
- `meta-earplugs-helmholtz-resonators-jasa-april-2026.md` — JASA 159(4) 3702 (Apr 28 2026); surfaced in Hearing Review week of May 12; 3D-printed passive earplug with Helmholtz resonators in series tuned to sub-1 kHz; +15 dB low-frequency attenuation via phase-cancellation reflection; near-zero occlusion effect.

**New concept pages (2):**
- `wiki/concepts/medical-domain-edge-llms.md` — Companion-phone-substrate framing distinct from on-chip lane. Workflows table: tinnitus iCBT counseling, plain-language audiogram explanation, post-fit Q&A, conversational triage, first-fit onboarding, care-partner counseling. Bottleneck shifts from compute to **hearing-care domain alignment** because audiology training corpora are an order of magnitude sparser than general medicine. Risks section: hallucination in counseling, SaMD liability framing, monthly base-model update cadence, multilingual coverage gap, voice-modality gap (MedPsy is text-only).
- `wiki/concepts/passive-acoustic-metamaterials.md` — Phase-cancellation reflection as the mechanism (vs absorption). Computational acoustics + generative geometry as a tunable parameter space analogous to neural-network design. Floor-raising thesis: every dB attenuated mechanically is a dB the active DSP/DNN/ANC layer doesn't fight, paying a power/latency/algorithmic-complexity dividend up front. Co-design table across passive shell + active DSP/DNN + companion phone LLM. Limits subsection: dynamic conversation, per-user personalization, sub-2 kHz design bias.

**Updated existing pages (2):**
- `wiki/concepts/small-language-models-edge-ai.md` — Added QVAC MedPsy entry to Notable Small Models 2026 table; bumped frontmatter sources/related/tags; added MedPsy source row.
- `wiki/concepts/digital-therapeutics-tinnitus.md` — Added MedPsy as adherence-lever open question (does on-device conversational counseling out-complete form-based delivery?); bumped frontmatter sources/related; added source row.

**Index update:** added the two new concept pages, bumped SLM and tinnitus-DTx tag/date entries.

**Underlying LinkedIn posts:**
1. *QVAC MedPsy on-device medical LLM — the hearing-care companion app just got an upgrade* (medical-domain edge LLMs collapse the cloud-LLM regulatory friction and rule-based-script personalization deficit; companion app substrate transformed; bottleneck shifts to domain alignment).
2. *Meta-earplugs Helmholtz resonators — passive metamaterials as a counter-narrative to AI maximalism in hearing protection* (3D-printed phase-cancellation geometry as a design loop structurally identical to NN tuning; floor-raising layer beneath the active stack; future products co-design passive shell with active DSP rather than picking).

---

## 2026-05-13 — INGEST (Daily Hearing+AI Digest)

**Operation:** Ingested today's hearing+AI daily digest (10 items: 2 papers, 4 industry news, 2 AI/ML, 2 worth-watching). Most digest items were already in the wiki (Fortell Spatial AI paper, Apple Hearing Study May 1, Starkey Omega Government Services, ICASSP URGENT, Otarmeni gene therapy). Four genuinely new sources warranted ingestion.

**New source files (4):**
- `airpods-hearing-aid-country-expansion-may-2026.md` — Apple's 12 May 2026 expansion of the AirPods Pro 2/3 Hearing Aid feature to Italy, Romania, and Czechia, bundled with Apple Watch hypertension alerts; now in 100+ countries. iOS 26+ required.
- `apple-otc-haf-usability-aja-2025.md` — First independent academic evaluation of Apple's OTC Hearing Aid Feature in the American Journal of Audiology (DOI 10.1044/2025_AJA-25-00192). MAUQ usability 6.7/7 in adults with self-perceived mild-to-moderate loss; high satisfaction and sound-quality scores; lab measurements meet OTC prescription-target expectations.
- `sonova-sennheiser-consumer-divestiture-may-2026.md` — Sonova publicly announced it is seeking a buyer for the Sennheiser-branded Consumer Hearing business. Refocus on core hearing care. Implicit concession that the consumer-hearable category has been won by Apple/Bose/Sony rather than medical-device incumbents.
- `dfingernet-noise-adaptive-se-arxiv-2025.md` — DFingerNet (arXiv:2501.10525) — Deep Filter Network backbone extended with a noise-fingerprint adaptation module. Conditional SE inference replaces the discrete scene-classifier-plus-program-switch pattern. On-device-friendly architecture.

**Updated pages (4):**
- `wiki/entities/apple-hearing-features.md` — Added country-rollout sentence in Software Requirements; refreshed frontmatter (`updated: 2026-05-13`); added two new source rows.
- `wiki/entities/sonova-ag.md` — Added new Sennheiser Consumer Hearing Divestiture subsection under Recent Developments (May 2026); refreshed frontmatter; added new source row.
- `wiki/concepts/otc-hearing-aids.md` — Added independent clinical validation (AJA) and geographic rollout (May 12) bullets in the Apple Disruption section; refreshed frontmatter sources.
- `wiki/concepts/dnn-in-hearing-aids.md` — Added new Conditional / Noise-Fingerprint Adaptation subsection under Key Architectures, citing DFingerNet as the canonical example; refreshed frontmatter.

**No new wiki pages required** — all items folded into existing infrastructure.

**Coverage gaps noted (deferred):**
- AONDevices AONx360 edge-AI silicon (CES 2026) — mentioned in digest Worth-Watching but already covered well by existing `aizip-tiny-ai-hearing-devices-2026.md` and the edge-AI/TinyML concept set. Not a priority for a standalone source file today.
- Verifying whether the Fortell Spatial AI paper venue is IJA or *Hearing, Balance and Communication* — existing source file says IJA; some Taylor & Francis search hits referenced HBC. DOI prefix `10.1080/14992027` resolves to IJA. Leaving the existing source unchanged.

**Email digest record:** `hearing-ai-digest-2026-05-13` — 10 items: Spatial AI Fortell paper (lead), Apple OTC-HAF AJA validation, AirPods country expansion, Apple Hearing Study findings, Starkey Omega VA channel, Sonova/Sennheiser divestiture, ICASSP 2026 URGENT, DFingerNet, Otarmeni gene therapy, AONDevices AONx360.

---

## 2026-05-11 — INGEST (Daily Hearing+AI Digest)

**Operation:** Ingested today's hearing+AI daily digest (8 items: 3 papers, 3 industry news, 1 AI/ML, 1 worth-watching).

**New source files (3):**
- `speaker-distance-estimation-reverberation-arxiv-2026.md` — Neri et al., arXiv:2605.07694, 11 May 2026. Single-channel speaker distance estimation; empirical decomposition of early vs. late reverberation degradation. Reinforces late-tail-as-next-frontier-nuisance with Huang/NDF+ thread.
- `starkey-omega-ai-government-services-may-2026.md` — Starkey announces Omega AI feature parity (Auracast Assistant, Push-to-Talk, Google Fast Pair) for VA/DoD/IHS as of May 1, 2026, plus the new StarLink Edge LE Adapter. Channel-economics expansion + one new accessory.
- `live-captioning-smart-glasses-may-2026.md` — Glass Almanac roundup of Wired's May 2026 live-captioning glasses comparative review. Category-convergence pressure on hearing aids.

**Backfill (1 source):**
- `predictive-generative-drift-decomposition-arxiv-2026.md` — added arXiv:2605.06189 ID and 8 May 2026 submission date (was placeholder).

**Digest record:** `hearing-ai-digest-2026-05-11.md`

**Wiki page updates (2):**
- `concepts/speech-enhancement-neural-networks.md` — Added Speaker Distance Estimation source to frontmatter; added "Single-Channel Speaker Distance Estimation under Reverberation (Neri et al., May 2026)" subsection under Recent Academic Advances; updated Predictive-Generative Drift Decomposition subsection with arXiv ID. Updated `updated:` to 2026-05-11.
- `entities/starkey.md` — Added Government Services source to frontmatter; added "Government Services Portfolio Expansion (May 1, 2026)" section between Auracast/Connectivity Update and AAA 2026 Showcase. Updated `updated:` to 2026-05-11.

**Index updates:**
- Top-of-file "Last updated" entry rewritten for 2026-05-11 ingest; prior 2026-05-10 entry demoted.
- Speech Enhancement Neural Networks row: tags + date refreshed.
- Starkey row: tags + date refreshed.

**No new wiki pages required** — Monday light cycle, all items mapped to existing infrastructure.

**Strategic threads reinforced:**
- Late-reverberation as next-frontier nuisance variable (Neri + Huang).
- Channel-economics dominance — third consecutive day (Starkey Government Services + WSA Sam's Club + Lexie B3 prior).
- Category convergence: live-captioning glasses now substituting for HA on the "speech-in-noise understanding" job for some profiles.

**Already-covered items not re-ingested:** Spatial-Magnifier (May 8), Predictive-Generative Drift (May 8 — backfill only), Apple Hearing Study (May 1 source), FHH 2026 conference (existing source), Sonova FY readout (calendar flag only — results not yet released).

---

## 2026-05-10 — LINT

**Operation:** Comprehensive LINT pass — all 70 wiki pages read (39 concepts, 21 entities, 4 comparisons, 6 syntheses); source file directory listing reviewed (individual source files not read due to volume ~180 files).

**Checks performed:** A (index completeness), B (broken index entries), C (orphan detection), D (broken cross-references), E (duplicate concepts), F (stale sources), G (missing cross-references), H (page size).

**Summary:**
- Checks A, B, H: PASS — no issues
- Check C: PASS with weak-link notes (who-hearing-program, hearing-ai-research-landscape-2025, large-sensor-models)
- Check D: 5 issues found — typo in sources frontmatter, wrong entity path prefix, 2 wrong relative paths in concept body wikilinks, wrong relative path in comparisons body link, stale Apple product reference in comparison
- Check E: 3 candidate pairs — dnn-architectures vs dnn-in-hearing-aids (overlap), small-language-models vs tinyml-edge-ai (scope overlap), model-compression triplication — all flagged for human judgment
- Check F: 7 stale source concerns — hearing-ai-research-landscape-2025 title outdated, speech-enhancement 2024 foundation model sources, automated-audiometry 2024 ML sources, OTC comparison referencing superseded AirPods Pro 2
- Check G: 8 pages with missing cross-references — who-hearing-program, automated-audiometry, world-models, audio-reasoning, model-context-protocol, large-sensor-models, gene-therapy-hearing, hearing-loss-dementia-link
- Additional: duplicate Sources section in speech-enhancement-neural-networks, empty sources[] in who-hearing-program, potential duplicate source file pairs (6), duplicate `updated:` key in automated-audiometry frontmatter

**Auto-fixes applied (15 issues across 13 files):**
1. `concepts/hearing-aid-market-dynamics.md` — Fixed typo: `sciencedient` → `sciencedirect` in sources frontmatter
2. `concepts/subjective-objective-hearing-gap.md` — Fixed missing `../entities/` prefix on apple-hearing-features in related field
3. `concepts/speech-enhancement-neural-networks.md` — Removed first duplicate Sources section (lines 210-219 were incomplete copy of full Sources at end)
4. `concepts/care-partner-dyad-models.md` — Fixed wrong wikilink path `[[../sources/...]]` → `[[../../sources/...]]`
5. `concepts/cochlear-implant-ai.md` — Fixed wrong wikilink path `[[../sources/...]]` → `[[../../sources/...]]`
6. `comparisons/dnn-vs-natural-processing.md` — Fixed Sources body link `../sources/` → `../../sources/` (wrong relative depth from comparisons/)
7. `comparisons/otc-vs-prescription-hearing-aids.md` — Updated stale AirPods Pro 2 @ $249 reference to AirPods Pro 3 @ $200 (April 2026)
8. `entities/who-hearing-program.md` — Added 5 missing related links (otc-hearing-aids, audiologist-workforce-shortage, teleaudiology, hearing-loss-dementia-link, gene-therapy-hearing) to frontmatter and Related Pages body
9. `concepts/automated-audiometry.md` — Expanded Related Pages body section to match frontmatter (added 5 links); removed duplicate `updated:` key; corrected updated date to 2026-05-10
10. `concepts/world-models-hearing-ai.md` — Added closed-loop-data-flywheel and cortical-reorganization-hearing-aids to related field and Related Pages
11. `concepts/audio-reasoning-chain-of-thought.md` — Added agentic-engineering-hearing-rd to related field and Related Pages
12. `concepts/model-context-protocol.md` — Added agentic-engineering-hearing-rd to related field and Related Pages
13. `concepts/large-sensor-models.md` — Added closed-loop-data-flywheel and digital-phenotyping-cognitive-decline to related field and Related Pages
14. `concepts/gene-therapy-hearing.md` — Added software-defined-medical-implants to related field and Related Pages
15. `concepts/hearing-loss-dementia-link.md` — Added care-partner-dyad-models and expanded Related Pages body (added 4 links)

**Issues requiring human judgment (8):**
- H1: `hearing-ai-research-landscape-2025.md` title says "2025" — wiki is now May 2026; recommend rename to 2026 or update title; all backlinks would need updating
- H2: `dnn-architectures-hearing-aids.md` vs `dnn-in-hearing-aids.md` — overlapping scope; recommend clarifying lead paragraphs or merging
- H3: `model-compression.md` content triplicated across `small-language-models-edge-ai.md` and `tinyml-edge-ai.md` — trim compression sections in both; defer to model-compression.md
- H4: `entities/who-hearing-program.md` — `sources: []` empty; only page with no source citations; needs source files identified and cited
- H5: `concepts/speech-enhancement-neural-networks.md` — 2024 foundation model sources for a rapidly-moving topic; annotate as older evidence; new 2026 sources (ndf-plus, aida-2) already added
- H6: `concepts/automated-audiometry.md` — 2024 ML classification sources; page lacks 2026 OTC audiometry developments (Apple hearing test, HIMSA Noah ES)
- H7: 6 potential duplicate source file pairs in `sources/` — read both in each pair to determine if true duplicates: (ai-audiology-scoping-review-2024 vs ai-audiology-scoping-review), (low-latency-dnn-noise-reduction-frontiers-2025 vs low-latency-dnn-noise-reduction), (signia-ix-platform-2024 vs signia-ix-platform), (resound-vivia-dnn vs resound-vivia-launch-2025), (cochlear-implant-ai-innovations vs ai-cochlear-implant-innovations-review-2025), (oticon-intent-4d-sensors vs oticon-intent-launch-2024)
- H8: `comparisons/otc-vs-prescription-hearing-aids.md` and `comparisons/on-device-vs-cloud-ml.md` — Sources body sections use informal citations not linked to actual source files

**Pages touched:** 13 (auto-fixes applied)

---

## 2026-05-10 — INGEST (LinkedIn drafts)

**Operation:** INGEST (LinkedIn post research, hearing + AI)

**Sources added (2):**
- `aida-2-bayesian-generative-se-arxiv-2026.md` — Hidalgo-Araya, Trésor, van Erp, Nuijten, van de Laar, de Vries (TU Eindhoven + Lazy Dynamics + **GN Advanced Science**), arXiv 2603.28436, 30 Mar 2026. AIDA-2: probabilistic generative model for spectral SE; ~85 effective parameters competitive with Wiener (PESQ 2.17 vs 2.22) on VoiceBank+DEMAND; signal processing + learning + personalization unified as inference in a factor graph (RxInfer.jl); industrial provenance via GN Advanced Science.
- `asha-nslhm-2026-care-partners.md` — ASHA National Speech-Language-Hearing Month 2026 resource set, May 2026. Care-partner content prominent (spouses of adults with hearing loss; adult children of parents with dementia; families navigating swallowing/communication disorders); not the official theme but a clear emphasis.

**New wiki pages (2):**
- `concepts/probabilistic-generative-models-hearing-ai.md` — Counter-paradigm to "bigger DNNs on chip"; Bayesian factor-graph inference framing for hearing-aid signal processing; AIDA-2 as primary exemplar; positions a third path beyond DNN-vs-classical DSP.
- `concepts/care-partner-dyad-models.md` — Design / data gap concept page. Hearing-aid AI is n=1 (the wearer) but adherence and outcome literature points to the dyad as the unit of adoption. Concrete schema additions: conversation partner enrollment, dyad-level telemetry (repair / repetition events), bilateral fitting feedback, joint outcome metrics.

**Pages updated (3):**
- `concepts/speech-enhancement-neural-networks.md` — Added AIDA-2 to `sources:` and `related:` frontmatter; new subsection "AIDA-2 — Probabilistic Generative Counter-Paradigm" under Recent Academic Advances; appended source link; updated date.
- `entities/gn-hearing-resound.md` — Added "GN Advanced Science — Research Arm" subsection with AIDA-2 details; updated `sources:`, `related:`, `tags:`, and date. Frames AIDA-2 as a parallel non-DNN R&D track alongside ReSound Vivia DNN.
- `concepts/closed-loop-data-flywheel.md` — Added "Probabilistic / Bayesian Flywheel — AIDA-2" subsection (third architecture beyond M&A and software-defined data collection) and "Multi-User / Dyad Extension (Care Partners)" subsection; expanded `sources:`, `related:`, `tags:`, date.

**Pages reused / cross-linked into (no duplicate concepts):**
- `concepts/digital-phenotyping-cognitive-decline.md` — referenced from new care-partner page as adjacent measurement frontier.
- `concepts/longitudinal-hearing-phenotyping.md` — referenced from new care-partner page as outcome layer.
- `concepts/hearing-loss-dementia-link.md` — referenced from new care-partner page (care-partner role most acute in dementia context).
- `comparisons/dnn-vs-natural-processing.md` — referenced from new probabilistic-generative page as a related but distinct dichotomy (probabilistic generative is a third path).
- `syntheses/ai-understanding-gap-hearing-industry.md` — referenced from both new pages.
- `concepts/on-device-ml-hearing-aids.md`, `concepts/hearing-aid-chip-architectures.md`, `concepts/dnn-architectures-hearing-aids.md` — referenced from probabilistic-generative page (parameter-budget implications).

**Index/log:**
- Updated `wiki/index.md` last-updated banner with this ingest.
- Will append banner notes for 2 new concept pages added to Concepts table.
- Appended this log entry.

**Underlying LinkedIn posts (10 May 2026, posted to Discord channel 1492462147127742565 and emailed to door.punch_4o@icloud.com):**
1. **AIDA-2 — 85-parameter Bayesian generative model as a counter-narrative to on-chip DNNs** (arXiv 2603.28436)
2. **Care partners as a hearing-aid data-model gap — ASHA NSLHM 2026** (asha.org NSLHM 2026)

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

---

## 2026-05-09 — LinkedIn drafts ingest

**Underlying LinkedIn posts:**
1. LUCIA — UK's first system-scale RCT for bilateral cochlear implants in adults (announced 6 May 2026; Cambridge / Birmingham / 14 NHS hospitals; n>250). Framed as a missing-dataset, not missing-AI, problem; access expansion runs on labeled cohorts.
2. Pediatric softband BCD database (Frontiers in Audiology and Otology, 8 May 2026, n=5,490 children, ~28 years). Framed as routine clinical telemetry serving as the warrant for candidacy expansion before guideline change.

**Sources created (2):**
- sources/lucia-bilateral-ci-trial-may-2026.md — University of Birmingham press release, 6 May 2026; first system-scale RCT of bilateral vs unilateral CI in late-deafened adults across 14 NHS hospitals; recruitment autumn 2026, 12-month follow-up; no AI/ML technology component — purpose-built to generate the labeled cohort that 30-year reimbursement debates have lacked.
- sources/pediatric-softband-bcd-database-frontiers-may-2026.md — Frontiers in Audiology and Otology, 8 May 2026; retrospective review of 5,490 children fitted with softband BCDs 1998-2025 within publicly-funded pediatric audiology system; PEACH 46% → 82% aided, 74% daily use, 88% of fittings outside the textbook microtia/atresia population (OME, craniofacial anomalies, cleft palate, unknown etiology); first large-scale characterization of contemporary fitting practices.

**Pages updated (3):**
- wiki/syntheses/cochlear-implant-access-economics.md — added new section "Adult Bilateral CI as the Next Access Frontier — LUCIA Trial (May 2026)" tying the trial to the Robinson institutional-economics keynote framing; added lucia source to frontmatter sources; added longitudinal-hearing-phenotyping to related; added bilateral-ci, rct tags; appended to Sources list; bumped updated date to 2026-05-09.
- wiki/concepts/cochlear-implant-ai.md — added subsection "LUCIA Trial — A New Cohort for Adult Bilateral CI Modelling (May 2026)" under "AI for Outcome Prediction" connecting LUCIA's labeled cohort to the JAMA / Northwestern preimplant-MRI prediction model that previously had no adult bilateral comparison data; added lucia source to frontmatter sources; bumped updated date to 2026-05-09.
- wiki/concepts/longitudinal-hearing-phenotyping.md — added new section "Pediatric BCD Exemplar — Telemetry Becomes the Warrant (May 2026)" before Use Cases, framing the n=5,490 pediatric BCD database as the proof-of-concept that routine clinical telemetry can drive guideline change at scale, and the absent adult-hearing-aid analogue as a strategic gap; added pediatric BCD source to frontmatter sources; added telemetry, candidacy-expansion tags; appended to Sources list; bumped updated date to 2026-05-09.

**Pages created (0):** Both items mapped cleanly to existing infrastructure — preferred in-place updates over near-duplicate pages, per wiki conventions.

**Index updated:** wiki/index.md — added top-line entry for today's ingest; bumped updated dates for cochlear-implant-ai.md (added bilateral-ci tag), longitudinal-hearing-phenotyping.md (added telemetry, candidacy-expansion tags), and cochlear-implant-access-economics.md (synthesis date row).

**Discord drafts posted to channel 1492462147127742565.** Email sent to door.punch_4o@icloud.com — "📝 LinkedIn Drafts — 09 May 2026" — 2 posts.

**Notes:**
- Both sources are first-week-of-May 2026, fresh material that did not overlap with any of the 60+ prior post topics in the LinkedIn post history log.
- Both items reinforce the recurring 2026 thread that hearing care's binding constraints are dataset/cohort/policy-shaped, not signal-processing-shaped — a thread that links Apple Hearing Study, MEG cortical reorganization, remote CI programming, and Robinson's CI2026 keynote.
- LUCIA timing (announced 6 May, CI2026 Chicago wraps 9 May) reads as a deliberate field-level reframing.

---

## 2026-05-09 — Daily hearing+AI digest ingest

**Sources researched (10):**
1. arXiv:2605.06189 — Predictive-Generative Drift Decomposition for SE & Separation (Richter et al., MERL/Hamburg/Paderborn). *Already ingested*.
2. arXiv:2605.04749 — Spatial-Magnifier multichannel SE (Lee, Pandey, Parekh et al.). *Already ingested*.
3. arXiv:2605.03776 — Codec intelligibility w/ noise + SE (Behringer et al.). *Already ingested*.
4. arXiv:2605.01101 — Virtual Speech Therapist clinician-in-the-loop AI agent (Sheikh et al.). **NEW**.
5. Lexie B3 OTC powered by Bose, $999/pair, 128 hr runtime, BLE 5.3, "Automatic Sound Focus". HearingTracker. **NEW**.
6. Sony OTC discontinued. *Already ingested*.
7. Brian Taylor → Neurotone AI as VP Clinical Research. *Already ingested*.
8. Phonak Virto R Infinio 2026 Red Dot Award. *Already ingested*.
9. Northwestern JAMA Oto-HNS deep transfer learning for CI language outcome prediction. *Already ingested*.
10. Auracast UK theatre rollout (National Theatre Dorfman, Bridge Theatre). *Already ingested*.

**Sources created (3):**
- sources/lexie-b3-bose-launch-may-2026.md — WSA's first post-Sony OTC vehicle. RIC, $999, 32 hr aid + 96 hr case = ~5 days, Bluetooth 5.3 (Classic + BLE), "Automatic Sound Focus" directional system. Strategic stress test of mid-priced ($700-$1,300) OTC band that Sony failed in.
- sources/virtual-speech-therapist-arxiv-2026.md — Sheikh et al. arXiv:2605.01101. Clinician-in-the-loop AI agent for speech therapy. Adjacent vertical, but exact architectural mirror of the Neurotone aural rehab pattern Brian Taylor articulated.
- sources/hearing-ai-digest-2026-05-09.md — daily digest record (10 items, 656 words, sent to door.punch_4o@icloud.com).

**Pages updated (3):**
- wiki/concepts/otc-hearing-aids.md — added lexie-b3-bose-launch-may-2026 to frontmatter sources; added "lexie, bose" tags; added Lexie B3 spec details to Lexie entry under Mass-Retail OTC Brands; added new "Mid-Priced OTC Stress Test: Lexie B3 (May 2026)" subsection under Premium OTC Pricing Failure framing the B3 as the next data point on the middle-squeeze thesis; bumped updated date to 2026-05-09.
- wiki/entities/ws-audiology-signia.md — added lexie-b3-bose-launch-may-2026 to frontmatter sources; added new "Lexie B3 — Post-Sony OTC Vehicle (May 2026)" subsection after Sony Discontinuation framing WSA's strategic bet that Sony's failure was execution-specific; appended Lexie B3 to Sources list; bumped updated date to 2026-05-09.
- wiki/entities/neurotone-ai.md — added virtual-speech-therapist-arxiv-2026 to frontmatter sources; added "clinician-in-the-loop" tag; added new "Architectural Pattern: Clinician-in-the-Loop AI Agents (May 2026)" subsection under Strategic Significance, framing Sheikh et al. as the first peer-reviewable instance of the pattern Neurotone is commercializing; appended Sheikh et al. to Sources list; bumped updated date to 2026-05-09.

**Pages created (0):** All items mapped cleanly to existing pages — preferred in-place updates over near-duplicate pages, per wiki conventions.

**Index updated:** wiki/index.md — added top-line entry for today's digest ingest above the LinkedIn-drafts entry from earlier today; bumped updated dates and tags for OTC Hearing Aids, WS Audiology / Signia, and Neurotone AI.

**Email sent:** door.punch_4o@icloud.com — "🎧 Hearing + AI Daily Digest — 09 May 2026" — 10 items: 4 papers (drift decomposition, spatial-magnifier, codec intelligibility, virtual speech therapist), 5 industry news (Lexie B3, Sony exit, Brian Taylor/Neurotone, Phonak Red Dot, FHH Conference), 1 AI/ML (Northwestern CI MRI prediction), 1 worth-watching (Auracast UK theatres). 656 words.

**Notes:**
- Light Saturday news cycle. 7 of 10 items overlapped with prior 2026-05-06 / 2026-05-07 / 2026-05-08 digests; only 2 genuinely new sources to ingest.
- Both new sources reinforce existing wiki threads: Lexie B3 → middle-squeeze OTC thesis (already developed in OTC concept page after Sony exit); Sheikh et al. → clinician-in-the-loop pattern (already implicit in Neurotone framing, now with peer-reviewable architectural exemplar).
- Discord confirmation message: "✅ Daily hearing+AI digest sent to door.punch_4o@icloud.com — 10 items covered (4 papers, 5 industry, 1 AI/ML, 1 worth-watching)."

---

## 2026-05-10 — Daily hearing+AI digest ingest

**Sources researched (5 items in digest):**
1. NDF+ — Joint Neural Directional Filtering and Diffuse Sound Extraction (Huang/Habets et al., Fraunhofer IIS / IAL Erlangen, arXiv:2605.06108, submitted 7 May 2026). *Already ingested 2026-05-08 — backfilled arXiv ID + submission date.*
2. NationsBenefits replacing Lucid Hearing as operational partner of Sam's Club's ~450 in-club Hearing Aid Centers. HearingTracker. **NEW**.
3. CI2026 Chicago closing day (6–9 May 2026). *Already ingested via ci2026-chicago-robinson-keynote-may-2026.md and aci-alliance-ci2026.md*.
4. AAA 2026 panel — AI vs. provider shortage tension. *Already ingested via aaa-2026-leadership-panel-may.md*.
5. ICASSP 2026 URGENT Speech Enhancement Challenge wrap. *Already ingested via gap-urgenet-urgent-challenge-icassp-2026.md*.

**Sources created (2):**
- sources/sams-club-nationsbenefits-supplants-lucid-may-2026.md — HearingTracker, May 2026. Channel-economics shift: WSA loses ~450 mass-retail clinic operations to NationsBenefits. Vertical-integration pattern with same operator running Aetna MA hearing benefit AND in-store dispensing.
- sources/hearing-ai-digest-2026-05-10.md — daily digest record (5 items, 506 words, sent to door.punch_4o@icloud.com).

**Sources updated (1):**
- sources/ndf-plus-neural-directional-filtering-arxiv-2026.md — backfilled arxiv_id (2605.06108), arxiv_url, exact submission date (2026-05-07). Source file previously had "specific arXiv ID to be backfilled when paper page resolves" note; resolved.

**Pages updated (3):**
- wiki/entities/ws-audiology-signia.md — added sams-club-nationsbenefits-supplants-lucid-may-2026 to frontmatter sources; added "lucid, retail-channel, sams-club" tags; added new "Lucid Hearing Loses Sam's Club Operational Role (May 2026)" subsection after the Lexie B3 subsection, framing the three structural events in ~6 weeks (Sony exit / Lexie B3 launch / Sam's Club operational role lost) and the vertical-integration model. Appended source to Sources list. Bumped updated date to 2026-05-10.
- wiki/concepts/otc-hearing-aids.md — added sams-club-nationsbenefits-supplants-lucid-may-2026 to frontmatter sources; added "sams-club, retail-channel, nationsbenefits, lucid, vertical-integration" tags; added new "Retail-Channel Vertical Integration: Sam's Club / NationsBenefits / Lucid (May 2026)" subsection after Lexie B3 subsection. Appended source to Sources list. Bumped updated date to 2026-05-10.
- wiki/concepts/hearing-aid-market-dynamics.md — added sams-club-nationsbenefits-supplants-lucid-may-2026 to frontmatter sources; added "retail-channel, vertical-integration, benefits-administrators, medicare-advantage" tags; added new "Retail-Channel Vertical Integration: Benefits Administrators Move into Dispensing (May 2026)" section before Revenue vs. Units. Appended source to Sources list. Bumped updated date to 2026-05-10.

**Pages created (0):** Single new source mapped cleanly to existing infrastructure (WSA entity, OTC concept, market-dynamics concept) — preferred in-place updates per wiki conventions.

**Index updated:** wiki/index.md — added top-line entry for today's digest ingest above the LinkedIn-drafts entry from earlier today; bumped updated dates and tags for OTC Hearing Aids, WS Audiology / Signia, Hearing Aid Market Dynamics.

**Email sent:** door.punch_4o@icloud.com — "🎧 Hearing + AI Daily Digest — 10 May 2026" — 5 items: 1 paper (NDF+), 2 industry (Sam's Club/NationsBenefits, CI2026 close), 1 AI/ML (AAA 2026 panel re-circulation), 1 worth-watching (ICASSP URGENT wrap). 506 words.

**Notes:**
- Sunday light news cycle. 4 of 5 items overlapped with prior 2026-05-06 → 2026-05-09 digests; only 1 genuinely new source ingested.
- The Sam's Club / NationsBenefits / Lucid story is the structural news of the week: it's the first US-market instance of an MA benefits administrator vertically integrating the dispensing clinic. Worth flagging for synthesis next week if NationsBenefits expands to Costco / BJs / Walmart Health.
- Three WSA US retail-channel events in ~6 weeks (Sony exit Apr / Lexie B3 launch ~6 May / Sam's Club operational role lost 10 May) reinforce the "WSA US OTC pipeline narrowing" thread that began with the Sony discontinuation. The wiki now has this thread tracked across WSA entity + OTC concept + market-dynamics concept.
- Discord confirmation message: "✅ Daily hearing+AI digest sent to door.punch_4o@icloud.com — 5 items covered (1 paper, 2 industry, 1 AI/ML, 1 worth-watching)."

---

## 2026-05-11 — LinkedIn-drafts ingest (Schmitt & Stropahl SilentCloud RWD + Francis/Seshadri Framingham 2025)

**Sources created (2):**
- sources/silentcloud-tinnitus-rwd-frontiers-may-2026.md — Schmitt & Stropahl (Sonova R&D), Frontiers in Audiology and Otology, 7 May 2026, DOI 10.3389/fauot.2026.1769291. First peer-reviewed real-world outcomes for SilentCloud (CE / FDA 510(k) tinnitus DTx). Mean THI −14.7 pts (p<0.001), Cohen's d ≈0.69, 63.5% clinically meaningful improvement among 63 iCBT completers. The headline number is the funnel: 17,271 registered → 63 completers (~0.4%). No ML methods reported — traditional stats only. Industrial provenance (Sonova).
- sources/framingham-hearing-aid-dementia-jaman-2025.md — Francis, Seshadri, Dillard, Kujawa, Welling, Alcabes, Beiser, JAMA Neurology Letters, 18 Aug 2025, DOI 10.1001/jamaneurol.2025.2713. Distinct from the existing 2024 Framingham/brain-structure source. n=2,953 Framingham adults, up to 20-yr follow-up. Under-70 hearing-aid users: 61% lower incident-dementia risk vs untreated peers. Over-70: no significant association. Self-reported HA use (no telemetry validation). Resurfaced in May 2026 via IHS Better Hearing Month PR (May 5) and McKnight's coverage (May 6).

**Pages created (1):**
- wiki/concepts/digital-therapeutics-tinnitus.md — New concept page covering tinnitus DTx as a category (CE/FDA SaMD landscape, the SilentCloud RWD result, the adherence-as-ML-problem framing, reference architecture for a dropout-aware DTx, competitive landscape, open research questions). Cross-links to care-partner-dyad-models, hearing-loss-dementia-link, longitudinal-hearing-phenotyping, audiologist-workforce-shortage, sonova-ag entity.

**Pages updated (2):**
- wiki/concepts/hearing-loss-dementia-link.md — added framingham-hearing-aid-dementia-jaman-2025 to frontmatter sources; added new "Framingham Hearing Aid Use → Incident Dementia (2025, JAMA Neurology Letters)" subsection inside the "Recent Academic Updates" section, emphasizing the age-stratified result (61% under-70 vs no effect 70+), the midlife-prevention reframing, and the product-design implication (industry has optimized for 75+ phenotype but the consequential cohort is 50–69). Appended source to Sources list with descriptive label. Bumped updated date to 2026-05-11.
- wiki/entities/sonova-ag.md — added silentcloud-tinnitus-rwd-frontiers-may-2026 to frontmatter sources; added new digital-therapeutics-tinnitus concept link to Related Pages; appended SilentCloud RWD source to Sources list. Bumped updated date to 2026-05-11.

**Index updated:** wiki/index.md — added "Digital Therapeutics for Tinnitus" entry under Concepts (tags: tinnitus, digital-therapeutics, dtx, icbt, adherence, silentcloud, sonova; date 2026-05-11). Hearing-loss-dementia-link entry already in index — date will refresh on next lint sweep.

**LinkedIn posts (2):**
- Post 1 — "SilentCloud real-world tinnitus data — the adherence funnel is the ML problem" — frames 17,271 → 63 funnel as the central ML problem (dropout-time survival, sequence-aware nudges, dyadic onboarding), not the post-completion effect size. Sonova industrial provenance.
- Post 2 — "Framingham 61% under-70 dementia reduction — design hearing technology for midlife, not retirement" — reframes the age cutoff as product strategy: industry optimizes for 75+ phenotype but the consequential intervention cohort is 50–69. Concrete data-science task list: passive midlife screening, working-age acoustic personalization, per-user cognitive-trajectory telemetry.

**Email sent:** door.punch_4o@icloud.com — "📝 LinkedIn Drafts — 11 May 2026"
**Discord posted:** channel 1492462147127742565 (LinkedIn-drafts channel)

**Notes:**
- The Schmitt & Stropahl paper is the first published RWD evidence for SilentCloud since the Sonova acquisition. The internal angle is more interesting than the external angle — the dropout funnel reveals where ML can move the needle. Worth watching for follow-up papers from the same group with adherence modelling.
- The Francis/Seshadri 2025 Framingham analysis is distinct from the existing 2024 Framingham/brain-structure source on the wiki — both ingested now, cross-linked, and labelled clearly.
- The age-stratified result (61% under-70 / no effect 70+) is the most actionable hearing-cognition finding of the past year and deserves a dedicated synthesis page if more under-70-cohort evidence accumulates. Flagging for synthesis if a third confirmatory study lands.

---

## 2026-05-12 — LinkedIn-drafts ingest (Choudhari/Mesgarani Nature Neuroscience closed-loop AAD + GN NAL-NL3 global launch)

**Sources created (2):**
- sources/brain-controlled-hearing-nature-neuroscience-may-2026.md — Choudhari, Mesgarani et al. (Columbia Zuckerman Institute), *Nature Neuroscience*, 11 May 2026, DOI 10.1038/s41593-026-02281-5. First closed-loop human demonstration of real-time brain-controlled hearing. Intracranial ECoG in epilepsy patients; system improved intelligibility, reduced listening effort, was consistently preferred across guided + self-initiated attention shifts. Reframes hearing-aid AI's loss function from signal-side enhancement to attention-side enhancement. Form-factor gap (ECoG won't ship) is now the translational question for ear-EEG / cEEGrids / non-neural surrogates. Coverage: NPR, NeurosciencneNews, Inside Precision Medicine, EurekAlert, MedicalXpress. Senior author Mesgarani is the same group behind much of the foundational AAD work since 2012.
- sources/gn-nal-nl3-global-launch-march-2026.md — GN press release, 11 March 2026. World's first commercial fitting platform built on NAL-NL3, the successor to 2011-era NL2 and the field's first data-derived prescription baseline. Global software release across ReSound Smart Fit 2.3.1, Beltone Solus Max 2.3.1, Hearing Australia Fitware 2.3.1. NL3 layers large-scale clinical fitting datasets + real-world user feedback into the prescription target. Companion enhanced AutoREM tooling automates real-ear verification. Methodology paper in *International Journal of Audiology* (online ahead of print, DOI 10.1080/14992027.2026.2648713). Distinct from the pre-existing sources/nal-nl3-fitting-protocol-2026.md trade-press summary — this source covers the GN-specific commercial launch and global software release.

**Pages created (1):**
- wiki/concepts/hearing-aid-prescription-formulas.md — New concept page covering the NAL / DSL / OEM-proprietary prescription-formula landscape. First dedicated wiki page on prescription targets as the upstream baseline every downstream AI layer (DNN, beamforming, personalization, AAD) inherits. Frames the NL2→NL3 transition as the most consequential change to the field's default starting point in 15 years. Sections: core function, the major formulas (NAL-NL1/2/3, DSL v5, Phonak APD, Oticon VAC+, Starkey e-STAT, WSA SoundFit / Sound Preference), NAL-NL3 as the data-native successor, why prescription formulas are an AI/ML story now (manufacturer divergence, closed-loop feedback opportunity, outcome equity/fairness, REM verification still matters), relationship to personalization (prior vs posterior framing), open questions. Cross-links to ml-personalized-fitting, dnn-in-hearing-aids, closed-loop-data-flywheel, wsa-sound-preference-program-april-2026, gn-hearing-resound, vcca-computational-audiology.

**Pages updated (2):**
- wiki/concepts/auditory-attention-decoding.md — added brain-controlled-hearing-nature-neuroscience-may-2026 to frontmatter sources (placed first); added "ecog, closed-loop, cocktail-party" tags; added new "First Real-Time Closed-Loop Human Demonstration with ECoG (May 2026)" subsection at the top of the Recent Academic Advances section (positioned ahead of the 2025 TU Denmark closed-loop paper since the Columbia paper is the human / perceptual milestone vs the Danish hearing-impaired-in-the-loop milestone). Appended source to Sources list at top. Bumped updated date to 2026-05-12.
- wiki/entities/gn-hearing-resound.md — added gn-nal-nl3-global-launch-march-2026 to frontmatter sources (placed first); added hearing-aid-prescription-formulas to related; added "nal-nl3, fitting-software" tags; added new "NAL-NL3 — First to Ship Data-Native Prescription Formula (March 2026)" section after the GN Advanced Science section, framing GN as having the most complete top-to-bottom data-native fitting stack (NL3 prior + Vivia DNN + AIDA-2 Bayesian) of any OEM as of mid-2026. Added prescription-formulas concept to Related Pages list. Appended source to Sources list at top. Bumped updated date to 2026-05-12.

**Index updated:** wiki/index.md — added Hearing Aid Prescription Formulas concept entry between Hearing Aid Chip Architectures and Hearing Loss and Dementia Link; bumped Auditory Attention Decoding updated date to 2026-05-12 with ecog + closed-loop tags; bumped GN Hearing / ReSound updated date to 2026-05-12 with nal-nl3 + dnn + bayesian tags. New top-line _Last updated_ entry for today's ingest.

**LinkedIn posts (2):**
- Post 1 — "Real-time brain-controlled hearing aid — first human demo and the shift in loss function" — frames the Columbia ECoG closed-loop demonstration as a reframe of hearing-aid AI's loss function (signal-side → attention-side) and lays out three implications (evaluation metrics, personalization as moment-by-moment conditioning, form-factor / ear-EEG translation).
- Post 2 — "NAL-NL3 — the prescription baseline every hearing aid starts from just went data-derived" — frames the GN NL3 launch as the unsexy-but-foundational moment when the prescription target itself becomes ML-derived, with three implications (manufacturer divergence as competitive variable, closed-loop feedback at the prior level, outcome equity as dataset-curation problem).

**Email sent:** door.punch_4o@icloud.com — "📝 LinkedIn Drafts — 12 May 2026"
**Discord posted:** channel 1492462147127742565 (LinkedIn-drafts channel)

**Notes:**
- The Columbia paper is the most consequential AAD result in years and the natural anchor for any future synthesis page on "brain-controlled hearing aids." Closed-loop with a perceptual benefit endpoint, in humans, was the missing milestone. If a follow-up paper appears with non-invasive sensing (ear-EEG, cEEGrids) achieving anything close to the ECoG result, flag for synthesis page.
- The NAL-NL3 thread now has full coverage: trade-press summary (nal-nl3-fitting-protocol-2026.md, April), commercial launch (gn-nal-nl3-global-launch-march-2026.md, March), and a dedicated concept page (hearing-aid-prescription-formulas.md) cross-referencing both. Watch for Phonak / Oticon / Starkey / WSA NL3 adoption announcements — that would be the canary for whether NL3 becomes a true cross-OEM default or stays GN-aligned.
- Both posts intentionally adopt a "data-science framing of an underappreciated change" pattern — distinct from the May 11 funnel-modelling and midlife-prevention framings, and from the May 10 Bayesian counter-narrative framing. Track for fatigue if the pattern repeats too often.

---

## 2026-05-12 — INGEST (Daily Hearing+AI Digest, second pass)

**Operation:** Ingested the daily hearing+AI digest sent this morning. Most digest items were already in the wiki from earlier ingests today (Columbia AAD paper, AAA 2026 panel, Phonak AI Excellence Award, Aizip tiny-AI, multi-stage low-latency paper, selective-NC survey, Apple Hearing Study results, Lexie B3, Oticon Verit, Auracast UK theatres, Northwestern CI language prediction). Only one genuinely new item required source creation.

**New source files (1):**
- `sonova-costco-sennheiser-sonite-r-may-2026.md` — HearingTracker, 11 May 2026. Sonova returns to Costco via a pilot trial with the Sennheiser Sonite R RIC in 100+ U.S. warehouses, reversing the 2024 Phonak pullout. Significant because it (a) restores Sonova's exposure to Costco's fitting/outcome data flow, and (b) completes a four-stack retail strategy (Phonak premium independent / Unitron mid-tier independent / Sennheiser-licensed Sonite R Costco mass / AudioNova consolidated own-brand) that gives Sonova the broadest data footprint of any OEM if scaled.

**Pages updated (1):**
- wiki/entities/sonova-ag.md — added sonova-costco-sennheiser-sonite-r-may-2026 to frontmatter sources; added new "Costco Return — Sennheiser Sonite R Pilot (11 May 2026)" subsection inside Recent Developments (May 2026), framing the four-stack retail-data strategy; appended source to Sources list. Bumped updated date to 2026-05-12.

**Email sent:** door.punch_4o@icloud.com — "🎧 Hearing + AI Daily Digest — 12 May 2026" (706 words). Headline: Columbia AAD paper.

**Notes:**
- The Costco return is a retail/strategy story, but the underlying interest is the data-footprint asymmetry it implies — Sonova is the only OEM now operating across all four major retail channel types simultaneously. If Phonak/DEEPSONIC OTAs eventually push to Sonite R units in the Costco channel, that's a much bigger story.
- No new concept or synthesis pages needed — today's digest mostly consolidated material already on the wiki. Index and concept-page hygiene is current.

---

## 2026-05-13 — INGEST (LinkedIn drafts)

**Operation:** Ingested the two LinkedIn drafts generated today (Fortell IJA preference study and WCA 2026 Seoul computational audiology programming) into the wiki.

**New source files (1):**
- `fortell-spatial-ai-ija-may-2026.md` — *International Journal of Audiology*, May 2026, DOI 10.1080/14992027.2026.2663345. Peer-reviewed preference study of Fortell's investigational "Spatial AI" hearing aid against five state-of-the-art premium incumbents. n=20 adults with mild-to-moderately-severe bilateral hearing loss, 100 randomized blinded A/B trials per participant. Investigational device preferred 99/100 (one tie); average SNR uplift 12.2 dB vs 3.0–5.9 dB for the five controls. Consultants: William Shapiro and Mario Svirsky (NYU Langone). Companion Nov 2025 intelligibility study: 17 dB SNR uplift vs 1.9 dB control, 80% word comprehension in challenging noise vs 31% control. Custom AI chip ~235× compute of conventional HA SoCs, up to 100B ops/sec, <10 ms end-to-end latency. Single Park Avenue clinic, $6,800/pair, multi-month waitlist. Framed as the first startup full-stack chip+algorithm+dataset co-design with peer-reviewed evidence beating incumbents on preference by an order of magnitude in SNR.

**Source files expanded (1):**
- `world-congress-audiology-seoul-may-2026.md` — Confirmed program details added: theme "Broadening the Horizon of Audiology"; 60 planned sessions / 10 hands-on workshops / 18 special sessions / 32 oral presentation sessions; three AI-framed plenaries; Computational Audiology Network (CAN) multi-session presence — Round Table moderated by Nicky Chong-White, Workshop "The Force Awakens: Robots, Avatars, and ASR in Clinical Audiology" by Gloria Araiza-Illan and Jan-Willem Wasmann, and Planned Session "Future e-Health: AI for the Ear and Beyond" with three named talks (AI Virtual Patients for Audiology Training, AI-Assisted Diagnosis of Childhood Ear Disease, VR-Based Fine-Tuning of Hearing Device Settings). Significance framing added: computational audiology graduates from sidecar to track at flagship congress; hiring-pipeline implication for Sonova/Demant/GN/Starkey/WSA in 2027–2028; validation-loop compression as more clinicians become ML-literate.

**New wiki pages (1):**
- `wiki/entities/fortell.md` — New entity page for Fortell as a market entrant. Covers architecture highlights (custom AI chip + Spatial AI algorithm + curated dataset, co-design philosophy), distribution and pricing (Manhattan boutique, $6,800/pair, waitlist), clinical evidence (IJA May 2026 + companion Nov 2025), strategic position (validates co-design thesis, counter-pressure on shared-silicon strategies, premium positioning ≠ mass-market threat yet, industry-sponsored evidence caveat), and four open questions (scale path, independent replication, form-factor compression, OEM response). Cross-linked to chip architectures, DNN-in-hearing-aids, speech enhancement networks, Phonak (Sphere Infinio parallel), and Sonova-AG.

**Pages updated (3):**
- `wiki/concepts/hearing-aid-chip-architectures.md` — Added Fortell to Integrated NPU / Dual-Chip section as a startup full-stack example with custom AI chip at ~235× conventional HA SoCs. Added Fortell to Processing Power Statistics table (100B ops/sec). Updated frontmatter (sources, related — added fortell entity, updated tag list to include `co-design`). Added Fortell source to bottom Sources list. Bumped updated to 2026-05-13.
- `wiki/entities/vcca-computational-audiology.md` — Added new "CAN Programming at WCA 2026 Seoul (24–27 May 2026)" section between VCCA2026 Programme and Impact. Added WCA 2026 source to frontmatter and Sources list. Added `wca2026` tag. Updated frontmatter related: list noted via Sources only. Bumped updated to 2026-05-13.
- `wiki/index.md` — Updated last-updated stanza with 2026-05-13 entry summarizing the Fortell + WCA ingest. Demoted prior 2026-05-12 stanza to "Earlier" with full text preserved. Added Fortell entity row to Entities table. Updated VCCA row tags and date. Updated Hearing Aid Chip Architectures row tags (added `co-design`) and date.

**LinkedIn posts (2):**
- Post 1 — "Fortell's 99/100 preference vs incumbent hearing aids — when the chip is designed for the algorithm" — frames the IJA preference study as evidence that the SNR ceiling moves an order of magnitude when chip/algorithm/dataset are co-designed end-to-end, validating Sonova's Sphere Infinio dedicated-AI-chip bet and challenging shared-silicon strategies. Two open questions on vertical-integration necessity and premium-pricing market impact.
- Post 2 — "World Congress of Audiology Seoul 2026 — computational audiology becomes a track, not a sidecar" — frames the CAN multi-session presence at WCA as a structural escalation of computational audiology from sub-community to track, with hiring-pipeline implications for the five major OEMs and a validation-loop compression implication for ML-pipeline builders.

**Email sent:** door.punch_4o@icloud.com — "📝 LinkedIn Drafts — 13 May 2026"
**Discord posted:** channel 1492462147127742565 (LinkedIn-drafts channel)

**Notes:**
- Fortell is the first new HA-industry entity added to the wiki in May. The page is intentionally cautious about the "startup beats incumbents" narrative — industry-sponsored study, n=20, single-clinic distribution, premium pricing — but the SNR numbers are striking enough to warrant a full entity page rather than a single subsection inside a chip-architectures page. If independent replication appears, upgrade the strategic-position section accordingly.
- The WCA / CAN angle is structurally important but harder to evidence quantitatively. Watch for the post-conference summary (late May / early June) for which CAN sessions actually drew industry attendance versus academic-only audiences. That signal is the real test of "computational audiology becoming a track."
- Both posts continue the "data-science framing of an underappreciated structural change" pattern. Three days in a row now (May 11 funnel modeling / May 12 attention-side loss function and NL3 priors / May 13 silicon-algorithm co-design and curriculum pipeline). Track for fatigue.

---

## 2026-05-14 — INGEST (arXiv: L3-SE — Linguistic Hallucination in LM-Based Speech Enhancement)

**Operation:** Ingested Wang et al., arXiv:2605.08608 (eess.AS, 9 May 2026), "Reducing Linguistic Hallucination in LM-Based Speech Enhancement via Noise-Invariant Acoustic-Semantic Distillation." LM-based speech enhancement (autoregressive token-LM over WavLM-derived codec features) names a new failure mode — linguistic hallucination — and proposes acoustic-semantic distillation as the mitigation. The wiki-relevant angle is the failure-mode + evaluation-metric-gap argument: standard HA metrics (PESQ/STOI/SI-SNR/HASPI/HASQI/DNS-MOS) measure perceptual quality and intelligibility, not faithfulness to the words actually spoken. A hallucinated output can score well on all of them. Hearing-aid field needs to import hallucination benchmarks from the text-LLM community before generative SE ships in products.

**New source files (1):**
- `sources/l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md` — Wang, Rong, Su, Tan, Wu, Fan, Luo, Luan, Lu; arXiv:2605.08608; eess.AS; 9 May 2026. Full bibliographic + architecture breakdown (three-component: noise-invariant conditioning encoder with dual acoustic+semantic distillation, high-fidelity codec with learnable weighted WavLM-layer representations, decoder-only autoregressive LM). Why-it-matters section frames four pillars: new failure-mode category (inaudible to listener, no reference signal), evaluation-metric gap, high-stakes communication (medical/financial/legal/safety), architectural implication for HA generative SE. Open questions covered (latency, hallucination measurement methodology, composition with spatial/TSE pipelines, multilingual generalization, HI-listener evaluation).

**New wiki pages (2):**
- `wiki/concepts/llm-based-speech-enhancement.md` — The autoregressive-LM-over-speech-tokens paradigm as a structurally distinct branch of the SE tree (sibling of Whisper/VALL-E/AudioLM, not a spectral mask network). Sections: core architecture (codec + conditioning encoder + decoder-only AR LM), why LM-based SE exists (naturalness, strong language prior, universal degradation handling, foundation-model trajectory), L3-SE architectural innovations, relationship to other SE paradigms (mask-based / generative-predictive fusion / diffusion / LM-based / probabilistic-generative comparison table), hearing-aid deployment considerations (latency floor, smartphone-side hybrid, 3-5 year on-chip horizon), the hallucination question (cross-link), open questions. Cross-links to dnn-in-hearing-aids, dnn-architectures-hearing-aids, large-sensor-models, model-compression, on-device-ml-hearing-aids, probabilistic-generative-models-hearing-ai, eu-ai-act-medical-devices, audio-reasoning-chain-of-thought, and primary cross-link to linguistic-hallucination-speech-enhancement.
- `wiki/concepts/linguistic-hallucination-speech-enhancement.md` — Failure-mode page. Sections: why this is a categorically new failure mode (audible-vs-inaudible table), why generative SE hallucinates (prior takes over when acoustic evidence is weak), the evaluation-metric gap (table: PESQ/STOI/SI-SNR/HASPI/HASQI/DNS-MOS/listener-panel — all miss it), why it matters for hearing aids specifically (high-stakes communication, no external verification path, asymmetric trust by user group — CI/severe-HI cohort benefits most and verifies least, regulatory implications via EU AI Act + FDA AI/ML SaMD, connection to subjective-objective gap), what the field needs to build in order (standard benchmark, faithfulness metric, inference-time confidence estimates, HI-listener forced-choice transcription tests, regulatory guidance for generative SaMD), relationship to other failure modes (final summary table — only failure mode where both columns are "no"), open questions (base rate, severity distribution, user detection thresholds, hybrid architectures, multilingual fairness, adversarial robustness).

**Pages updated (6):**
- `wiki/concepts/speech-enhancement-neural-networks.md` — Added L3-SE subsection under Recent Academic Advances (positioned after Single-Channel Speaker Distance Estimation as the latest May 2026 entry; frames structurally distinct branch + failure mode + evaluation gap + HA implication + latency floor caveat). Added llm-based-speech-enhancement and linguistic-hallucination-speech-enhancement to Related Pages. Appended L3-SE entry to bottom Sources list. Frontmatter: added source + 2 related + 2 tags; bumped updated to 2026-05-14.
- `wiki/concepts/dnn-in-hearing-aids.md` — Added new "LM-Based SE and the Linguistic-Hallucination Failure Mode (May 2026)" section between Multi-Stage Phase-Aware Enhancement and AI Aural Rehabilitation. Section frames the new failure-mode category, evaluation-metric gap, asymmetric risk by user group (cross-references Schulz et al. listener-group analysis already on this page), and production timeline. Added L3-SE source to frontmatter and bottom Sources list. Added llm-based-speech-enhancement and linguistic-hallucination-speech-enhancement to related list and Related Pages list. Tags bumped. Updated 2026-05-14.
- `wiki/concepts/large-sensor-models.md` — Added "Adjacent: LM-Based Speech Enhancement as a Foundation-Model-Shaped Audio Application" subsection framing L3-SE as the foundation-model trajectory reaching SE; flagging linguistic-hallucination as a failure mode that transfers to any cross-sensor foundation model deployed in HAs. Added 2 related links to Related Pages. Frontmatter sources/related/tags bumped. Updated 2026-05-14.
- `wiki/concepts/model-compression.md` — Added "Acoustic-Semantic Distillation (Wang et al., May 2026)" subsection under Knowledge Distillation; framed as the first SE distillation recipe whose primary objective is factuality (faithfulness to spoken words) rather than perceptual quality. Added 2 related links to Related Pages and L3-SE to frontmatter sources/related/tags. Updated 2026-05-14.
- `wiki/concepts/probabilistic-generative-models-hearing-ai.md` — Added new "vs LM-Based Speech Enhancement (L3-SE, Wang et al., May 2026)" subsection inside Relationship to Other Paradigms. Argument: AIDA-2-style architectures are hallucination-resistant by construction because inference is constrained by explicit joint distribution rather than autoregressive language prior; structural regulatory + audiological advantage if hallucination becomes the dominant safety concern. Added 2 related links to Related Pages list; added hallucination-resistance tag. Added L3-SE to bottom Sources list. Frontmatter sources/related/tags bumped. Updated 2026-05-14.
- `wiki/concepts/dnn-architectures-hearing-aids.md` — Frontmatter only: added L3-SE source, added 2 related links (llm-based-speech-enhancement, linguistic-hallucination-speech-enhancement), added llm-based-se tag, bumped updated to 2026-05-14.
- `wiki/concepts/on-device-ml-hearing-aids.md` — Frontmatter only: added L3-SE source, added 2 related links (llm-based-speech-enhancement, linguistic-hallucination-speech-enhancement), added llm-based-se tag.

**Index updated:** wiki/index.md — Top-line _Last updated_ stanza prepended summarizing the 2026-05-14 ingest. Two new concept rows added to Concepts table (LM-Based Speech Enhancement, Linguistic Hallucination in Speech Enhancement). Updated dates and tag lists on five existing concept rows: Large Sensor Models, DNN in Hearing Aids, Speech Enhancement Neural Networks, Model Compression for Hearing AI, Probabilistic Generative Models for Hearing AI. Demoted prior 2026-05-13 stanza to "Earlier" with full text preserved.

**Pages touched this ingest: 10** (1 source created, 2 wiki concept pages created, 6 wiki concept pages updated, index + log appended). On-target for the 5-15 pages-per-source schema budget.

**Notes:**
- The wiki now has explicit treatment of all four SE paradigms as distinct concept pages or sections: mask-based DNN (speech-enhancement-neural-networks), generative-predictive fusion (covered inside speech-enhancement-neural-networks via GAP-URGENet and Richter drift decomposition), probabilistic generative (probabilistic-generative-models-hearing-ai / AIDA-2), and now LM-based (llm-based-speech-enhancement / L3-SE). The comparison table on the new LM-based page is the canonical four-paradigm summary.
- The linguistic-hallucination page is the first wiki page whose primary thesis is an **evaluation-infrastructure gap** rather than a technology / market / clinical finding. It is structurally similar to the subjective-objective-hearing-gap page in that it argues for a new measurement axis the field is currently missing. If a second 2026 paper appears proposing a hallucination benchmark or faithfulness metric for SE, this page becomes the natural ingestion home and should be expanded into a benchmarking section.
- Production-relevance caveat: autoregressive LM-based SE is currently far from a HA latency budget (token-by-token generation incompatible with <10 ms algorithmic latency). The pages flag this clearly. The argument for ingestion is that (a) the failure-mode taxonomy generalizes beyond LM-based SE to any generative SE that ships in HAs, and (b) the evaluation-metric gap is real today even for current generative-predictive systems entering products.
- Watch list: any 2026 paper proposing a standard hallucination benchmark for SE; any HI-listener forced-choice transcription study under generative SE output; any regulator guidance (FDA, EMA, MHRA) addressing generative AI in SaMD audio devices; any HA OEM announcement of an LM-based SE product or research program. Each would warrant an update to the linguistic-hallucination page.

---

## 2026-05-14 — DIGEST EMAIL SENT

**Operation:** Compiled and sent daily Hearing + AI Digest email to door.punch_4o@icloud.com (subject "🎧 Hearing + AI Daily Digest — 14 May 2026"). Five items covered: Choudhari/Mesgarani brain-controlled selective hearing (*Nature Neuroscience*, 11 May 2026); Wang et al. L3-SE linguistic-hallucination paper (arXiv:2605.08608, 9 May 2026); Northwestern deep-transfer-learning pediatric CI language-outcome prediction model (JAMA Otolaryngology – Head and Neck Surgery); NationsBenefits/Sam's Club channel transition supplanting Lucid Hearing (HearingTracker, 9 May 2026); HHTM Future of Hearing Healthcare 2026 virtual conference (Hearing Review, opening 13 May 2026). All five sources already present in `sources/` from prior ingests (brain-controlled paper from 2026-05-12, L3-SE from 2026-05-14 morning ingest, CI prediction model from earlier April ingest, NationsBenefits and HHTM from prior weeks).

**No new wiki pages created in this operation** — digest is a downstream artifact of already-ingested sources. The wiki was the source-of-truth used to compile the digest, not a target for new ingestion.

**Sanity check on digest framing:**
- Brain-controlled hearing → anchored as the headline because Nature Neuroscience publication date (11 May) puts it inside the 48h "last week" window and lay-press coverage (NPR, Greek Reporter, Brighter Side) continued through May 13.
- L3-SE → framed as the second-tier headline because it's the genuinely novel ML failure-mode story and the digest reader benefits from seeing it before generic outlets pick it up.
- Northwestern CI prediction → included as a credible peer-reviewed result with a clear clinical workflow implication; cross-referenced wiki pages on cochlear-implant-ai.
- NationsBenefits/Sam's Club → included as the only material US dispensing-channel news in the 48h window.
- HHTM Future of Hearing Healthcare → included as the live event the reader can still attend (sessions 13/20/27 May).

**Discord confirmation:** Posted to active channel — "✅ Daily hearing+AI digest sent to door.punch_4o@icloud.com — 5 items covered."

**Notes:**
- Yesterday's digest (2026-05-13) leaned on Fortell + Apple Hearing Study + Starkey VA + Sonova/Sennheiser + Otarmeni + Apple OTC HAF eval. Today's digest deliberately rotated to brain-controlled AAD + L3-SE + Northwestern CI MRI + Sam's Club channel + HHTM conference to avoid republishing the same five anchors two days running. Apple expansion was demoted to a "Worth Watching" mention rather than headline placement.
- The digest's "Quick Stats" section continues to be the most reader-friendly summary — five concrete numbers, all sourced from the items above. Keep this pattern.
- Watch list for tomorrow: any independent replication of the Choudhari/Mesgarani result with non-invasive sensors; any Fortell competitor preference study (industry-sponsored response expected); any first publication of an L3-SE-style hallucination benchmark; any new Apple Hearing Study release; any major OEM Q1 earnings commentary on AI hearing aid uptake.

---

## 2026-05-17 — DAILY DIGEST INGEST + EMAIL SENT

**Operation:** Compiled and sent daily Hearing + AI Digest email to door.punch_4o@icloud.com (subject "🎧 Hearing + AI Daily Digest — 17 May 2026"). 11 items covered across Research Papers, Industry News, AI/ML Developments, Worth Watching, and Quick Stats sections. Ingested 4 net-new sources + 1 digest record into the wiki.

**New sources (5):**
1. `tf-mlpnet-tiny-speech-separation-arxiv-2026` — Itani et al., arXiv:2508.03047. First on-device real-time neural speech separation for low-power hearables. Architectural argument: deliberately avoids transformer + Mamba blocks because current HA NPUs don't support those ops. Pure MLP + depthwise-conv stacks over TF bins; beats prior streaming separation/TSE baselines within the hearable power envelope.
2. `dod-biometric-hearing-protection-fy26` — US DoD FY26 appropriations bill +$7.5M for Aware Defense custom-molded in-ear sensor system (PPG / temperature / motion / stress). Dual-use precedent that subsidizes the in-ear sensor BOM and shell-molding qualification cycle that civilian hearables will inherit on 2-4 year lag.
3. `musicians-tinnitus-meta-analysis-2026` — *Otolaryngology – Head and Neck Surgery* meta-analysis; 67 studies / 28k+ musicians / 21 countries. 42.6% tinnitus prevalence in musicians vs 13.2% controls; 25.7% hearing loss vs 11.6%; 37.3% hyperacusis vs 15.3%. **Genre-neutral** — no significant classical-vs-rock/pop difference; instrument / seating / acoustics / protection-adherence dominate over genre.
4. `fda-low-risk-ai-wellness-wearables-guidance-jan-2026` — FDA Jan 2026 guidance reducing SaMD oversight on low-risk AI-enabled wearables / wellness devices. Preserves 2022 OTC rule and Apple OTC HAF precedent. Bifurcates consumer-earwear market into regulated amplification tier vs deregulated wellness tier; generative-SE classification ambiguity remains the highest-leverage open question.
5. `hearing-ai-digest-2026-05-17` — digest record itself.

**Updated wiki pages (6):**
- `concepts/speech-enhancement-neural-networks.md` — added TF-MLPNet — Tiny On-Device Speech Separation, Accelerator-Aware subsection under Recent Academic Advances; reinforces deployable-envelope thesis (MLP / depthwise-conv / quantized-CRN as the 2026 on-chip envelope, transformer-on-HA gated on next silicon cycle); added source to frontmatter; bumped updated date.
- `concepts/on-device-ml-hearing-aids.md` — added TF-MLPNet — Accelerator-Opcode-Driven Design subsection under Key Players & Their Chips; names the design-workflow inversion of building architecture around the accelerator opcode set first then optimizing the math; added source; bumped updated date.
- `concepts/digital-therapeutics-tinnitus.md` — added occupational-cohort prevalence bullet citing the musicians meta-analysis; quantifies the genre-neutral TAM expansion lever; bumped updated date.
- `concepts/large-sensor-models.md` — added Dual-Use Defense Funding Subsidizes the In-Ear Sensor Stack section citing the DoD FY26 increase; argues defense procurement makes LSM-style HA sensor fusion a near-term realistic substrate rather than a 2030s ambition; bumped updated date.
- `concepts/otc-hearing-aids.md` — added Wellness / Medical Bifurcation (FDA Jan 2026 Guidance) subsection under Safety Limits; spells out regulated vs deregulated tier examples and the generative-SE classification ambiguity; bumped updated date.
- `concepts/hearing-aid-market-dynamics.md` — added Two Market-Structuring Regulatory + Procurement Inputs (FY26) section covering FDA Jan 2026 + DoD FY26 + musicians meta-analysis as three FY26 inputs shaping the OEM landscape on multi-year horizons; bumped updated date.

**Pages touched this ingest: 12** (5 sources created, 6 wiki concept pages updated, index + log appended). On-target for the 5-15 pages-per-source schema budget.

**Editorial framing:**
- Yesterday's digest (2026-05-16) leaned on Eargo 8 + Phonak AI awards + brain-controlled hearing + Framingham dementia + Northwestern CI prediction. Today's digest deliberately rotated to silicon-constraint / hardware (TF-MLPNet, ORKA Bose RIC, DoD biometric earwear) and regulatory (FDA AI-wellness guidance), with the musicians-tinnitus meta-analysis as the public-health anchor.
- Three of four genuinely new sources are technically older than the 48h freshness window but only surfaced in mainstream industry coverage this week (DoD funding via Biometric Update; FDA guidance via Biometric Update + DoD coverage; musicians meta-analysis re-surfaced via Neuroscience News / Medical Xpress / Classic FM in May). The TF-MLPNet paper has an Aug 2025 first-version date but the recent revision indexed in 2026; included because the "accelerator-doesn't-support-transformers" framing is precisely the production-relevance argument the wiki was missing.
- Light Sunday news cycle. No new primary product launches, no new clinical trial readouts, no new arXiv breakthroughs published in the strict 48h window. Today's value is **regulatory + procurement context** (FDA + DoD as 12-24 month market shapers) plus the **silicon-constraint architecture framing** (TF-MLPNet) — both more durable than a typical day's product/paper churn.

**Discord confirmation:** Posted to active channel — "✅ Daily hearing+AI digest sent to door.punch_4o@icloud.com — 11 items covered (3 papers, 3 industry notes, 2 AI/ML items, 2 worth-watching + 5 quick stats)."

**Watch list for tomorrow:**
- Any HA OEM commentary on the FDA Jan 2026 wellness/medical bifurcation in upcoming Q1 earnings calls (Sonova, Demant, GN, Starkey).
- Any new TF-MLPNet-style accelerator-aware architecture from a different group — would confirm the silicon-constraint design pattern is generalizing.
- Any defense-vendor product announcement leveraging the Aware Defense FY26 funding — first dual-use civilian spinout would be a meaningful market signal.
- Any clinical-tier follow-up to the Columbia brain-controlled hearing paper using non-invasive ear-EEG / cEEGrids (the form-factor gap is the dominant open question).
- Any musician-tier custom-IEM / tinnitus-DTx product announcement leveraging the 42.6% prevalence number as marketing.

---

## 2026-05-18 — LinkedIn drafts ingest

**Underlying LinkedIn posts:**
1. Signia Active Mini IX — instant-fit ITE collapses the impression-to-fit data gap that has throttled hearing-aid AI feedback loops
2. Neural codecs are *less* noise-robust than classical — and listening effort is the metric the hearing-aid pipeline forgot

**Sources processed:**
- `signia-active-mini-ix-may-2026.md` — **new** — Signia launches the world's smallest ready-to-wear ITE with full IX platform on board; same-day fitting, no custom shell; Hearing Review coverage May 12 2026.
- `codec-intelligibility-se-behringer-arxiv-2026.md` — **pre-existing** (from prior digest ingest); cross-linked into the new listening-effort concept page and into the speech-enhancement-neural-networks concept page Recent Academic Advances section.

**Pages created (1):**
- `concepts/listening-effort-evaluation.md` — formalizes listening effort as a first-class hearing-AI metric distinct from intelligibility; anchored to Behringer et al. codec finding that effort reveals differences invisible to intelligibility; documents measurement approaches (subjective scales, pupillometry, dual-task, EEG/fNIRS, ASR-derived proxies), the pipeline gap (codecs/SE/fitting), what "first-class" would mean (HASPI-equivalent for effort, regulatory acceptance criterion, telemetry-side proxies), and open questions (ASR-effort generalization to HI listeners, effort-vs-faithfulness for generative SE).

**Pages updated (2):**
- `entities/ws-audiology-signia.md` — added Active Mini IX (May 12 2026) under Form Factor Expansion subsection; added new Active Mini IX — Data-Pipeline Significance subsection covering time-to-first-telemetry compression, cosmetic-sensitive demographic reach, ITE deep-canal acoustic-phenotype expansion of the BTE-dominated training distribution, and the ~6-week WSA cadence (Sound Preference Program → Lexie B3 OTC → Active Mini IX instant-fit). Added `signia-active-mini-ix-may-2026.md` to frontmatter sources. Bumped updated date to 2026-05-18.
- `concepts/speech-enhancement-neural-networks.md` — added Codec × Speech Enhancement × Noise — Listening Effort Reveals What Intelligibility Hides subsection under Recent Academic Advances; cross-links the new listening-effort-evaluation concept page; added Behringer codec source to frontmatter sources and codec-evaluation + listening-effort tags; added listening-effort-evaluation and auracast-bluetooth-le-audio to related; bumped updated date to 2026-05-18.

**Editorial framing:**
- Signia angle deliberately reframes a routine form-factor launch as a closed-loop data-pipeline event. The product page sells discretion + same-day fitting; the data-science argument is that fit-day = data-day and Signia Assistant's learning loop now starts on hour 1 rather than week 3. The cosmetic-sensitive first-time-user cohort that the BTE-dominated training corpus has structurally missed for 20 years is now reachable.
- Codec / listening-effort angle uses an Interspeech 2026 submission to introduce a missing wiki concept. The Behringer paper was already in the source pool but had no dedicated effort-side wiki anchor — today's ingest creates that anchor and cross-links from speech-enhancement-neural-networks, linguistic-hallucination-speech-enhancement, subjective-objective-hearing-gap, cortical-reorganization-hearing-aids, multimodal-hearing-assessment, and companion-phone-speech-pipeline. Effort now has its own lookup entry alongside the existing intelligibility / faithfulness / personalization measurement axes.

**Pages touched this ingest: 4** (1 new source, 1 new concept page, 2 wiki pages updated; index + log appended). On-target for the 5-15 pages-per-source schema budget given small primary ingest (the second source was pre-existing).

---

## 2026-05-18 — Daily hearing+AI digest ingest

**Digest sent to door.punch_4o@icloud.com:** 🎧 Hearing + AI Daily Digest — 18 May 2026 (3 items: Wasano tinnitus RCT, Mesgarani brain-controlled hearing, FHH conference session 2).

**Sources processed:**
- `tinnitus-app-rct-jama-wasano-may-2026.md` — **new** — Wasano et al., JAMA Otolaryngology–Head & Neck Surgery (May 2026). Double-blind sham-controlled RCT, n=60, CBT + educational-counseling smartphone app for chronic tinnitus. Between-group THI improvement **−20.4 at week 16, −18.3 at week 24** (durable after therapeutic functions blocked). No serious AEs. Tokai University School of Medicine, Japan.
- `brain-controlled-hearing-nature-neuroscience-may-2026.md` — **pre-existing** (ingested 11 May from primary publication). Re-surfaced in NPR 14 May follow-up; no wiki delta required.

**Pages created (0).** New material consolidated into existing concept page rather than fragmented.

**Pages updated (2):**
- `concepts/digital-therapeutics-tinnitus.md` — added new "Wasano RCT — Controlled Efficacy Signal (May 2026)" section ahead of the SilentCloud RWD section; framed the two papers as complementary evidence layers (controlled efficacy vs real-world effectiveness + adherence). Added Wasano source to frontmatter sources; added `cbt` and `rct` tags; appended Wasano entry to Sources block; bumped updated date to 2026-05-18.
- `wiki/index.md` — refreshed Digital Therapeutics for Tinnitus tag list (added cbt, rct) and updated date stamp to 2026-05-18.

**Editorial framing:**
- The Wasano paper is the strongest digital-therapeutics-for-tinnitus evidence to land since the SilentCloud RWD a week ago. The framing decision was to NOT create a new concept page (DTx-tinnitus already exists and is the right home) but to explicitly position the two 2026 papers as **complementary evidence layers**: Wasano = controlled efficacy (does the protocol work?), SilentCloud = real-world effectiveness + adherence (does it reach people?). Adherence is the bridge. This framing should age well into the reimbursement-pathway conversation.
- The brain-controlled hearing story is the dominant news beat in the 11-18 May window but was ingested at primary publication; surfacing the NPR follow-up doesn't change the underlying wiki state. Noted in log for chronological completeness.
- News cycle was deliberately characterized as quiet in the digest body — a tighter, more credible 3-item brief beat padding with 24-hour-old secondary coverage of stories already covered.

**Pages touched this ingest: 3** (1 new source, 1 concept page updated, 1 index entry refreshed; log appended). Below the 5-15 schema budget but appropriate given a single substantive new source and a deliberately consolidative editorial choice.

## 2026-05-20 — LinkedIn drafts ingest

**LinkedIn drafts posted to Discord and emailed to door.punch_4o@icloud.com:**
1. **Pre-training is back.** Andrej Karpathy joined Anthropic on May 19 2026 to work on pre-training under Nick Joseph. Anthropic's framing: "use Claude to accelerate pre-training research." For hearing-care AI the strategic reread is that OEMs uniquely own a multi-decade audiogram + in-situ telemetry + fitting-outcome corpus that is too small to pre-train a general foundation model from scratch and too important to leave fully outside one — the next-decade moat may shift from "best on-chip algorithm" to "best audio + audiogram + telemetry pre-training corpus."
2. **Sonova FY 2025/26 results (May 18 2026).** Sales CHF 3,605.9M (+5.9% LC), EBITA +17.3% LC, dividend record CHF 4.70. R&D spending CHF 217.7M (+3.8% LC) — single-digit growth against a clearly broadening AI feature surface (Infinio Ultra + AutoSense OS 7.0, Sphere variants, Virto R Infinio first rechargeable custom ITE, EasyGuard, AB×Spiral Therapeutics collaboration). Two interpretations testable in next year's R&D line: (a) AI R&D productivity dividend operationalizing Karpathy's "outsource execution not understanding" in published financials, vs (b) capitalization timing where the next platform cycle's bill arrives in FY 2026/27.

**Sources processed:**
- `karpathy-anthropic-pretraining-may-2026.md` — **new** — TechCrunch, CNBC, Winbuzzer, Yahoo Finance, Reuters, US News (multiple outlets, May 19 2026). Karpathy quote in full ("the next few years at the frontier of LLMs will be especially formative … get back to R&D"). Anthropic spokesperson framing: team focused on using Claude to accelerate pre-training research. Background on Karpathy (OpenAI co-founder, ex-Tesla AI, Software 3.0, Autoresearch, LLM Wiki, idea-files). Hearing-care relevance section laying out the OEM corpus asymmetry argument.
- `sonova-fy-2025-26-results-may-2026.md` — **new** — Sonova Holding AG earnings release via Webdisclosure, MarketScreener, Investing.com, ad-hoc-news (May 18 2026). Full headline figures, segment performance (HI Wholesale+Retail +7.5% LC, CI −11.1% LC under China VBP), FY 2026/27 guidance (sales +5–8%, core EBIT +7–10%), Sennheiser divestment reclassified as discontinued operations, regionalized operating model transition, R&D-to-sales compression observation, data-science reading of the two competing hypotheses (productivity dividend vs capitalization timing).

**Pages created (1):**
- `syntheses/pretraining-corpus-as-moat-hearing-ai.md` — unifies the Karpathy news with the hearing-care OEM corpus question. Four architectural options for OEM pre-training: continued pre-training on existing audio foundation models, OEM↔frontier-lab partnership pre-training, federated/synthetic pre-training, and probabilistic/Bayesian substitutes (AIDA-2 lineage). Connects to existing wiki threads: closed-loop-data-flywheel (Option A/B vertical-data architecture upstream of fine-tuning), agentic-engineering-hearing-rd (Anthropic move operationalizes Autoresearch thesis in most expensive R&D loop), vertical-integration-trend (Amplifon-GN flywheel rationale strengthens further), probabilistic-generative-models-hearing-ai (Bayesian alternative to weight-based pre-training). Six open questions (first-mover identity, lab partnerships, compute access, regulatory framing as training-distribution disclosure under PCCPs, federated privacy architecture at audio-data scale, open-corpus contribution analog to LAION/The Pile). Cross-linked to five OEM entity pages (Sonova, Demant, GN, WSA, Starkey) as candidates for first move.

**Pages updated (3):**
- `entities/sonova-ag.md` — added FY 2025/26 Full-Year Results subsection under Recent Developments (May 2026) with figures, segment split, FY 2026/27 guidance, strategic statements, and the data-science reading naming the two competing hypotheses. Added `sonova-fy-2025-26-results-may-2026.md` to frontmatter sources; added `pretraining-corpus-as-moat-hearing-ai.md` to related; added `earnings` tag; bumped updated date to 2026-05-20. Added source entry to Sources block.
- `concepts/agentic-engineering-hearing-rd.md` — added new "Karpathy → Anthropic (May 19 2026) — Pre-Training as the Next AI-Improves-AI Loop" section between Human Understanding and Sonova Implications sections; argues the Anthropic move closes the recursive Autoresearch/Software-3.0 loop in the canonical most-expensive R&D phase, and that the strategic question for OEMs reopens to whether the moat lives in pre-training corpus, not just on-chip algorithm. Added Karpathy-Anthropic source to frontmatter; added pretraining-corpus-as-moat synthesis to related; added `pre-training` and `anthropic` tags; bumped updated date to 2026-05-20. Added source entry to Sources block.
- `concepts/closed-loop-data-flywheel.md` — added new "Pre-Training-Aware Flywheel (May 2026)" section as a fourth architecture, sitting alongside Amplifon-GN (M&A), WSA Sound Preference (software-defined), AIDA-2 (Bayesian), and the care-partner dyad extension. Frames the Karpathy news as the trigger that elevates every telemetry sample's per-sample value (future-pre-training-data vs future-fine-tuning-data) and that constrains telemetry-side architecture choices accordingly. Cross-linked to pretraining-corpus-as-moat synthesis. Added Karpathy-Anthropic source to frontmatter; added synthesis to related; added `pre-training` and `corpus-strategy` tags; bumped updated date to 2026-05-20.

**Index updated:**
- Added new synthesis page entry; updated Sonova entity row tags (added `earnings`, `fy-2025-26`) and date; new top-of-page _Last updated: 2026-05-20_ section with full ingest summary.

**Editorial framing:**
- The two news hooks are both fresh (May 18 and May 19) and chosen for thematic complementarity rather than topical overlap. Post 1 is a structural framing piece (industry-wide AI strategy shift); Post 2 is a financials-as-evidence piece (one published earnings release as a data point in the AI-productivity question). Both connect through the Karpathy axis without recycling prior Karpathy posts (Software 3.0, Autoresearch, LLM Wiki, idea files, Sequoia Ascent all previously covered — this is the first "pre-training" framing).
- The Sonova analytical framing is kept deliberately neutral and two-sided (productivity dividend vs capitalization timing) — written from an analyst's vantage on a public earnings release, not as a promotional employer-praise piece. The two interpretations are explicitly testable against next year's R&D line, which protects the post's intellectual honesty.
- Cross-wiki, the new pre-training-corpus-as-moat synthesis is the highest-leverage page produced this week because it reframes ~10 prior wiki threads (closed-loop flywheel, Amplifon-GN, WSA Sound Preference, AIDA-2, agentic engineering, DEEPSONIC corpus, Apple Hearing Study, VA dataset, NAL-NL3, gene-therapy phenotyping) under one strategic question. Expect to update it as OEMs respond to the Karpathy signal over the next 12 months.

**Pages touched this ingest: 5** (2 new sources, 1 new synthesis page, 3 existing pages updated, 1 index entry refreshed, log appended). Within the 5-15 schema budget.

## 2026-05-20 — Hearing+AI Daily Digest ingest

**Digest sent to door.punch_4o@icloud.com** (subject: "🎧 Hearing + AI Daily Digest — 20 May 2026"); Discord confirmation posted to digest channel (10 items: 3 papers, 3 industry, 2 AI/ML, 2 worth-watching).

**Sources processed:**
- `arxiv-2507-07043-selective-noise-cancellation-review-2026.md` — **new** — survey of deep-learning SNC for hearing aids; headline benchmark 18.3 dB SI-SDR with sub-10 ms variants; five named gaps (HW/SW co-design, evaluation protocol heterogeneity, regulatory framing for adaptive on-device models, environmental generalization, personalization). Reads as the contemporary review companion to the Columbia brain-controlled-hearing paper.
- `moonshine-v2-streaming-asr-2026.md` — **new** — Useful Sensors open-source streaming ASR; ~27M-param variants; "Ergodic Streaming Encoder" architectural contribution targets latency-critical deployments. Three hearing-tech hooks recorded: on-aid keyword spotting, companion-device caption pipelines, federated voice/accent personalization.
- `federated-tinyml-urban-sound-mdpi-sensors-2026.md` — **new** — MDPI Sensors 26(9):2854; federated TinyML pattern (frozen feature extractor + 231-param/1.2-kB classifier head exchanged via MQTT) lifts cross-dataset accuracy 78% → ~85%. Cleanest published template for on-device scene-classifier personalization within hearing-aid telemetry budgets and below the threshold where PCCP-style continuously-learning regulatory framing kicks in.
- Pre-existing sources referenced in the digest body but **not re-ingested** (already in wiki): `brain-controlled-hearing-nature-neuroscience-may-2026.md`, `apple-hearing-study-results-may-2026.md`, `airpods-hearing-aid-country-expansion-may-2026.md`, `sonova-fy-2025-26-results-may-2026.md`, `auracast-uk-live-theaters-april-2026.md`, `harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md`, `google-gemma-4-open-models-april-2026.md`.

**Pages created (0).** Three new sources land in well-developed concept neighborhoods (DNN-in-hearing-aids, auditory-attention-decoding, closed-loop-data-flywheel, agentic-engineering-hearing-rd, pretraining-corpus-as-moat-hearing-ai) and the editorial call is to let them cross-reference into those pages on the next substantive update rather than create thin new pages today.

**Pages updated (0).** Deliberate restraint — the digest is a *signal-distribution* operation, not a *wiki-restructure* operation. The three new sources are now discoverable via filename + frontmatter tags and will be wired into concept pages on the next ingest that has a thematic update worth bundling them with.

**Editorial framing:**
- Light news cycle today; the genuinely fresh wiki-additive material was the three sources above. The Columbia/Apple/Sonova items dominating the digest body are aftershocks of earlier ingests, surfaced for the email reader and intentionally not re-ingested.
- The arXiv review + MDPI federated-TinyML pairing is the most interesting pattern of the week: a literature snapshot of "what selective noise cancellation can do" alongside "how to personalize the classifier on-device without breaking the regulatory frame." Worth a synthesis pass once one more dot lands.

**Pages touched this ingest: 3** (3 new sources, log appended). Below schema budget by design — see editorial framing.

## 2026-05-22 — Hearing+AI Daily Digest ingest

**Digest sent to door.punch_4o@icloud.com** (subject: "🎧 Hearing + AI Daily Digest — 22 May 2026"); Discord confirmation issued (8 items: 3 papers, 2 industry, 1 AI/ML, 2 worth-watching).

**Sources processed:**
- `acclock-earbud-bcg-biometric-may-2026.md` — **new** — Help Net Security coverage (May 19 2026) of AccLock research: continuous wearer authentication via ballistocardiogram detected by earbud accelerometer/IMU already in mainstream devices. 33-user study, low single-digit EER at rest, ~2 min enrollment; degrades on walking/running and on speech (jaw vibration). Deployment blocker: OEMs do not currently expose raw IMU to third-party developers. Relevant to hearing-aid telemetry-as-identity binding and to the hearables-as-health-platform thread.
- `brain-informed-ci-speech-separation-arxiv-2601-22260.md` — **new** — arXiv eess.AS paper proposing EEG-AAD-conditioned speech separation for cochlear implants. 2 ms algorithmic latency, slightly lower parameter count than audio-only baseline, higher SI improvement. Sits in the gap between the May 2026 Columbia ECoG cocktail-party work (gold-standard but invasive) and shipping CI sound processors (latency-bound, non-invasive). Companion to existing `auditory-attention-decoding.md` concept page.
- `multi-speaker-doa-binaural-ha-icassp-2026.md` — **new** — ICASSP 2026 submission combining deep DOA estimation with a speaker-count fusion head for binaural HAs. Attacks the scene-analysis front-end (vs. the separator side attacked by the CI paper above) — together the pair frames a "front-end DOA + back-end AAD separator" architecture for the cocktail-party problem.

**Sources referenced in the digest body but NOT re-ingested** (already in wiki, verified via filename match):
- `widex-allure-ai-may-2026.md` (yesterday's ingest)
- `starkey-omega-ai-big-ai-awards-2026.md`
- `frontiers-ai-enabled-hearables-industry-2026.md`
- `dod-biometric-hearing-protection-fy26.md`
- `lexie-b3-bose-launch-may-2026.md`

**Pages created (0).** Same restraint policy as the May 20 ingest — three new sources land in well-developed concept neighborhoods (`auditory-attention-decoding`, `cochlear-implant-ai`, `lalm-selective-auditory-attention`, `closed-loop-data-flywheel`) and the editorial call is to let them be discoverable via frontmatter and cross-reference into concept pages on the next ingest that has a synthesis worth bundling them with.

**Pages updated (0).** Deferred per the same restraint policy.

**Editorial framing:**
- Second light news day in a row; the genuinely additive items today are the two arXiv papers + AccLock. Of those, AccLock is the most interesting because it lands in a part of the wiki (hearables-as-identity-platform) that does not yet have a dedicated concept page — flag for a concept-page creation on the next ingest that has at least one more biometric-hearables data point to pair with it.
- The Brain-Informed CI Speech Separation paper + the Multi-Speaker DOA Binaural HA paper are a natural pair: front-end (DOA + count) + back-end (AAD-conditioned separation). Worth a comparison page (`comparisons/front-end-vs-back-end-cocktail-party.md`) when at least one more entry in either side appears.
- Apple AirPods country expansion (May 12) and the Columbia/Apple/Sonova items dominating recent news cycles were intentionally suppressed from today's digest to avoid duplicating yesterday's coverage.

**Pages touched this ingest: 3** (3 new sources, log appended). Below schema budget by design — see editorial framing.

## 2026-05-26 — Hearing+AI Daily Digest ingest

**Digest sent to door.punch_4o@icloud.com** (subject: "🎧 Hearing + AI Daily Digest — 26 May 2026"); Discord confirmation posted to digest channel (9 items: 3 papers, 3 industry, 1 AI/ML, 2 worth-watching). Lead story: WCA 2026 Seoul Day 3 — Pichora-Fuller Aram Glorig Award lecture.

**Sources processed:**
- `arxiv-2603-07471-lightweight-se-adaptation.md` — **new** — Cui et al., March 2026 arXiv preprint. Frozen SE backbone + LoRA-style adapters updated via self-supervised training. <1% of base-model parameters updated; +1.51 dB SI-SDR average within 20 updates per scene. Cleanest published template this quarter for the on-device-personalization-without-PCCP-trauma problem.
- `arxiv-2603-02724-own-voice-detection-simulated-tfs.md` — **new** — March 2026 arXiv. Single-microphone own-voice detection trained on simulated transfer functions, 80% accuracy on real HA recordings with no fine-tuning, aided by lightweight test-time feature compensation. Direct relevance to OVPL / occlusion management and to OTC in-ear form factors that lack outward-facing mics.
- `jmir-otc-hearing-aids-dementia-2026.md` — **new** — JMIR Human Factors 2026;13:e83857. Semi-structured interviews on OTC HA facilitators/barriers in people with dementia — fills the population gap in the existing OTC efficacy literature.

**Sources referenced in the digest body but NOT re-ingested** (already in wiki, verified via filename match):
- `world-congress-audiology-seoul-may-2026.md` (WCA 2026 conference announcement)
- `wca-2026-pichora-fuller-aram-glorig-may-26-2026.md` (today's marquee lecture, ingested earlier)
- `starkey-omega-ai-aaa-2026-showcase.md` + related Starkey Omega Government Services coverage
- `federated-tinyml-urban-sound-mdpi-sensors-2026.md` (referenced as architectural pair to the new arXiv:2603.07471)

**Pages created (0).** All three new sources land in well-developed concept neighborhoods (DNN-in-hearing-aids, closed-loop-data-flywheel, pccp-regulatory-framing, own-voice-processing, otc-hearing-aids, hearing-cognition). Same restraint policy as 2026-05-20 and 2026-05-22 ingests — discoverability via filename + frontmatter tags is sufficient; concept-page updates batched for the next ingest with a synthesis worth bundling them with.

**Pages updated (0).** Deferred per the same restraint policy.

**Editorial framing:**
- The two arXiv 2603.xx papers are a natural pair: both shipping-model-is-frozen, both close the deployment gap with a lightweight delta (low-rank adapter vs test-time feature compensation). Worth a future synthesis page on "test-time adaptation patterns for hearing-aid ML" once one or two more entries land — flag for the next ingest with an additional candidate.
- The JMIR OTC-dementia paper is thematically downstream of today's Pichora-Fuller WCA lecture: both argue audiology has been measuring the wrong variables and that cognitive-load × hearing-loss is the underweighted axis. Worth surfacing together in any future synthesis pass on "FUEL framework as a lens for product evaluation."
- WCA 2026 Seoul is generating most of the AI-in-audiology signal this week; expect more ingests as Days 3-4 (May 26-27) close out and trip reports surface.

**Pages touched this ingest: 3** (3 new sources, log appended). Below schema budget by design — see editorial framing.

## 2026-05-27 — Hearing+AI Daily Digest ingest

**Digest sent to door.punch_4o@icloud.com** (subject: "🎧 Hearing + AI Daily Digest — 27 May 2026"); Discord confirmation posted to digest channel 1490303675648970823 (8 items: 3 papers, 2 industry, 1 AI/ML, 2 worth-watching). Lead story: WCA 2026 Seoul Day 3 — Brent Edwards (NAL) on "audiologists don't need patient consent to use AI," Stefan Launer (Sonova) on AI-as-benefit not AI-as-feature.

**Sources processed:**
- `wca-2026-day3-edwards-launer-strophal-ai-panel-may-26-2026.md` — **new** — Independent journalism (Liam O'Dell, May 26 2026) on the WCA Day 3 AI panel. Three named on-record positions: Edwards (NAL Australia) — no patient consent required for clinical AI use, but transparency essential; Launer (Sonova) — industry should stop AI-feature talk and start AI-benefit talk; Strophal — three-bucket clinical-surface taxonomy (efficiency/back-office, patient education, pre/post-appointment counseling). Surfaces a *genuinely new wiki theme* — clinician-side AI consent and trust — that is not yet anchored anywhere on the wiki. Strophal's taxonomy also makes explicit a clinic-side vs device-side AI partition that the wiki has been implicitly conflating.
- `arxiv-2605-23604-word-level-cpc3-fusion-nakazawa-may-2026.md` — **new** — Nakazawa CPC3 *text-assisted* submission (22 May 2026, same author and date as the 2605.23619 non-intrusive paper already in wiki). Frozen Whisper encoder + teacher-forced decoder conditioned on canonical transcript + word-aligned cross-attention acoustic branch. Joint fusion: Eval RMSE 24.39 / Corr 0.806 / incorrect-word F1 0.778. Headline negative result: text-assisted gains only +~0.01 in correlation over the non-intrusive variant on this evaluation — implies the frozen-foundation-model class has a near-term ceiling that adding a transcript does not break.
- `arxiv-2605-25605-aad-lopeo-unbalanced-eeg-may-2026.md` — **new** — Zhang, Liang, Lin, Lu (Nanjing-affiliated, ~26 May 2026). Methodological correction: DNN stimulus-reconstruction AAD decoders systematically overestimate accuracy on unbalanced EEG datasets. Proposes LOPEO (Leave-One-Paired-Envelope-Out) cross-validation, validated on KUL/DTU/NJU cEEGrid. Materially affects published AAD benchmarks — sibling to the May "ASR Too Good to Be True" correction. The existing `auditory-attention-decoding.md` concept page now rests on numbers that need a methodology-asterisk.
- `arxiv-2605-21141-lcmv-deep-beamformer-multi-speaker-may-2026.md` — **new** — Zaidel, Engel, Engel, Gannot (Bar-Ilan / Gannot lab, 20 May 2026). DNN estimates beamforming weights directly from noisy multichannel input while enforcing LCMV distortionless + null-on-interferer constraints via an augmented-Lagrangian-style multi-term loss. Beats classical LCMV; more controlled sidelobes. Completes the spatial-filtering leg of the cocktail-party stack — pairs naturally with `multi-speaker-doa-binaural-ha-icassp-2026.md` (front-end DOA + speaker count).

**Sources referenced in the digest body but NOT re-ingested** (already in wiki, verified via filename match):
- `frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md` (today's earlier LinkedIn-pass ingest — Nakazawa's non-intrusive companion paper)
- `multi-speaker-doa-binaural-ha-icassp-2026.md`
- `dat-cftnet-ci-speech-enhancement-icassp-2026.md`
- `gap-urgenet-urgent-challenge-icassp-2026.md`
- `wca-2026-pichora-fuller-aram-glorig-may-26-2026.md` (paired Day 3 lecture)
- `sonova-fy-2025-26-results-may-2026.md`

**Pages created (0).** Continued restraint policy from the 2026-05-20, 2026-05-22, and 2026-05-26 ingests — all four new sources land in well-developed concept neighborhoods. The genuinely new theme (clinician AI consent + trust) is anchored in only one source so far; per policy, defer the concept-page creation until a second data point lands.

**Pages updated (0).** Deferred per restraint policy. Three carry-forward flags:
1. `concepts/auditory-attention-decoding.md` should get a methodology-asterisk on the next ingest with a follow-up paper that either replicates LOPEO or re-runs prior AAD benchmarks under it. This is the most pressing of the deferred updates — existing claims now rest on potentially inflated numbers.
2. `concepts/non-intrusive-intelligibility-prediction.md` (created earlier today) should be revised to acknowledge the text-assisted/non-intrusive pair from Nakazawa once a third CPC3 paper lands — flag for a `comparisons/non-intrusive-vs-text-assisted-cpc3.md` page at that point.
3. A new concept page `concepts/clinician-ai-consent-and-trust.md` should be created the next time a corroborating data point (regulator statement, professional-body position, second on-record clinician quote) lands.

**Editorial framing:**
- Two of the four sources today are *methodological corrections* (AAD LOPEO; implicit ceiling-finding in Nakazawa's text-assisted vs non-intrusive comparison). This is the second consecutive ingest dominated by methodology rather than capability — pattern worth naming: hearing-AI has crossed the threshold where its own hygiene papers are showing up in the same week as its capability papers. That's a maturity signal.
- The Edwards "no consent required" claim is jurisdiction-specific (Australia-leaning); under EU AI Act Class IIa it may not survive. Worth a deeper cross-reference pass with `concepts/eu-ai-act-medical-devices.md` on a future ingest.
- WCA 2026 Seoul closes today (May 27); expect a 3-5 day wave of trip reports from AudiologyOnline, Hearing Review, and Hearing Health & Technology Matters. Several of those will likely re-quote the Edwards / Launer panel — when corroborating coverage lands, that's the trigger to create the consent-and-trust concept page.
- The cocktail-party stack now has anchors at all four stages (DOA + speaker count → spatial filter → separation → attention-guided refinement). One more entry at *any* stage and a `comparisons/cocktail-party-stack-front-to-back.md` page becomes the right move.

**Pages touched this ingest: 4** (4 new sources, log appended, index updated). Below schema budget by design — see editorial framing.

## 2026-05-28 — LinkedIn drafts ingest

**Drafts emailed to door.punch_4o@icloud.com** (subject: "📝 LinkedIn Drafts — 28 May 2026 (corrected)"); Discord channel: 1490303675648970823. Two posts: (1) GN/Ampetronic Seoul Session + YouGov stigma data — stigma as the missing demand-side variable in the hearing-care funnel-attribution stack; (2) Nakazawa's second CPC3 paper — granularity (utterance → sentence → word → phoneme) as a separable third axis from encoder choice and fusion architecture.

**Sources processed:**
- `gn-auracast-seoul-session-big-ocean-may-2026.md` — **new** — GN Hearing × Ampetronic Seoul Session at WCA 2026 (May 26 2026). Kind Seoul jazz club becomes the first permanent Auracast venue installation in South Korea; live performance by Big Ocean (K-pop trio whose three members all wear hearing aids and cochlear implants); Andreas Anderhov (GN APAC President) confirmed permanence on the record. In parallel GN released YouGov nationally representative survey data — 30 January – 4 February 2026, n≈3,053 across AU/UK/US with n≈955 hearing-loss respondents — showing up to 40% of people with hearing loss are perceived as less intelligent or less capable, >1/3 read as rude or disengaged, >1/3 report others believe they should "try harder" to hear. Structurally a counter-stereotype-exposure intervention on the stigma variable the funnel-attribution stack has never instrumented.
- `arxiv-2605-23604-word-level-cpc3-fusion-nakazawa-may-2026.md` — **already in wiki** (ingested in the 2026-05-27 daily digest pass). Surfaced today for the LinkedIn pass as the granularity-as-a-third-axis counterpoint to yesterday's frame-aligned fusion post. The two Nakazawa CPC3 papers (same author, same week, same dataset, different architectural axes) are now the structural backbone of the foundation-model-fusion-speech concept page.

**Pages updated (4):**
1. `concepts/auracast-bluetooth-le-audio.md` — added "First South Korea Auracast Venue + K-Pop Performance (May 26, 2026)" section covering Big Ocean performance, Anderhov permanent-install confirmation, YouGov stigma data, and three implications spanning OEM behavior / metric stack / regulator framing. Added `stigma` tag; added `hearing-care-funnel-attribution` to related; bumped updated to 2026-05-28.
2. `entities/gn-hearing-resound.md` — added "Seoul Session at WCA 2026 — Stigma + Cultural Deployment (May 26, 2026)" section reframing GN's WCA positioning from product showcase to demand-side intervention. Added `stigma`/`korea`/`lmic` tags; added `hearing-care-funnel-attribution` to related; bumped updated to 2026-05-28.
3. `concepts/hearing-care-funnel-attribution.md` — added "Stigma as the Missing Demand-Side Input (May 2026)" section. Three implications: (a) stigma is upstream of awareness so the funnel needs a pre-awareness identity-threat-suppression stage; (b) cultural-visibility events are interventions not marketing and counter-stereotype-exposure is the right model class; (c) three currently-unlogged inputs a stigma-aware adoption model needs — cultural-visibility events, partner/family attitudes via care-partner enrollment, post-fitting social environment via existing on-device telemetry. Added `stigma`/`cultural-visibility` tags; bumped updated to 2026-05-28.
4. `concepts/foundation-model-fusion-speech.md` — added "Granularity Is a Third Axis (May 22, 2026 — same author, different paper)" section using the second Nakazawa paper. Frozen Whisper encoder + decoder conditioned on canonical transcript + word-aligned local acoustic branch + utterance-level global branch; per-word correctness probability aggregated into sentence score; Eval RMSE 24.39 / Corr 0.806 / incorrect-word F1 0.778 / MCC 0.626 on CPC3 (baseline 24.92). Headline framing: granularity (utterance / sentence / word / phoneme) is a separable search axis from architecture, and word-level scoring gives OEMs + regulators *which words failed* — the substrate for post-market surveillance distributions that sentence-level RMSE cannot produce. Both Nakazawa source files now in frontmatter; added `word-level-prediction` tag; bumped updated to 2026-05-28.
5. `syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md` — added "Update — 28 May 2026: Granularity Joins as a Third Axis" section. The search space is now encoder choice/pairing × fusion architecture × output granularity, and word-level prediction is the granularity axis's first deployable substrate for the "which words failed" post-market surveillance distribution the field needs. Bumped updated to 2026-05-28.

**Pages added to index (4) — backfill correction:**
- `concepts/non-intrusive-intelligibility-prediction.md` (created 2026-05-27 LinkedIn ingest, never wired into index table)
- `concepts/foundation-model-fusion-speech.md` (created 2026-05-27 LinkedIn ingest, never wired into index table — updated 2026-05-28)
- `concepts/continual-learning-hearing-ai.md` (created 2026-05-27 LinkedIn ingest, never wired into index table)
- `entities/clarity-prediction-challenge.md` (created 2026-05-27 LinkedIn ingest, never wired into index table)

These four pages were created in the 2026-05-27 LinkedIn ingest but the index row additions were not committed — the index's `_Last updated` block referenced them in the natural-language summary but the tables themselves did not list them. Corrected today.

**Editorial framing:**
- The GN Seoul + YouGov stigma release lands in a part of the funnel-attribution model that was named as a gap on 2026-05-16 but had no anchor source. Today's release provides the first nationally representative quantification of perceived-stigma (n≈3,053 across three countries) as an input to the hearing-care funnel — paired with a structurally clean counter-stereotype-exposure intervention (permanent Auracast install + K-pop performance with hearing-aid-wearing performers) that GN has effectively turned into a demand-side A/B substrate. This is the first time the wiki's funnel-attribution model has both a measurement (YouGov) and an intervention (Seoul Session) for the stigma variable in the same week.
- The second Nakazawa paper completes a pattern that was only half-visible after yesterday's post: the same author, same week, same dataset, two papers attacking the CPC3 benchmark along two orthogonal architectural axes (fusion location vs output granularity). The foundation-model-fusion-speech concept page now has both papers as structural anchors and explicitly names the three-axis search space (encoder choice × fusion architecture × output granularity) as the competitive frontier for the next 12 months. The synthesis page's "what is still missing" inventory shrinks by one — word-level prediction is now deployable on the existing fusion-architecture substrate.
- Index integrity: the 2026-05-27 LinkedIn ingest created four pages but only mentioned them in the natural-language `_Last updated` block — the index tables were not updated. Today's pass catches that and reconciles the index. This is the second time this quarter that the index-table update step has been skipped on the LinkedIn-ingest path; flag for a future lint pass to scan the natural-language entry summaries for `Created N new wiki pages` strings that do not have matching table rows.

**Pages touched this ingest: 9** (1 new source, 5 wiki pages updated content-wise, 4 wiki pages added to index tables, log appended).

## 2026-05-28 — Daily hearing+AI digest ingest

**Digest emailed to door.punch_4o@icloud.com** (subject: "🎧 Hearing + AI Daily Digest — 28 May 2026"). Three items: (1) CFMDCTCodec sub-kbps neural speech codec (arXiv:2605.26812); (2) Demant Q1 2026 results — Oticon Zeal carries the quarter; (3) FHH Virtual Conference 2026 Day 3 wrap.

**Sources processed:**
- `arxiv-2605-26812-cfmdctcodec-may-2026.md` — **new** — Du, Ai et al. MDCT-domain encoder–quantizer–decoder + noise-prior-aware conditional-flow-matching (CFM) spectral enhancer with ODE solver. Non-adversarial joint reconstruction + quantization + CFM objective. **0.65 kbps** operating point, perceptual quality approaching much larger codecs with significantly fewer parameters. Accepted at IEEE/ACM TASLP. Relevance is squarely Auracast / BLE Audio bitrate frontier rather than SE — kept it out of the speech-enhancement-neural-networks page on that basis.
- `demant-q1-2026-zeal-results-may-2026.md` — **new** — Total revenue +16% (+6% organic + +10% acquisitions); Hearing Aids organic ex-customers +9%, driven by global Oticon Zeal rollout. Gross-margin expansion on higher ASPs and mix. Share +~11% on print. 2026 outlook held at 3–6% organic / DKK 4.1–4.5B EBIT-before-specials, with low-end results "less likely" — explicit upward-skew language within the band. On track for DKK 250M savings in 2026 (DKK 500M total by 2028). Reported global HA market read: **+4% value (+3% units, +1% ASP)** — top of Demant's assumed 2–4% 2026 range; 9% organic vs. 3% global units = **share taken**.
- `fhh-virtual-conference-2026-may-27.md` — **new** — Sixth annual HHTM Future of Hearing Healthcare virtual conference; three half-day sessions on May 13 / 20 / 27 / 2026; 23+ expert-led sessions. Day 3 closes the third major industry conversation in three weeks (after AAA 2026 leadership panel and WCA 2026 Seoul) that put AI front and centre — pattern reinforced: AI is no longer treated as a forecast item, the unresolved questions are clinician trust + patient-benefit evidence + informed consent, not raw capability.

**Pages updated (3):**
1. `entities/demant-oticon.md` — added "May 2026 — Q1 2026 results" entry under Corporate Developments, with the +16% / +6% / +9% breakdown, gross-margin expansion, share reaction, outlook held with upward-skew language, market-share-taken framing, and cross-links to `concepts/hearing-aid-market-dynamics` and `syntheses/hearing-aid-market-outlook`. Added `demant-q1-2026-zeal-results-may-2026.md` to frontmatter sources. Added `earnings`/`share-shift` tags. Added `hearing-aid-market-dynamics` to related. Bumped updated to 2026-05-28.
2. `concepts/hearing-aid-market-dynamics.md` — added **"Q1 2026 Two-OEM Cross-Check: Market Value at Top of Band (May 2026)"** section with two-print triangulation table (Sonova FY 25/26 + Demant Q1 26), the unit-deceleration-vs-value-cycle-top-of-band reconciliation, the premium-product-launch-cadence framing as the main share-shift lever, and the explicit Demant outlook-skew language. Added both Sonova and Demant Q1 sources to frontmatter. Bumped updated to 2026-05-28.
3. `concepts/auracast-bluetooth-le-audio.md` — added **"Sub-kbps Neural Codecs Push the Bitrate Frontier (May 2026)"** section covering CFMDCTCodec's MDCT-domain architecture and 0.65 kbps operating point. Four-bullet relevance frame: (a) regime LC3/LC3plus cannot reach; (b) multi-stream broadcast venue airtime relief; (c) on-device decoding parameter-count favourable but ODE-solver remains an open MIPS/latency question; (d) codec-SE blurring via post-decode CFM enhancement, pairs with Behringer codec-SE-intelligibility source. Closed with the SIG-roadmap watch flag for sub-kbps codec profile signalling in the next 12–24 months. Added CFMDCTCodec source to frontmatter and Sources list. Bumped updated to 2026-05-28.

**Pages created (0).** Three new sources, but each lands in a well-developed neighbourhood — restraint policy continues. FHH 2026 specifically would have anchored a `concepts/ai-clinician-trust.md` or similar, but per the 2026-05-27 carry-forward flag the consent/trust concept page should wait for a second on-record clinician quote or a regulator statement; FHH 2026 is corroborating-coverage tone rather than a fresh data point.

**Carry-forward flags (continuing from 2026-05-27):**
1. `concepts/auditory-attention-decoding.md` methodology-asterisk on next AAD ingest under LOPEO protocol.
2. `concepts/non-intrusive-intelligibility-prediction.md` revise with third CPC3 paper, flag for a `comparisons/non-intrusive-vs-text-assisted-cpc3.md`.
3. `concepts/clinician-ai-consent-and-trust.md` create when next corroborating data point lands (regulator statement, professional-body position, second on-record clinician quote). **FHH 2026 Day 3 is corroborating-tone but not new-data; flag still open.**

**Editorial framing:**
- The CFMDCTCodec finding lands at an unexpected place in the wiki — *not* on the SE page (which would be the obvious guess) but on the Auracast page, because the operating point that matters is **bitrate, not intelligibility-in-noise**. This is the second consecutive ingest where a paper's most useful framing was not at its surface-level topic — see also 2026-05-27 where the Nakazawa word-level paper went on `foundation-model-fusion-speech` rather than on `non-intrusive-intelligibility-prediction`. Worth a future synthesis on what "the right home for an SE paper" is when the architecture borrows from codec/LLM/CI machinery.
- Two large-OEM prints in two weeks (Sonova FY 25/26 + Demant Q1 26) **both reading market at top of the 2–4% band** is now the clearest 2026 macro signal we have — and it sits *alongside* the EHIMA 2025 unit-deceleration print (+2.1% YoY). The reconciliation matters: 2026 unit growth is recovering off the 2025 trough (+3% global units per Demant Q1) while ASP contribution (+1%) does the rest of the value-cycle work. The new "Q1 2026 Two-OEM Cross-Check" section on `hearing-aid-market-dynamics` is the canonical place for this reconciliation going forward.
- FHH 2026 Day 3 closes a three-conference pattern (AAA → WCA → FHH) where AI moved from a future-tense talking point to a present-tense workflow item in the same six weeks. The unresolved questions across all three were *trust + benefit-evidence + consent*, not capability. This is the strongest signal yet that the AI-in-hearing-care subfield has crossed into a maturity phase where the bottleneck is interpretive infrastructure, not technical capability. If FHH session recordings drop usable quotes from clinician panels in the next 7–10 days, the consent-and-trust concept page becomes the right next move.

**Pages touched this ingest: 6** (3 new sources, 3 wiki pages updated, log appended).

## 2026-06-01 — LinkedIn drafts ingest (2 posts)

**LinkedIn posts drafted, posted to Discord (channel 1492462147127742565), emailed to door.punch_4o@icloud.com.**

**Sources processed:**
- `audien-atom-air-launch-may-28-2026.md` — **new** — Audien Hearing launches Atom Air OTC, $149 MSRP, **A1 MAX chip, single hearing mode, no app, no fitting, 24h battery, nearly-invisible ITE**. Marketing framed explicitly as anti-complexity / anti-personalization ("lightweight, discreet, affordable, easy to use; does not require apps or in-office appointments"). Positions between Atom One ($99) and Atom Pro 2 ($249) on form-factor / isolation but *identically below* Pro 2/X on personalization features. Distributed through Audien's existing 11,000+ retail location footprint (Target, Walmart, Best Buy, CVS).
- `claude-opus-4-8-effort-controls-may-28-2026.md` — **new** — Anthropic releases Claude Opus 4.8 with **user-controlled "effort" slider** (fast = 2.5× speed, ~3× cheaper; high-effort default = better quality at comparable Opus 4.7 token spend) and **dynamic workflows** for Claude Code (hundreds of parallel sub-agents coordinated mid-task; Messages API now accepts system entries inside the messages array). First frontier-LLM release to ship continuous user-controlled cognitive-effort dosing as a UI primitive — not hidden behind opaque router labels. Released 9 days after Karpathy joined Anthropic's pre-training team (May 19); positioned by Anthropic as more honest about uncertainty and more capable of longer independent work.

**Pages updated (2):**
1. `concepts/otc-hearing-aids.md` — added the **Atom Air launch entry** under Audien Hearing in the "Mass-Retail OTC Brands" list (single mode / no app / 24h / A1 MAX / ITE, $149); added new section **"OTC Bifurcation: Personalization vs Simplicity (May 2026)"** with two-pole table (personalization pole anchored by Apple AirPods Pro 2/3, Sennheiser All-Day Clear, Lexie B2/B3, Eargo 8, Phonak Virto R Infinio, Widex Allure Clarity Boost; simplicity pole anchored by Audien Atom One / Atom Air, Ceretone, MDHearing), middle-squeeze framing tied to Sony CRE discontinuation + Lexie B3 as live experiment, data-science implications (telemetry vacuum at the simplicity pole, personalization roadmap denominator question), three open questions. Added `audien-atom-air-launch-may-28-2026.md` to frontmatter sources. Added Atom Air to Sources list at bottom. Bumped updated to 2026-06-01. Added `anti-personalization, audien-atom-air` to index tag row.
2. `concepts/listening-effort-evaluation.md` — added new section **"The Claude Opus 4.8 Parallel — Effort as a User-Controlled Dosing Parameter (May 28 2026)"** with comparison table (continuous slider vs. binary Clarity Boost button, explicit cost trade-off vs. hidden battery cost, user dosing vs. adaptive routing, token-measurable effort vs. unmeasured listening effort). Framed the personalization-UX moat as "continuous user-controlled effort slider + real effort metric (pupillometry from earbud sensors, in-ear EEG, behavioural proxies), not perceptual surrogate." Added `claude-opus-4-8-effort-controls-may-28-2026.md` to frontmatter sources; updated `last_change` note. Added Claude 4.8 source to Sources list. Bumped updated to 2026-06-01. Updated index tag row.

**Pages created (0).** Two new sources, both landing in well-developed neighbourhoods (OTC bifurcation extends the existing OTC concept page; Claude effort-dosing extends the existing listening-effort-evaluation page). Restraint policy continues.

**Editorial framing:**
- The Audien Atom Air is the cleanest single-product evidence yet of the OTC market bifurcating into two non-overlapping product hypotheses. The pre-existing `otc-hearing-aids` concept page had a strong "Sony middle-squeeze" thread already; the new section formalises it as a two-pole synthesis with an explicit anti-personalization label for the simplicity pole. Worth watching whether the simplicity pole stays at the entry tier or drifts upward as commodity-chip cost curves move.
- The Claude Opus 4.8 effort-dosing parallel is the second time this month a frontier-LLM release has illuminated a hearing-care construct gap by operationalizing it elsewhere first (the previous was QVAC MedPsy on May 7 illuminating the companion-phone medical-LLM substrate). The pattern — *LLM industry ships X as a product feature → audiology realizes it has been the implicit objective function for decades but is operationally absent* — is now a recurring framing. Open question: which other audiology constructs are next in this pipeline (faithfulness/factuality? confidence calibration? behavior-cloning from telemetry?).
- Both posts and both ingests deliberately avoided overlap with the active May 27–28 threads (Nakazawa CPC3 fusion-architecture × granularity, representation-centric continual learning, GN/YouGov stigma funnel, Demant Q1 + Sonova FY top-of-band cross-check). Today's two posts open fresh axes: **product-philosophy bifurcation at the OTC anchor price** (Audien) and **effort-as-dosing-primitive imported from the LLM frontier** (Anthropic).

**Carry-forward flags (continuing from 2026-05-28):**
1. `concepts/auditory-attention-decoding.md` methodology-asterisk on next AAD ingest under LOPEO protocol.
2. `concepts/clinician-ai-consent-and-trust.md` create when next corroborating data point lands (regulator statement, professional-body position, second on-record clinician quote).
3. **NEW:** Watch for OEM response to the Audien Atom Air anchor — does any premium OEM announce a simplified / no-app SKU within 3-6 months? If yes, the bifurcation thesis hardens; if no, the bifurcation remains a market-segment story rather than a product-portfolio one.
4. **NEW:** Watch for the next OEM hearing-aid product release that ships a *continuous* user-controlled processing-intensity / effort slider (beyond Widex Allure's binary button). The Claude 4.8 framing predicts this becomes a 12-24 month roadmap item; first OEM to ship defines UX category.

**Pages touched this ingest: 5** (2 new sources, 2 wiki pages updated content-wise, 1 index updated, log appended).

---

## 2026-06-01 — Daily Hearing+AI Digest ingest (11 items, 0 new sources)

**Digest emailed to door.punch_4o@icloud.com at 06:47 PT.** Sections covered: 3 research papers, 4 industry news items, 2 AI/ML developments, 2 worth-watching, 5 quick-stat lines.

**Items covered (all already in wiki — restraint policy applied, no duplicate source files created):**

Research:
- Columbia brain-controlled hearing aid (Nature Neuroscience, May 11) → `brain-controlled-hearing-nature-neuroscience-may-2026.md` (ingested 2026-05-12)
- AI predicts CI language outcomes (JAMA Oto, deep transfer learning, n=278) → `ai-predicts-ci-language-outcomes.md` + `pediatric-ci-language-prediction-transfer-learning-2025.md`
- Low-latency DL noise reduction across NH/HI/CI (Frontiers Aud & Oto) → `low-latency-dnn-noise-reduction-frontiers-2025.md`

Industry:
- Widex Allure AI RIC launch (5 markets today 2026-06-01, dual-chip, Clarity Boost button, +6 dB SNR claim, Compass Cloud 2.0) → `widex-allure-ai-may-2026.md`
- Sonova SilentCloud acquisition (tinnitus, VA channel) → `sonova-silentcloud-acquisition-2026.md`
- Apple AirPods hearing aid country expansion (100+ regions, May 2026) → `airpods-hearing-aid-country-expansion-may-2026.md` + `apple-airpods-india-italy-taiwan-may-21-2026.md`
- Phonak Virto R Infinio Red Dot + iF Design awards 2026 → `phonak-virto-r-infinio-red-dot-april-2026.md`

AI/ML:
- Speech foundation models in SE loss functions (WavLM/SSSR, arXiv 2407.13333) → `speech-foundation-models-hearing-impaired-2024.md`
- Binaural complex CNN+transformer SE (arXiv 2403.05393) → `multi-speaker-doa-binaural-ha-icassp-2026.md` covers the binaural-DOA neighbourhood

Worth watching:
- Auracast adoption (ReSound Nexia + Jabra Enhance Pro 20 active; broad ready-pending-firmware list) → multiple `auracast-*` sources
- OTC 2026 trend report (AI/BT/self-fit/rechargeable as table stakes) → `concepts/otc-hearing-aids.md` covers; bifurcation thread from 2026-05-28 still active

**Pages created (0). Sources created (0). Wiki pages updated (0).**

**Editorial framing:**
- Today's digest is the first run where **every covered item was already in the wiki via an upstream pipeline** (LinkedIn drafts, ad-hoc research, lint passes). This is a positive signal — the digest is no longer the primary source of fresh ingest because the parallel pipelines are catching items first. The digest's role is shifting from *ingest* to *retrieval-and-curation*: surfacing the day's important items from existing wiki state and routing them to the user's morning scan. Worth flagging in the next lint pass: is the digest worth running daily if it never sources new files, or should it switch to weekly trend-summary mode anchored on the synthesis pages?
- The Widex Allure AI dual-chip "Clarity Boost button" model is the cleanest current example of the user-controlled-effort-dosing thesis from the 2026-05-28 Claude Opus 4.8 entry — a *binary* version of the continuous slider that LLM frontier ships, deployed in a hearing aid 4 days later. The carry-forward flag from 2026-05-28 (watch for first OEM continuous slider) remains open; Widex's binary-button precedent is the asymptote not yet crossed.

**Pages touched this ingest: 1** (log appended only — no source or wiki page changes given full coverage).

---

## 2026-06-02 — LinkedIn Drafts Ingest

**Trigger:** Daily LinkedIn drafts pass (8:13 AM Zurich) — 2 posts drafted + posted to Discord channel `1492462147127742565`, emailed to user.

**Sources ingested (2):**
- `sources/breaking-the-pair-speaker-switching-arxiv-june-2026.md` — Nilabh & Sharma, "Breaking the Pair: Evaluating Dyadic Interaction via Speaker Switching," arXiv:2606.02185 (1 June 2026). Dyadic Distance Matrix + speaker-switch test as first methodologically clean diagnostic for interaction preservation as a separable evaluation axis. Key finding: discriminability of real-vs-switched DDMs is *higher* on read speech (LibriSpeech) than on naturalistic conversation (CANDOR) — the opposite of where hearing-aid wearers care about performance.
- `sources/mindvoice-non-invasive-neural-speech-arxiv-may-2026.md` — Bao, Zeng, Feng & Xue, "MindVoice: Reconstructing Intelligible Speech from Non-invasive Neural Signals with Pretrained Priors," arXiv:2605.31173 (29 May 2026). Dual-pathway disentanglement (semantic + acoustic) feeding a frozen speech generation model with in-context voice cloning. First non-invasive system to produce natural + intelligible output rather than spectral-similar-but-unintelligible.

**Pages created (2):**
- `wiki/concepts/dyadic-interaction-preservation.md` — Names the speaker-switch diagnostic + DDM as a fifth, orthogonal evaluation axis (alongside signal / lexical / neural-attention / effort). Representation-agnostic so composes cleanly with the foundation-model-fusion architectures of the May 27/28 update. Open questions on multi-party (>2 speaker) conversation, on-device computability, and asymmetric entrainment for HI listeners.
- `wiki/concepts/non-invasive-brain-to-speech.md` — The pretrained-prior paradigm as the modern alternative to classical EEG-stimulus-reconstruction AAD. Cross-references the November 2025 Nature *Scientific Reports* in-ear-EEG comparison (scalp 83.4% / around-ear 67.2% / in-ear 61.1% on 60s AAD windows) as the wearable-form-factor accuracy floor the architectural shift is designed to lift. Names the architecture shift from "decode attention → boost source" to "decode partial intent → query frozen foundation model → re-render," and the regulatory implication that frozen-backbone + small-learned-bridge maps cleanly onto FDA Predetermined Change Control Plans.

**Pages updated (3):**
- `wiki/concepts/auditory-attention-decoding.md` — Added `mindvoice-non-invasive-neural-speech-arxiv-may-2026.md` to sources, added `non-invasive-brain-to-speech.md` to related, added `brain-to-speech` tag, bumped updated to 2026-06-02.
- `wiki/concepts/communication-accessibility-metric.md` — Added `breaking-the-pair-speaker-switching-arxiv-june-2026.md` to sources, added `dyadic-interaction-preservation.md` to related, added `dyadic-interaction` tag, bumped updated to 2026-06-02. The speaker-switch test is the first quantitative diagnostic candidate for the construct Pichora-Fuller named at WCA Seoul.
- `wiki/syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md` — Added `breaking-the-pair-speaker-switching-arxiv-june-2026.md` to sources, added `dyadic-interaction-preservation.md` + `communication-accessibility-metric.md` to related, added `dyadic-interaction` tag, bumped updated to 2026-06-02. New "Update — 2 June 2026: Interaction Preservation Joins as a Fifth Axis" section describing the DDM + speaker-switch test, the read-vs-naturalistic inversion finding, the actionable pre/post-SE regression-test framing, and the representation-agnostic-composes-with-foundation-model-fusion note. New entry added to the Sources list.

**Pages added to index (2):** `concepts/dyadic-interaction-preservation.md`, `concepts/non-invasive-brain-to-speech.md`. Also refreshed the tags+date on the existing `auditory-attention-decoding.md` and `communication-accessibility-metric.md` rows.

**Editorial framing:**
- This ingest is the cleanest example yet of two papers from the same 5-day window reinforcing the same architectural recipe across two surfaces. MindVoice (EEG/MEG → speech) and the Nakazawa CPC3 fusion work (degraded HA audio → intelligibility) both reduce to "frozen pretrained backbone + small learned bridge." Whether the input is a noisy biosignal or noisy audio, the lever has stopped being "build a better custom encoder."
- The "Breaking the Pair" diagnostic gives the speech-enhancement-evaluation-stack-cracks synthesis its fifth axis exactly when the construct (communication accessibility) was named at the field's flagship congress (WCA Seoul, May 26). The pacing — construct named → quantitative diagnostic published — is six days.
- Carry-forward flag: the speaker-switch diagnostic begs a hearing-aid SE benchmark study where pre/post-SE DDM discriminability is tracked alongside HASPI/STOI/WER/AAD. None published as of today. First OEM or academic group to publish that benchmark sets the metric.

**Pages touched this ingest: 7** (2 sources, 2 wiki pages created, 3 wiki pages updated; plus log + index + LinkedIn memory).

---

## 2026-06-02 — Daily Hearing+AI Digest Ingest (afternoon pass)

**Trigger:** Daily hearing+AI digest email sent to door.punch_4o@icloud.com (subject: 🎧 Hearing + AI Daily Digest — 02 Jun 2026). Quiet Monday news cycle; two new ingestable items identified after wiki dedupe.

**Sources ingested (2):**
- `sources/veterans-hearing-aid-improvement-act-house-jun-2026.md` — Veterans Hearing Aid Improvement Act, House companion to S. 3739, introduced 1 June 2026 by Reps. Kevin Mullin (D-CA-15) and Keith Self (R-TX-03). Two-year VA pilot evaluating FDA-cleared OTC hearing aids for veterans with mild-to-moderate hearing loss, under VA clinical supervision. Bicameral and bipartisan; Senate sponsors Blackburn (R-TN) and Schiff (D-CA). Structurally creates a third OTC dispensing model — clinically-supervised OTC — distinct from both retail OTC and prescription.
- `sources/arxiv-2606-01905-electrolaryngeal-se-jun-2026.md` — "Advancing Electrolaryngeal Speech Enhancement Through Speech-Text Representation Learning" (arXiv:2606.01905, 2 Jun 2026). Seq2seq voice conversion with joint speech+text representation learning for laryngectomee speech reconstruction. Adjacent to mainstream HA SE, but adds to the same two-week architectural cluster (Nakazawa CPC3 fusion / MindVoice / Breaking the Pair / this paper) reinforcing the "frozen pretrained backbone + small learned bridge" recipe.

**Pages created (0).**

**Pages updated (3):**
- `wiki/syntheses/va-as-hearing-ai-dataset-may-2026.md` — Added `veterans-hearing-aid-improvement-act-house-jun-2026.md` to sources; added `../concepts/otc-hearing-aids.md` to related; added `otc-pilot, legislation` tags; bumped `updated` to 2026-06-02. New 5-paragraph "Update — June 2, 2026: A Legislative Third Tier (OTC Pilot)" section. Reframes the May 12–19 cluster from two-tier (premium / value prescription) to potentially three-tier (premium / value / supervised-OTC), and reframes the OEM list from 3 to potentially 8+ if Apple / Lexie / Eargo / Ceretone / Audien become pilot-eligible.
- `wiki/concepts/otc-hearing-aids.md` — Added `veterans-hearing-aid-improvement-act-house-jun-2026.md` to sources; added `../syntheses/va-as-hearing-ai-dataset-may-2026.md` to related; added `va, veterans, legislation, clinically-supervised-otc` tags; bumped `updated` to 2026-06-02. New "Clinically-Supervised OTC — VA Pilot Legislation (June 2026)" section with a three-row table contrasting retail-OTC vs. clinically-supervised OTC (proposed) vs. prescription on setting, supervision, and dataset quality. Source listed in Sources.
- `wiki/concepts/foundation-model-fusion-speech.md` — Added `arxiv-2606-01905-electrolaryngeal-se-jun-2026.md` to sources; added `non-invasive-brain-to-speech.md` to related; added `joint-modality, pathological-speech` tags; bumped `updated` to 2026-06-02. The EL paper extends the concept's coverage from "evaluation architecture" to also "generation architecture for pathological speech," which is a separate but compatible application of the same fusion recipe.

**Pages added to index (0).** No new wiki pages created; existing index rows for `va-as-hearing-ai-dataset-may-2026.md`, `otc-hearing-aids.md`, and `foundation-model-fusion-speech.md` already present (date refresh handled implicitly by frontmatter).

**Editorial framing:**
- The Veterans Hearing Aid Improvement Act is the first piece of *legislative* substrate the VA synthesis has had — every prior data point was an OEM commercial decision converging on a fixed VA channel structure. This bill, if enacted, *changes the channel structure itself.* The synthesis was previously a story of OEMs racing within fixed rails; it now also becomes a story of the rails being widened, with a new lane (clinically-supervised OTC) and a new addressable OEM list (Apple et al.) showing up at the same time. The "telemetry + outcome bridge" gap the synthesis identified gets materially easier to close if a pilot is *designed* to capture standardized outcomes from day one — much harder to retrofit into the live prescription contract.
- The electrolaryngeal SE paper is a low-bandwidth ingest in isolation, but as the fourth data point in a 5-day cluster around the "frozen backbone + small bridge" recipe, it confirms the pattern is not surface-specific. Inputs across the cluster: degraded audio (Nakazawa CPC3), naturalistic dyadic audio (Breaking the Pair), non-invasive biosignals (MindVoice), severely-degraded prosthetic audio (this paper). All converge on the same recipe. The Karpathy-style observation: the field's working architecture has visibly bifurcated from "encoder design" (the 2019–2024 era) to "fusion + bridge design" (the 2025–2026 era), and the proof is the cross-surface convergence within a single week.
- Carry-forward flags (new):
  - Watch House committee referral (VA vs. Energy & Commerce) for the Mullin/Self bill — referral determines whether it moves on a 2026 timeline or stalls into 2027.
  - Watch whether the Mullin/Self bill's eventual pilot RFP includes outcome-telemetry-return language — that would settle the open question on the VA synthesis page.
  - Watch for an OEM (Apple is the obvious candidate) publicly signaling intent to bid into the supervised-OTC pilot. First mover changes the bidding-set composition for everyone.

**Pages touched this ingest: 5** (2 sources created, 3 wiki pages updated; plus this log entry).

---

## 2026-06-03 — Ingest: DFC-IL (Voit & Doclo) + Whisper↔ECoG (Ciferri et al.)

**Sources added (2):**
- `sources/arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md` — "In-the-Loop Training of Deep Feedback Cancellation for Hearing Aids" (Voit & Doclo, arXiv:2606.03832, 2 Jun 2026). First demonstration that integrating the neural feedback canceller directly into the closed-loop optimisation during training holds stability at high amplification gains where open-loop-trained DFC begins to howl. Methodology argument with implications well beyond acoustic feedback.
- `sources/arxiv-2606-02305-whisper-ecog-ciferri-jun-2026.md` — "Mapping Whisper Representations to Human ECoG Responses with Interpretable Time-Resolved Neural Encoding" (Ciferri, Boccato, Olak, Ferrante, Toschi, arXiv:2606.02305, 1 Jun 2026, ICLR 2026 Workshop on Representational Alignment). Intermediate Whisper layers correlate most strongly with auditory cortex ECoG responses; attention analysis recovers anatomically coherent phoneme-category organization. Layer choice exposed as a free hyperparameter for downstream hearing-AI work.

**Pages created (3):**
- `wiki/concepts/training-deployment-distribution-gap.md` — New concept page generalising the DFC-IL methodology argument across hearing-aid ML sub-problems (SE, beamforming, scene classification, own-voice detection, noise reduction). Closes-the-gap toolkit: in-the-loop training, dynamics-level domain randomization, telemetry-grounded fine-tuning, curriculum, PCCPs.
- `wiki/concepts/acoustic-feedback-cancellation.md` — New concept page covering the canonical case for DFC-IL: closed-loop howl, classical adaptive filters, neural DFC architectures, the open-loop-vs-in-the-loop training gap, and product implications (profound-loss candidacy, open-fit RIC form factor, on-chip ordering).
- `wiki/concepts/brain-aligned-speech-foundation-models.md` — New concept page on intermediate-layer cortical alignment in speech foundation models. Connects Ciferri 2026 to existing AAD, non-invasive brain-to-speech, and cortical reorganization threads. Names the layer-selection hyperparameter as a free moat; raises open questions on layer drift across model versions, cross-subject generalization, and wearer-cortex reorganization.

**Pages updated (1):**
- `wiki/index.md` — Three new concept rows added (`training-deployment-distribution-gap.md`, `acoustic-feedback-cancellation.md`, `brain-aligned-speech-foundation-models.md`).

**Pages touched this ingest: 6** (2 sources, 3 concept pages, 1 index update; plus this log entry).

**Editorial framing:**
- DFC-IL is structurally a methodology paper masquerading as a feedback-cancellation paper. The interesting move is that it reframes "deploy a bigger neural canceller" as the wrong lever and "close the gap between training conditions and deployment conditions" as the right one. That argument generalises to speech enhancement (trained on iid noise, deployed into wearer scene), beamforming (trained on static geometry, deployed onto a moving head), scene classification (trained on balanced corpus, deployed into wearer's long-tail distribution), and own-voice detection (trained on studio speech, deployed into cough/chewing/motion). The on-device ML stack has been thinking architecturally; the lever DFC-IL exposes is dynamical.
- Ciferri et al. is the cleanest demonstration that Whisper specifically has a brain-aligned middle layer. The hearing-AI implication is that the field's reflex of tapping the last hidden state for downstream features is probably wrong for perceptual targets. The harder follow-on question is whether the brain-aligned layer is stable across model versions — when OpenAI ships Whisper v4 or v5, the cortex-correlated layer index could move, and OEMs adopting these models for fitting software or evaluation would need a layer-search protocol baked into every adoption.
- Carry-forward flags:
  - Track whether anyone publishes an in-the-loop training variant for speech enhancement or beamforming within the next 90 days — that would be the first generalization of the DFC-IL methodology beyond feedback cancellation.
  - Track Whisper v4/v5 release and whether anyone reproduces the Ciferri layer-alignment analysis on the new version.
  - Open question: what does the brain-aligned layer index look like for *hearing-impaired* cortex (vs the normal-hearing cohort in Ciferri's ECoG dataset)? Almost certainly different given the Becker 2026 cortical-reorganization finding, but no one has measured it.

## 2026-06-03 — Ingest: HearingTracker AI Hearing Aids vs. Background Noise (daily digest companion)

**Sources added (1):**
- `sources/hearingtracker-ai-hearing-aids-background-noise-jun-2026.md` — HearingTracker editorial/lab review (2 Jun 2026) concluding that dedicated AI co-processor devices (Phonak Sphere / DEEPSONIC and Widex Allure / Clarity Boost) deliver SNR-in-noise gains comparable to a remote microphone — the first non-CI on-aid alternative to that historical ceiling — at the cost of battery (~10–11 hr when AI block active), size, and premium pricing.

**Pages created (0).**

**Pages updated (2):**
- `wiki/entities/phonak.md` — Added new source to `sources:`; added `ws-audiology-signia.md` to `related:`; added `remote-mic-equivalent-snr` tag; bumped `updated` to 2026-06-03. New "HearingTracker Background-Noise Field Review (June 2, 2026)" section placing DEEPSONIC in the first independent-lab cohort to challenge the remote-mic SNR ceiling, with explicit battery/size/price trade-off list now suitable for patient counseling.
- `wiki/concepts/dnn-in-hearing-aids.md` — Added new source to `sources:`; bumped `updated` to 2026-06-03; appended sources-section bullet describing the field-level review.

**Pages added to index (0).** No new wiki pages; existing index rows already cover updated pages.

**Editorial framing:**
- This is the first source that frames "dedicated AI co-processor in a hearing aid" as a **product category** rather than a per-brand feature. Phonak DEEPSONIC and Widex Clarity Boost are now grouped as the two flagship members; the implicit prediction is that this category is what "AI hearing aid" will mean by the end of 2026 (anything without a dedicated co-processor falls below the SNR floor).
- The "remote-mic-equivalent SNR" framing is the most consequential. For two decades the remote microphone (Roger, Multi-Mic) defined the SNR ceiling for HI listeners. If lab measurements hold up under independent replication, the on-aid AI category collapses the remote-mic use case into the hearing aid itself — with downstream implications for the Roger / Phonak ecosystem, ALD reimbursement codes, and assistive listening venue infrastructure (Auracast intersects here).
- Pairs cleanly with the digest-day's other items: the Voit & Doclo DFC-IL paper (ingested earlier today) is the methodology-paper proof that the next big lever for on-aid AI is training-loop closure, not architecture; the HearingTracker review is the field-level proof that the **current** on-aid AI generation already pays off measurably for the dedicated-co-processor cohort.

**Carry-forward flags:**
- Track which independent lab published the SNR numbers — HearAdvisor is the most likely source. If HearAdvisor's full report appears, it becomes a primary source to ingest with explicit test conditions.
- Track whether Sonova / WSA publish their own controlled comparisons of DEEPSONIC vs. Clarity Boost on a common benchmark (matrix sentence in noise + reverb). Cross-OEM comparability is the obvious gap.
- Track when (not if) dedicated-AI-co-processor silicon migrates down into the mid-tier and OTC categories. The bifurcation thesis on the otc-hearing-aids concept page predicts 2027–2028; explicit silicon roadmap leaks would tighten this.

**Pages touched this ingest: 4** (1 source created, 2 wiki pages updated, plus this log entry).

---

## 2026-06-04 — LinkedIn Drafts Ingest

**Trigger:** Daily LinkedIn post generation; two arXiv papers submitted 4 Jun 2026.

**Sources created (2):**
- `sources/dal-differentiable-auditory-loop-google-june-2026.md` — Ballesta Rosen, Mikiel-Hunter, Maclaren, Collins, Lyon, Carlile, arXiv:2606.04103 (Google Research Australia + Macquarie University, 4 Jun 2026).
- `sources/fpga-sudormrf-feasibility-radboud-june-2026.md` — Olalere, Altin, van der Heijden, van Gerven, arXiv:2606.04221 (Radboud Donders + Columbia Zuckerman, 4 Jun 2026).

**Pages created (1):**
- `wiki/concepts/differentiable-cochlear-models.md` — new concept page for differentiable cochlear models as a loss-function substrate. Covers CARFAC + CARFAC-JAX, DAL as the first end-to-end framework, NAP/SAI loss primitives, three field implications (prescription → cost function, population priors as warm starts, strategic substrate ownership), open questions.

**Pages updated (3):**
- `wiki/entities/google-research.md` — added section 5 (Hearing-Aid R&D — Google Research Australia) covering DAL + CARFAC v2; reframes Google as substrate-provider for the perceptual loss function; added DAL source row; new related links + tags; bumped updated to 2026-06-04.
- `wiki/concepts/on-device-ml-hearing-aids.md` — added First Concrete Embedded-FPGA Benchmark (June 2026) subsection under Latency Constraints with the Olalere et al. numbers (9.7 ms denoising, 16.0 ms separation, 16-bit half-memory), the data-movement-not-compute headline, and the architectural implication favoring streaming-friendly architectures over U-Net-on-spectrograms; added FPGA source row; bumped updated to 2026-06-04.
- `wiki/index.md` — added differentiable-cochlear-models row to Concepts table; prepended new ingest summary to top.

**Underlying LinkedIn posts:**
1. Google Research Australia's Differentiable Auditory Loop (DAL) puts CARFAC inside the backprop graph — fitting target stops being a prescription (NAL-NL3, DSL v5) and becomes a per-wearer cost function in cochlear-neural-activity space; whoever owns the differentiable perceptual model owns the loss function the next decade of personalization will be optimized against. Google just open-sourced theirs.
2. First concrete on-chip DNN benchmark for hearing aids (Radboud + Columbia Zuckerman, Kria KV260): denoising clears the 10 ms clinical bar at 9.7 ms, speech separation does not at 16.0 ms, and data movement is the binding constraint — not compute. Architectural implication: streaming-friendly state-space / recurrent / single-pass causal transformers fit the actual silicon better than memory-hungry U-Net-on-spectrograms.

**Carry-forward flags:**
- Watch for OEM (Sonova / Demant / GN / Starkey / WSA) responses to Google open-sourcing the perceptual-loss substrate: do any of them fork CARFAC, license it, or publish a proprietary alternative?
- Watch for follow-up CPC / Clarity Prediction Challenge submissions that adopt DAL-style perceptual losses.
- Watch for FPGA benchmark replications across other embedded platforms (Synaptics Astra SR80, Aizip + commodity DSP, Qualcomm S5/S3) — if data movement is the bottleneck on Kria KV260, does it hold on the chips actually shipping in hearables?
- New `concepts/clinician-ai-consent-and-trust.md` page still waiting (carried from May 2026 logs) on a regulator statement / professional-body position / second on-record clinician quote.

**Pages touched this ingest: 6** (2 sources created, 1 wiki page created, 3 wiki pages updated, plus this log entry).

---

## 2026-06-04 — Daily Hearing+AI Digest Email Sent

**Trigger:** Daily hearing+AI digest email to door.punch_4o@icloud.com. Compiled during morning research pass and sent via gmail_send.py.

**Sources referenced in digest (all previously ingested — no new source files this run):**
- `sources/dal-differentiable-auditory-loop-google-june-2026.md` — headlined as Research Paper #1 (4 Jun 2026 arXiv).
- `sources/fpga-sudormrf-feasibility-radboud-june-2026.md` — headlined as Research Paper #2 (4 Jun 2026 arXiv).
- `sources/fortell-spatial-ai-ija-may-2026.md` — headlined as Research Paper #3 (RCT result, IJA 2026).
- `sources/phonak-ai-excellence-award-march-2026.md` — referenced under Industry News.
- `sources/starkey-omega-ai-big-ai-awards-2026.md` — referenced under Industry News.
- `sources/auracast-european-public-venue-rollout-2026.md` and the WWDC 2026 watch-item — referenced under Worth Watching.

**Sources created (0).** All material was already ingested.
**Pages created (0).**
**Pages updated (0).** Wiki pages affected by the underlying sources were updated at their original ingest dates; the digest is a downstream surfacing of existing knowledge, not a new claim that needs to be reflected back into concept/entity pages.

**Editorial framing of today's digest:**
- The two arXiv papers dated today (DAL, FPGA SuDoRM-RF++) define complementary frontiers — loss-function relocation into the cochlea, and silicon-side memory-bandwidth as the real latency bottleneck. The digest pairs them as the headline story.
- The Fortell IJA paper is included not as new news but as the field-level RCT proof that the on-aid AI category already delivers measurable wins against five flagship incumbents — anchoring the DAL/FPGA forward-looking story to a concrete current result.

**Carry-forward flags:**
- Apple WWDC 2026 next week — flagged in Worth Watching. If self-fitting envelope expands (currently mild-to-moderate only), ingest the keynote / FDA filing as a new source and update `entities/apple-hearing-features.md` and `concepts/otc-hearing-aids.md`.
- No additional pages touched in this ingest beyond this log entry.

**Pages touched this ingest: 1** (log entry only).

---

## 2026-06-05 — LinkedIn Drafts Ingest

**Trigger:** Two LinkedIn post drafts for 5 Jun 2026 → ingest researched sources into wiki.

**Underlying LinkedIn posts:**
- **Post 1** — HEAL 2026 Padua and the arxiv week that just shipped — clinical audiology and on-chip ML finally in the same room. Co-occurrence of HEAL 2026 (Padova, 4–6 Jun) with the June 1–4 arXiv wave (DAL / FPGA SE / DFC-IL / Whisper-ECoG) — common move across all four papers: drag the perceptual model inside the optimisation loop.
- **Post 2** — Cochlear Nucleus Nexa firmware-upgradeable implant as the first stress test of FDA's PCCP framework on a Class III implantable — and the data-science follow-on (cohort stationarity / allocation / plasticity costs).

**Sources created (2):**
- `sources/heal-2026-padova-june-4-6.md` — Conference (Padova Conference Centre, 4–6 Jun 2026). ~230 oral presentations, 100 posters, 5 rooms, 40+ countries. **Track-structure observation:** "AI and Data-Driven Approaches" and "Computational & Digital Health Approaches" elevated to first-class regular-program tracks (not special sessions). Cross-references the four June 1–4 arXiv papers (DAL 2606.04103, FPGA SE 2606.04221, DFC-IL 2606.03832, Whisper-ECoG 2606.02305).
- `sources/fda-pccp-final-guidance-december-2024.md` — FDA Final Guidance on Predetermined Change Control Plans for AI-enabled Device Software Functions (Dec 2024). Replaces April 2019 discussion paper, January 2021 Action Plan, April 2023 draft. Scope broadened from AI/ML SaMD to AI-DSF (incl. SiMD / implanted hardware). 1,350+ AI-enabled medical devices authorised by Q1 2026 (≈2× the 2022 count). PCCP = pre-specified Description of Modifications + Modification Protocol + Impact Assessment in the original marketing submission, allowing post-market changes without re-submission within the envelope. Operationalises TPLC framing. Open questions identified for hearing/CI: allocation, cohort stationarity, plasticity costs of updates, liability.

**Pages created (1):**
- `syntheses/clinical-ml-convergence-june-2026.md` — Synthesis: the structural observation that HEAL 2026's track structure (clinical audiology elevating two AI tracks to first-class) and the simultaneous arXiv eess.AS wave (DAL / FPGA SE / DFC-IL / Whisper-ECoG) execute *the same architectural move at the same time*: drag the perceptual / cortical / closed-loop model inside the optimisation loop so the gradient flows through it. Three enabling shifts named (differentiable cochlear models mature; foundation models for speech transferable to perceptual / cortical alignment; sub-10 ms on-chip latency floors). Competitive-moat shift table (before/after). Open question: which clinical outcome metric from HEAL Padova lands first in an arXiv loss-function definition in 2027 — concrete candidates named (FUEL-derived listening-effort score; audiovisual-intelligibility score; dyadic-interaction-preservation score; communication-accessibility composite).

**Pages updated (2):**
- `concepts/software-defined-medical-implants.md` — Added FDA PCCP final guidance to frontmatter sources. New section **"Three Data-Science Follow-On Questions (June 2026 Update)"** with the three named sub-problems from Post 2: (1) cohort stationarity breaks — five-year speech-in-noise outcomes become firmware-versioned multi-cohort analyses requiring version-stratified estimators; (2) the allocation problem — default rollout policy, reversibility, consent granularity, all currently underspecified; (3) plasticity cost of updates — auditory cortex has adapted to v1, v2 updates may carry re-adaptation costs the original trial protocol did not price; trial protocols and outcome metrics need a standard for measuring update-induced re-adaptation cost. Added allocation / cohort-stationarity / plasticity tags. Bumped updated to 2026-06-05.
- `wiki/index.md` — Added `clinical-ml-convergence-june-2026.md` row to the Syntheses table with 2026-06-05 stamp.

**Editorial framing:**
- The June 2026 convergence observation is the first synthesis in the wiki that names a *cross-disciplinary structural shift in real time*, anchored by a clinical-conference programme decision (HEAL track structure) co-occurring with a coherent arXiv wave (four papers, three institutions, one shared architectural move). The previous closest analog was the May 2026 SE evaluation-stack-cracks synthesis, which was an arXiv-only pattern; this one bridges the clinical-conference and arXiv timelines.
- The Nexa-vs-PCCP follow-on questions are the first wiki content that names cohort stationarity, allocation, and plasticity costs as *first-class data-science work* (not regulatory afterthought) for software-defined implants. Sets up the carry-forward concept page `concepts/firmware-versioned-cohort-analysis.md` if a third source surfaces a concrete cohort study or trial protocol on this construct.

**Carry-forward flags:**
- HEAL 2026 abstract book / proceedings — once released, ingest specific clinical metrics that map directly to recent ML loss-function design; expand the synthesis with concrete metric→loss mappings.
- WWDC 2026 keynote (8 Jun) — separately flagged in the prior 2026-06-04 digest log; still pending.
- Apple iOS 27 AirPods settings menu revamp surfacing hearing health — watch for separate update beyond hearing-aid-mode country expansion.
- First firmware-version-stratified outcomes paper from a Nexa cohort — triggers `concepts/firmware-versioned-cohort-analysis.md` page creation.

**Pages touched this ingest: 5** (2 sources created, 1 new synthesis page, 2 wiki pages updated, plus this log entry).

---

## 2026-06-07 — LinkedIn Drafts Ingest

**Trigger:** Two LinkedIn post drafts for 7 Jun 2026 → confirm sources are ingested and reflect new framings back into the wiki.

**Underlying LinkedIn posts:**
- **Post 1** — House companion to Veterans Hearing Aid Improvement Act writes the missing OTC-vs-clinician evaluation infrastructure into law. Constructive follow-up to May 19 Post 2 (VA OEM cluster lacks closed-loop telemetry-to-outcome bridge) — argues the federally-mandated interim+final reports + standardized VA outcome instruments (APHAB/COSI/HHIE-S/AzBio) are structurally a natural experiment with the modal contrast (self-fit vs clinician-fit) at population scale.
- **Post 2** — T-PAMI acceptance of DBHN-Net (arXiv:2606.05911, Fan et al., 5 Jun 2026) — dual-branch ANN+SNN with 7.5x average compute reduction. Constructive follow-up to June 4 Post 2 (memory bandwidth as binding constraint): SNNs are event-driven and temporally sparse and are exactly the architectural lever that addresses that bottleneck. Argument: on-chip compute frontier has just split into four lanes — dense ANN, compressed ANN, compute-in-memory, hybrid ANN+SNN — and SNN-friendly perceptual loss is the unbuilt evaluation piece.

**Sources created (0).** Both source files already ingested on prior cycles:
- `sources/veterans-hearing-aid-improvement-act-house-jun-2026.md` (ingested 2026-06-02).
- `sources/arxiv-2606-05911-dbhn-net-snn-ann-fan-jun-2026.md` (ingested 2026-06-05).

**Pages created (0).** Both target wiki pages already exist and reference the underlying sources:
- `syntheses/va-as-hearing-ai-dataset-may-2026.md` already contains the bill detail and the OTC-pilot framing (June 2 update).
- `concepts/speech-enhancement-neural-networks.md` already references DBHN-Net in `last_change` frontmatter.

**Pages updated (0).** Today's LinkedIn framings are downstream surfacings of claims already on the relevant pages, not new factual content that requires reflection back into concept/entity pages. The two new editorial angles introduced today (federal-reporting requirement as natural-experiment infrastructure; SNN+ANN hybrid as the fourth compute-frontier lane) are captured in the post-history memory file and in this log entry.

**Editorial framing of today's drafts:**
- Post 1 is the first wiki-anchored post that explicitly frames the federal interim+final reporting requirement as structured-outcome-publication infrastructure — the closed-loop bridge the May 19 VA-as-dataset synthesis named as missing. Future ingest of the actual bill text (once H.R. number assigned) should add the reporting-requirement specifics back into the synthesis page.
- Post 2 is the first wiki-anchored post to position hybrid ANN+SNN as a distinct compute-frontier lane parallel to TurboQuant-class compressed ANN and CIM. Future ingest of SNN-friendly perceptual-loss papers should trigger a new concept page `concepts/snn-friendly-perceptual-losses.md` and a backlink from `concepts/speech-enhancement-neural-networks.md`.

**Carry-forward flags:**
- House H.R. number for the Veterans Hearing Aid Improvement Act companion bill — update `sources/veterans-hearing-aid-improvement-act-house-jun-2026.md` once assigned.
- VA RFP language for the OTC pilot — watch for whether outcome-data-telemetry return is specified as vendor requirement. Triggers update to `syntheses/va-as-hearing-ai-dataset-may-2026.md` and `concepts/closed-loop-data-flywheel.md`.
- First SNN-friendly perceptual-loss paper for hearing-aid SE — triggers creation of `concepts/snn-friendly-perceptual-losses.md`.
- WWDC 2026 keynote (8 Jun) — still pending; hearing-health surface area expected.

**Pages touched this ingest: 1** (log entry only — sources and wiki pages already ingested on prior cycles).

---

## 2026-06-08 — LinkedIn Drafts Ingest

**Trigger:** Two LinkedIn post drafts for 8 Jun 2026 → reflect new framings back into the wiki.

**Underlying LinkedIn posts:**
- **Post 1** — SB-RF (arXiv:2606.05575, Lu, Lv, Hu, Xu, 4 Jun 2026): one-step generative SE via Schrödinger Bridge + Rectified Flow + entropy-regularized optimal transport. Frame: 4 years of generative-SE arxiv leaderboard work has been mathematically out of reach for hearing aids (multi-step diffusion ≠ ~1 ms algorithmic latency). One-step generative collapses that. Cross-references DBHN-Net (5 Jun T-PAMI) and Olalere et al. FPGA memory-bandwidth (4 Jun). Unbuilt piece: VoiceBank-DEMAND is anechoic; the team that ports SB-RF to HASPI / CEC3-style listener-perception loss owns the next round.
- **Post 2** — Age-Aware Adapter Tuning for Children's ASR (arXiv:2606.05440, Jialu Li, 3 Jun 2026): per-age-band parameter-efficient adapter modules with router-based inference selection. WER 12.6%→12.3% overall, macro 18.4%→17.6%; predicted-age routing tracks ground-truth; hard routing > FiLM. Frame: the 2026 hearing-aid AI conversation has been adult-speech-in-noise. Pediatric front-end is a different physics problem (smaller ear canals, evolving pinna, faster F0, developing phonology). Parameter-efficient adapters are the tractable ML hook AAA/ASHA/NAL pediatric-fitting guidance has lacked. Unbuilt piece: pediatric-HA-specific training corpus.

**Sources created (1):**
- `sources/arxiv-2606-05440-age-aware-adapter-children-asr-jun-2026.md` — Li, "Age-Aware Adapter Tuning for Children's Speech Recognition," arXiv:2606.05440 (3 Jun 2026). Per-age-band adapter modules; ground-truth age routing 12.6%→12.3% WER overall, 18.4%→17.6% macro; predicted-age routing tracks ground-truth; hard age routing > FiLM. First published parameter-efficient per-age-band adapter approach for child ASR.

**Sources already ingested on prior cycles:**
- `sources/arxiv-2606-05575-sbrf-schrodinger-bridge-jun-2026.md` (ingested 2026-06-05) — already cited from `concepts/probabilistic-generative-models-hearing-ai.md`.

**Pages created (0).** Both new framings extend existing concept pages.

**Pages updated (2):**
- `concepts/cross-lifespan-speech-models.md` — added arxiv-2606-05440 to frontmatter sources list, added a "first published instance" paragraph under the "third axis of training-data moat" section explicitly attributing per-age adapter tuning to Jialu Li (3 Jun 2026) with the WER deltas and the hard-routing > FiLM finding. Added new source row in Sources section. Bumped `updated` to 2026-06-08.
- `wiki/index.md` — bumped `cross-lifespan-speech-models` row date to 2026-06-08 and added `age-conditioned-adapters` tag.

**Editorial framing of today's drafts:**
- Post 1 reflects out from the already-ingested SB-RF source. The new framing this post adds — that 2026 is the *year* the generative-SE family finally competes on hearing-aid silicon, set against DBHN-Net (5 Jun) and the Radboud-Columbia FPGA benchmark (4 Jun) — belongs in a synthesis page (`syntheses/clinical-ml-convergence-june-2026.md` is the existing home). Carry-forward flag for next ingest cycle to extend that synthesis with the SB-RF + one-step-generative narrative.
- Post 2 lands the first concrete published method on top of the cross-lifespan-speech-models page's "age-conditioned adapter heads" axis. The previous framing identified the axis but had no published instance; this paper is that instance.

**Carry-forward flags:**
- Extend `syntheses/clinical-ml-convergence-june-2026.md` (or successor) to add SB-RF as the fourth "perceptual model inside the optimisation loop" data point alongside DAL, DFC-IL, Whisper-ECoG.
- Watch for a follow-up SB-RF paper applying the framework to hearing-impaired-listener perceptual losses (HASPI / CEC3). Would trigger creation of `concepts/optimal-transport-perceptual-losses.md`.
- Watch for an age-aware-adapter paper targeted at hearing-impaired pediatric ASR (the obvious next step) — would trigger a new source file and an update to `concepts/cross-lifespan-speech-models.md` to add a pediatric-HA-specific corpus subsection.

**Pages touched this ingest: 3** (1 new source, 2 page edits, +1 log entry).

---

## 2026-06-08 — Daily Hearing+AI Digest Ingest

**Trigger:** Daily hearing+AI digest email sent to door.punch_4o@icloud.com on 8 Jun 2026 — ingest underlying sources into the wiki.

**Digest items covered:**
- **arXiv:2606.02913** — Saha Shetu, Habets, Brendel (Fraunhofer IIS / IAL Erlangen) — controlled head-to-head between generative (diffusion-style) and discriminative SE; discriminative wins on stationary intrusive noise, generative wins on non-stationary noise and unseen reverberation but at the cost of content-warping artifacts.
- **Auditdata US audiologist time-crisis survey** (4 Jun 2026) — first US-wide quantitative instrument on administrative-time-loss as the workforce-shortage mechanism; explicitly names TPA portals (TruHearing, UHC Hearing) and prior-auth workflows; aggregated benchmark to publish later in 2026.
- **Apple pre-WWDC 2026 accessibility drop** (21 May 2026) — MFi hearing aid reliable cross-device handoff + Name Recognition (deaf/HoH ambient name-spotter, 50+ languages, on-device).
- WWDC 2026 keynote watchlist (8 Jun 2026, 10:00 PT) — pending; carry-forward flag.
- Voit & Doclo arXiv:2606.03832 — already in wiki (last cycle); recapped in digest only.
- Olalere et al. arXiv:2606.04221 FPGA SE benchmark — already in wiki; cited as quick stat.

**Sources created (3):**
- `sources/arxiv-2606-02913-generative-vs-discriminative-se-jun-2026.md` — Saha Shetu, Habets, Brendel (Fraunhofer IIS), arXiv:2606.02913, 3 Jun 2026. First controlled head-to-head generative-vs-discriminative SE benchmark; the *content-fidelity* gate alongside SB-RF's *latency* gate.
- `sources/auditdata-audiologist-time-survey-jun-2026.md` — Hearing Health & Technology Matters, 4 Jun 2026. First quantitative instrument on the administrative-burden mechanism behind the US audiologist shortage.
- `sources/apple-pre-wwdc-accessibility-may-2026.md` — Apple Newsroom, 21 May 2026. MFi cross-device handoff fix + Name Recognition for deaf/HoH users.

**Pages updated (3):**
- `wiki/concepts/probabilistic-generative-models-hearing-ai.md` — added new section "Where Generative vs Discriminative Sit Today (Fraunhofer IIS, Jun 2026)" framing the Fraunhofer paper as the *content-fidelity* gate complementary to SB-RF's *latency* gate; called out that the Fraunhofer paper benchmarks diffusion-style, not factor-graph, generative SE — head-to-head for the latter remains open. Added source to frontmatter. Added SB-RF and Fraunhofer source rows to Sources section (and corrected source-path depth from `../sources/` to `../../sources/`). Bumped `updated` to 2026-06-08.
- `wiki/concepts/audiologist-workforce-shortage.md` — added subsection "7. The Auditdata Time-Crisis Survey — First Quantitative Admin-Burden Instrument (Jun 2026)" explicitly naming TPA portals (TruHearing, UHC Hearing) and prior-auth as the survey's named drains; positioned as the *mechanism* layer beneath ASHA/BLS *headcount* and ScienceDirect *geographic* layers. Added source to frontmatter and Sources section. Bumped `updated` to 2026-06-08.
- `wiki/entities/apple-hearing-features.md` — added new section "Pre-WWDC 2026 Accessibility Drop (21 May 2026)" covering MFi cross-device handoff fix and Name Recognition; flagged WWDC 2026 keynote watchlist (8 Jun 2026, 10:00 PT). Added source to frontmatter and Sources section. Bumped `updated` to 2026-06-08.

**Index updates:**
- `wiki/index.md` — bumped dates on all three updated pages to 2026-06-08; added tags (`admin-burden`, `tpa-portals` on workforce; `ood-generalization` on probabilistic-generative; `mfi-handoff`, `name-recognition` on Apple).

**Carry-forward flags:**
- **WWDC 2026 keynote** (8 Jun 2026, 10:00 PT) — watch live for AirPods Pro 3 firmware updates tied to iOS 27, Conversation Boost / Media Assist upgrades, AirPods Pro w/ cameras preview. Any HA-relevant announcement triggers a same-day update to `entities/apple-hearing-features.md`.
- **Auditdata aggregated benchmark publication** — date TBD, expected later in 2026. Will be a primary citable data point for back-office-AI-leverage thesis.
- **Artifact-rate metric for SE** — a paper that ships an explicit artifact-rate metric alongside PESQ / HASPI / CEC3 would close the loop on the Fraunhofer comparison; would trigger creation of `concepts/artifact-rate-evaluation-se.md`.
- **Hybrid generative/discriminative architecture** — generative-when-OOD, discriminative-when-in-distribution, decided by on-device scene classifier. Obvious next product move; first published paper triggers source + new comparison page.
- **Probabilistic-generative vs diffusion-generative head-to-head** — Fraunhofer paper covers diffusion-style only. A controlled benchmark of factor-graph probabilistic generative (AIDA-2 family) against diffusion generative on the same OOD axes would resolve whether the explicit-likelihood structure is genuinely more artifact-resistant by construction.

**Pages touched this ingest: 7** (3 new sources, 3 page edits, 1 index update, +1 log entry).

---

## 2026-06-09 — LinkedIn drafts ingest

**Mode:** LinkedIn drafts ingest (daily). Two sources, both single-event hooks paired with structural framing.

### Sources added (2)
1. **`widex-allure-ai-launch-june-2026.md`** — Widex Allure AI RIC live in five markets June 1, 2026; follow-on industry coverage adds the technical disclosure that the AI co-processor runs a **third-generation "Linear Recurrent Neural Network" (L-RNN)** specifically built for audio. Quoted Widex AI team rationale: "It works with the temporal aspect of sound and can keep memory of what happened before. That allows balancing noise reduction, power consumption, and sound quality in a way that other AI architectures are not able to do." Full US launch Nov 1, 2026.
2. **`biear-meng-2026-arxiv.md`** — Meng, Ambikairajah, Sethu, Zhang, Li (UNSW Sydney + Haizhou Li, NUS / CUHK Shenzhen); arXiv:2606.06795, posted June 5, 2026; accepted INTERSPEECH 2026. **BiEAR** — binaural auditory front-end with neural controller adaptively adjusting filterbank frequency selectivity at inference, inspired by the medial olivocochlear (MOC) reflex. Bilateral feedback controllers driven by per-subband sound pressure levels. End-to-end learning from multi-speaker localisation + distance estimation losses. Outperforms fixed binaural front-ends with robustness to unseen rooms / speakers.

### Pages created (1)
- **`concepts/efferent-moc-feedback-hearing-ai.md`** — New concept page for the MOC / efferent feedback class as a hearing-AI primitive. Defines the biological MOC reflex (brainstem → outer hair cell gain modulation in response to scene), reviews its established anti-masking / selective-attention / protective-gain functions, names the gap in conventional binaural HA front-ends (fixed filterbank, fixed gain map, runtime adaptation only in the back-end). Documents BiEAR as the reference implementation. Includes an afferent/efferent pair table — DAL (June 4) models the forward cochlear path; BiEAR (June 5) models the descending path — making the case that 2026 is the year the cochlear loop becomes a first-class ML object instead of a fixed preprocessing block. Implications section: filterbank as first-class adaptive object, second axis of personalization beyond the audiogram-shaped insertion gain, scene-conditioning at the source moving back-end work upstream, bridge to AAD (top-down read vs structural mechanism). Open questions on biological fidelity of the learned controller, transfer to hearing-impaired listeners (whose MOC function is itself impaired), porting to HASPI/STOI/CEC3 speech-intelligibility losses, and hardware translation cost.

### Pages updated (2)
- **`concepts/differentiable-cochlear-models.md`** — Added BiEAR to frontmatter sources + `biear-meng-2026-arxiv.md` reference; added `efferent-moc-feedback-hearing-ai.md` to related; new tags `afferent`, `efferent-pair`. New subsection **"The Afferent / Efferent Pair (Added 2026-06-09)"** documenting that DAL models afferent and BiEAR models efferent, posted within 24 hours of each other, and together operationalise the cochlear loop as a first-class ML object. Updated 2026-06-09.
- **`concepts/user-controlled-on-demand-ai-hearing-aids.md`** — Added `widex-allure-ai-launch-june-2026.md` to frontmatter sources. Updated Reference Implementation section to record the June 1 five-market launch as actually executed (was previously framed as scheduled-launch), with full US still on November 1 trajectory. Added the **L-RNN** technical disclosure to the on-demand-path description. New subsection **"Why the L-RNN choice matters"** — maps L-RNN to the State Space Model family (S4, Mamba, RWKV-7, Hyena) the audio ML community has been converging on for chip-friendly streaming; cross-references the June 4 Olalere FPGA finding (memory bandwidth as binding on-chip constraint — exactly the constraint SSM-family architectures are designed to relax). New tags `linear-recurrent-neural-network`, `l-rnn`, `state-space-models`. Updated 2026-06-09.

### Index update
- Added `efferent-moc-feedback-hearing-ai` row to Concepts table.
- Updated `user-controlled-on-demand-ai-hearing-aids` row tags + date.
- Updated `differentiable-cochlear-models` row tags + date.
- New top-of-index summary entry.

### Underlying LinkedIn posts
1. **Widex Allure AI RIC — opt-in AI is a labeled-dataset architecture, not just a marketing position.** Every press of the Clarity Boost button is a labeled positive ("this listener, this scene, perceived enough difficulty to ask for help"); every release is a labeled negative. Across millions of wearer-hours that's a contextual-bandit dataset most R&D teams would pay to construct. The L-RNN architecture choice puts WSA in the same on-chip-streaming-audio-via-SSMs camp as the rest of the 2026 chip-level audio ML field, not an idiosyncratic Widex bet.
2. **BiEAR (arXiv:2606.06795) — efferent MOC feedback as the missing axis in binaural hearing AI.** UNSW Sydney + NUS team put a neural controller over a binaural auditory filterbank that adjusts frequency selectivity at inference, learned end-to-end from downstream localisation losses. Paired with Google's DAL (afferent / forward cochlear model) the cochlear loop — forward and back — is now a first-class ML object. For hearing AI specifically: the audiogram-shaped insertion gain has been a one-shot person-level parameter for forty years; efferent gain control is the second axis — moment-by-moment, scene-conditioned.

### Carry-forward flags
- **L-RNN architecture detail.** Widex did not disclose the specific L-RNN variant (S4-style? Mamba-derived? proprietary?). Worth watching next disclosure cycle.
- **Real-world Clarity Boost engagement rates.** From June 1 onward in the five launch markets, real-world button-press telemetry distributions are testable in principle. Whether WSA publishes any aggregated data is the open question.
- **BiEAR speech-in-noise port.** BiEAR's losses are localisation and distance estimation, not HASPI/STOI/CEC3 intelligibility. The HA-relevant SI port is unbuilt — the team that ships it owns the next round.
- **Cross-trial validation of the MOC story.** Whether the BiEAR-learned controller actually resembles biological MOC policy is an interesting downstream analysis the paper does not perform.

**Pages touched this ingest: 6** (2 new sources, 1 new concept page, 2 page updates, 1 index update, +1 log entry).

---

## Ingest — 2026-06-09 (Daily Digest 09 Jun 2026)

**Source of operation:** Daily hearing+AI digest email compiled and sent to door.punch_4o@icloud.com.

### New source files
- **`sources/elehear-delight-cic-otc-ces-2026.md`** — Elehear Delight, first AI CIC OTC hearing aid; launched at CES 2026 (Jan 13). $299 pre-order, VocClear AI engine, on-device 20-language translation, IP67, BT 5.3, ≤45 dB amplification.
- **`sources/hearing-ai-digest-2026-06-09.md`** — Internal archive of today's digest delivery (10 items: 3 papers, 4 industry, 2 AI/ML, 2 worth-watching; 9 already in wiki, 1 net-new ingest).

### Wiki page updates
- **`wiki/concepts/otc-hearing-aids.md`** — Added `elehear-delight-cic-otc-ces-2026.md` to frontmatter sources; `updated:` bumped to 2026-06-09. New subsection **"CIC Form Factor Enters OTC — Elehear Delight (CES 2026)"** documenting that CIC is materially new to OTC, with a spec table and three "why it matters" hooks (form-factor as third axis beyond personalization/simplicity; translation as wedge feature; sub-$300 collapses the discretion premium prescription CIC has historically held).

### Coverage map (10 digest items → wiki state)
| Item | Wiki coverage |
|------|---------------|
| DBHN-Net (arXiv:2606.05911) | already: `arxiv-2606-05911-dbhn-net-snn-ann-fan-jun-2026.md` |
| DAL Differentiable Auditory Loop | already: `dal-differentiable-auditory-loop-google-june-2026.md` |
| Northwestern CI language prediction | already: `ai-cochlear-implant-language-prediction-2025.md` |
| Phonak AI Excellence Award | already: `phonak-ai-excellence-award-march-2026.md` |
| Sonova ⇒ divest Sennheiser Consumer | already: `sonova-sennheiser-consumer-divestiture-may-2026.md` |
| Elehear Delight CIC OTC | **NEW**: `elehear-delight-cic-otc-ces-2026.md` |
| Apple AirPods Hearing Aid 100+ countries | already: `airpods-hearing-aid-country-expansion-may-2026.md` |
| SNN+ANN hybrids / TinyML survey | folded into DBHN-Net citation |
| Mamba / SSM in audio | already: `mamba-ssm-audio-traction-2026.md` |
| Auracast venue rollout | already: `auracast-uk-live-theaters-april-2026.md` |
| AAA 2026 audiologist-supply panel | already: `aaa-2026-leadership-panel-may.md` |

### Editorial notes
Quiet news cycle Monday — most of today's items were extensions or reaffirmations of existing wiki content. The single net-new source (Elehear Delight) opens up a new dimension (form factor) in the OTC bifurcation thread that has otherwise been about personalization-vs-simplicity. Deliberately holding back on WWDC 2026 follow-up coverage — iOS 27 betas haven't landed yet, will pick up tomorrow.

**Pages touched this ingest: 4** (2 new sources, 1 page update, +1 log entry).

---

## Ingest — 2026-06-10 (LinkedIn drafts ingest)

**Source of operation:** Daily LinkedIn post drafts emailed to door.punch_4o@icloud.com and posted to Discord.

### New source files
- **`sources/apple-wwdc-2026-airpods-custom-eq-jun-2026.md`** — Apple WWDC 2026 keynote (Mon 8 Jun 2026). 3-band Custom EQ for AirPods in iOS 27 (Bass / Mids / Treble), live waveform preview, H2-chip devices only (AirPods 4 H2, Pro 3, Max 2). First user-controllable EQ in the AirPods line since 2016. Explicitly NOT audiogram-driven, structurally separate from FDA-cleared Hearing Aid Mode. AirPods settings reorganized to surface Spatial Audio / Hearing Health / Adaptive at top level. AirPods Pro 3 GymKit heart-rate sync co-announced.
- **`sources/arxiv-2606-09557-rir-encoder-dereverb-khanagha-gerkmann-jun-2026.md`** — Khanagha & Gerkmann, U Hamburg Signal Processing Group, arXiv:2606.09557 (8 Jun 2026, accepted Interspeech 2026). Probes both diffusion-based and discriminative U-Net dereverberation networks; finds deeper layers implicitly encode RIR embeddings; explicit conditioning via contrastive learning yields faster convergence, better dereverb, and significantly fewer reverse diffusion steps. Reframes 30 years of blind dereverberation as a misnomer — the room was always being measured.

### Wiki page updates
- **NEW `wiki/concepts/room-aware-dereverberation.md`** — Concept page defining the architectural pattern of making room characteristics a first-class object in the on-chip pipeline. Sections: why it matters (top-3 wearer complaint), the Khanagha & Gerkmann pivot, on-chip implications (shared room representation across SE / scene classification / beamforming / own-voice detection), frequent-room prior with per-wearer RIR library, complementary-to-SB-RF axis table, benchmark gap (HASPI/STOI/CPC don't score RIR-awareness — Clarity 2027 candidate).
- **`wiki/concepts/speech-enhancement-neural-networks.md`** — Added Khanagha & Gerkmann source to frontmatter; added `room-aware-dereverberation.md` to related; new "Implicit Room-Impulse-Response Encoders (Khanagha & Gerkmann, Jun 2026)" section with implicit-RIR finding, contrastive-learning conditioning, on-chip implications, SB-RF complementary-axis table, and benchmark gap; new tags `rir-encoder`, `room-aware-se`, `implicit-representations`; `updated:` bumped to 2026-06-10.
- **`wiki/entities/apple-hearing-features.md`** — Added Apple WWDC source to frontmatter; new "WWDC 2026 — Custom EQ + AirPods reorganization (Jun 8, 2026)" section covering the 3-band EQ + live-preview UI + H2-only device support + the explicit NOT-audiogram-driven framing + AirPods settings reorganization + AirPods Pro 3 GymKit heart-rate sync + the why-it-matters-for-hearing-AI framing on consumer EQ as the next-decade UX baseline against clinical fitting cycle; updated Software Requirements to include iOS 27 for Custom EQ; added `closed-loop-data-flywheel.md` + `hearing-aid-prescription-formulas.md` to related; new tags `ios27`, `custom-eq`, `wwdc-2026`; `updated:` bumped to 2026-06-10.
- **`wiki/concepts/hearing-aid-prescription-formulas.md`** — Added Apple WWDC source to frontmatter; added `apple-hearing-features.md` to related; new "Consumer-Side Counterpoint — Apple Custom EQ (WWDC 2026)" section explicitly contrasting Apple's 3-band consumer tone control with NAL-NL3 / DSL v5 multi-band gain curves (no audiogram input, no real-ear verification, no compression ratio) but argues the consumer-side UX baseline just shifted and the 2030 fitting model is more likely audiogram-warm-start + continuous user adjustment than prescription-locked-at-fitting; new tags `consumer-eq`, `airpods`, `custom-eq`; `updated:` bumped to 2026-06-10.
- **`wiki/index.md`** — Added new top-of-file ingest entry with full descriptions of both sources and pages touched; added `room-aware-dereverberation` row to Concepts table.

### Underlying LinkedIn posts
1. **Apple ships 3-band Custom EQ to AirPods at WWDC 2026 — the audiogram-shaped sound personalization primitive just went mass-market.** Apple announced a 3-band Custom EQ for AirPods in iOS 27 with live waveform preview, and the hearing-aid field has been doing this same primitive — band-gain shaping — since around 1985 as the most basic layer of every NAL-NL3 / DSL v5 prescription. The difference is who holds the slider (audiologist vs ~600M AirPods users). The wearer who tries AirPods first will not accept a 6-week clinical fitting cycle to update a curve they could drag in 30 seconds. Fitting UX is the next competitive axis, not chip TOPS. The 2030 fitting model is "audiogram as warm start, continuous user adjustment in real listening scenarios as the gradient."
2. **Khanagha & Gerkmann arXiv:2606.09557 — your dereverberation U-Net is secretly an RIR encoder.** U Hamburg probes both diffusion-based and discriminative U-Net dereverb models and finds that deeper layers implicitly encode RIR embeddings. Explicit contrastive RIR conditioning yields faster convergence + fewer diffusion steps. Reframes 30 years of blind dereverberation — the network was measuring the room all along. Pairs with SB-RF (June 4) along a separable axis — better ODE vs better conditioning, complementary not competing. Frequent-room prior + per-wearer RIR library + room-conditioned dereverb is structurally cheap and clinically meaningful, absent from every product on the market.

### Editorial notes
- Two distinct angles, both anchored to news posted within the last 48 hours (WWDC June 8, arXiv June 8). Wiki's WWDC 2026 hold (from June 9 log) is now released — Custom EQ is the first concrete artifact worth ingesting.
- Both posts reinforce the same meta-pattern from earlier June: stop ignoring the part you used to factor out. DAL (forward cochlea), BiEAR (efferent cochlear control), Whisper-ECoG (brain alignment as a layer hyperparameter), and now RIR-encoder (the room) — all four say "the silent variable is the one to expose." Synthesis candidate forming.

**Pages touched this ingest: 7** (2 new sources, 1 new concept page, 3 page updates, 1 index update, +1 log entry).

---

## Ingest — 2026-06-10 (Daily hearing+AI digest ingest)

**Source of operation:** Daily hearing+AI digest email sent to door.punch_4o@icloud.com.

### Coverage map (today's digest items → wiki state)
| Item | Wiki coverage |
|------|---------------|
| DBHN-Net (arXiv:2606.05911, 4 Jun) | already: `arxiv-2606-05911-dbhn-net-snn-ann-fan-jun-2026.md` |
| FPGA SuDoRM-RF++ feasibility (arXiv:2606.04221, 2 Jun) | already: `fpga-sudormrf-feasibility-radboud-june-2026.md` |
| HLAA 2026 Convention opens today | **NEW**: `hlaa-2026-convention-opens-june-2026.md` |
| Veterans Hearing Aid Improvement Act (House) | already: `veterans-hearing-aid-improvement-act-house-jun-2026.md` |
| BIHIMA Q1 2026 UK market | already: `bihima-q1-2026-uk-sales-jun-2026.md` |
| Phonak Red Dot / iF / AI Excellence awards | already: `phonak-virto-r-infinio-red-dot-april-2026.md`, `phonak-infinio-if-design-award-2026.md`, `phonak-ai-excellence-award-march-2026.md` |
| Sonova Sennheiser divestiture | already: `sonova-sennheiser-consumer-divestiture-may-2026.md` |
| Microsoft Edge 148 on-device Web Speech API | **NEW**: `microsoft-edge-148-on-device-speech-api-june-2026.md` |
| Synaptics Astra SR80 always-on edge AI audio MCU | **NEW**: `synaptics-astra-sr80-edge-ai-audio-may-2026.md` |
| Frontiers in Dementia review (May 2026) | **NEW**: `frontiers-dementia-hearing-loss-review-2026.md` |
| Auracast venue rollout | already: `auracast-uk-live-theaters-april-2026.md` + others |
| AirPods Hearing Aid 100+ countries | already: `airpods-hearing-aid-country-expansion-may-2026.md` |

### New source files
- **`sources/hlaa-2026-convention-opens-june-2026.md`** — HLAA 41st annual convention opens today (10-12 Jun 2026, Galt House, Louisville). Friday Research Symposium "The AI Revolution in Hearing Health: Smarter Tech, Greater Access" (12 Jun, 10am CT) flagged as the temperature read for what the consumer-advocacy side is willing to call AI vs. hype. Every meeting room captioned + hearing-looped. Endorses Veterans Hearing Aid Improvement Act.
- **`sources/microsoft-edge-148-on-device-speech-api-june-2026.md`** — Microsoft Edge 148 (announced at Build 2026, 2 Jun) ships experimental on-device Web Speech API + on-device Translator + Language Detector APIs. Removes the 200-800ms cloud STT round-trip and most HIPAA/GDPR friction from browser-based teleaudiology portals. Structural signal: browser vendors are normalizing on-device ASR as a baseline web capability.
- **`sources/synaptics-astra-sr80-edge-ai-audio-may-2026.md`** — Synaptics announced the Astra SR80 MCU family (May 2026), positioned as the new baseline category for "always-on edge AI audio" — single-chip integration of always-on scene detection, on-device NN audio inference, and high-fidelity I/O. Not a hearing-aid SoC, but the silicon class hearables and entry-level OTC HAs are migrating to; pressures OEM main-SoC roadmaps from below.
- **`sources/frontiers-dementia-hearing-loss-review-2026.md`** — Multi-author Frontiers in Dementia review (10.3389/frdem.2026.1736003) consolidating the hearing-loss → cognitive-decline literature. Two operational findings: (1) intervention reduces dementia incidence but not memory-test scores → wrong outcome variable, not weak treatment (consistent with subjective-objective hearing gap thesis); (2) calls for biomarkers (e.g., FSR ratio) to stratify risk → opens an ML-shaped lane for digital phenotyping via hearing-aid telemetry. Will be cited at HLAA AI Symposium Friday.

### Wiki page updates
- **`wiki/concepts/hearing-loss-dementia-link.md`** — Added `frontiers-dementia-hearing-loss-review-2026.md` to frontmatter sources; `updated:` bumped to 2026-06-10; new subsection **"Frontiers in Dementia Review (May 2026) — Mechanism Still Open"** documenting the "intervention reduces dementia but not memory tests → wrong outcome variable" pattern + the call for FSR-style MRI/EEG biomarkers as the ML-shaped opening for digital phenotyping.
- **`wiki/concepts/teleaudiology.md`** — Added Microsoft Edge source to frontmatter; `updated:` bumped to 2026-06-10; new section **"On-Device Browser ASR Removes a Cloud-STT Bottleneck (Jun 2026)"** documenting the latency + HIPAA/GDPR + multilingual implications for remote-fitting portals and Noah ES web clients. Frames the structural news as "vendors are normalizing on-device ASR as a baseline web capability."
- **`wiki/concepts/tinyml-edge-ai.md`** — Added Synaptics source to frontmatter; `updated:` bumped to 2026-06-10; new section **"Commodity Always-On Audio MCUs Emerge (Synaptics Astra SR80, May 2026)"** framing Astra SR80 as the structural signal that always-on audio NN inference is now MCU-class commodity, with implications for hearable/OTC form-factor convergence and pressure on OEM main-SoC roadmaps from below.
- **`wiki/concepts/auracast-bluetooth-le-audio.md`** — Added HLAA convention source to frontmatter; `updated:` bumped to 2026-06-10. The convention deploys hearing loops + Auracast in every meeting room — useful real-world stress-test data point.

### Editorial notes
- Light-net-new day: 6 of 11 digest items mapped to existing sources (DBHN-Net + FPGA SuDoRM-RF++ were already ingested 2-3 days ago; BIHIMA, Veterans Act, AirPods 100-countries, Phonak awards, Sonova divestiture, Auracast rollout all covered).
- Three net-new sources opened distinct lanes: (1) **HLAA AI Symposium** as a consumer-advocacy temperature read; (2) **Microsoft Edge on-device ASR** as a teleaudiology infrastructure shift; (3) **Synaptics Astra SR80** as a commodity-MCU pressure point against OEM SoC roadmaps. The fourth (Frontiers dementia review) reinforces the existing subjective-objective gap thesis with a fresh authoritative citation.
- The Synaptics + Microsoft Edge items together point to a coherent emerging substrate: always-on audio NN inference and on-device ASR are both becoming default commodity capabilities of the platforms hearing AI ships on. Worth a synthesis page in a future ingest if a third reinforcing data point appears.

**Pages touched this ingest: 9** (4 new sources, 4 page updates, +1 log entry, +index update to follow).

---

## Ingest — 2026-06-11 (LinkedIn drafts ingest)

**Source of operation:** Daily LinkedIn post drafts emailed to door.punch_4o@icloud.com and posted to Discord channel 1492462147127742565.

### New source files
- **`sources/apple-wwdc-2026-generated-subtitles-jun-2026.md`** — Apple WWDC 2026 keynote (Mon 8 Jun 2026). Generated Subtitles — on-device automatic speech recognition that auto-transcribes any uncaptioned video the OS plays into on-screen subtitles. Ships across iPhone / iPad / Mac / Apple TV / Vision Pro under iOS 27 / iPadOS 27 / macOS 27 / tvOS 27 / visionOS 27. Default-on, audio never leaves device, English U.S./Canada at launch with expansion expected. The platform-tier delivers a parallel visual-substitution accessibility pathway at consumer scale to ~1B installed devices.
- **`sources/apple-wwdc-2026-name-recognition-mfi-confirmation-jun-2026.md`** — Same WWDC 2026 keynote confirms two further hearing-accessibility primitives: (1) Name Recognition extends the deaf/HoH ambient-name-alert from English to 50+ languages on-device as a system-level service across iPhone / iPad / Apple Watch / Mac / Vision Pro, implying a single multilingual on-device acoustic keyword-spotter at production quality; (2) MfI hearing aid handoff confirmed reliable across iPhone / iPad / Mac / Apple Vision Pro under a unified iOS+iPadOS+macOS+visionOS setup flow, bringing MfI lifecycle management to parity with AirPods. Together with the June 8 AirPods Custom EQ, WWDC 2026 shipped four hearing-accessibility primitives in one keynote — visual substitution, audio personalization, semantic alerts, ecosystem device integration.

### Wiki page updates
- **NEW `wiki/concepts/visual-substitution-hearing-accessibility.md`** — Concept page formalizing visual substitution as a distinct accessibility category orthogonal to audio-pathway enhancement. Sections: Why This Matters (30 years of one-axis audio-cleaning competition), June 2026 inflection naming Apple Generated Subtitles + Apple Name Recognition + Microsoft Edge 148 on-device Web Speech API + live-captioning smart glasses + Adobe-Speechmatics on-device STT as a single substrate-commodification wave, **Two-Layer Strategy Stack table** spanning 9 wearer scenarios with audio-path + visual-path entries each, Where Audio Still Wins (no-screen / music / spatial / cognitive-load / safety), Where Visual Substitution Compresses Audio's Value (personal video / lecture-meeting / novel-clip / multilingual), Strategic Implications for Hearing-Aid OEMs (audio-pathway budget must defend itself, hybrid product opportunity unbuilt, Apple owns more of the accessibility surface area each release), open questions on latency / multi-speaker diarization / caption + HA co-personalization / battery / regulatory framing. Tags: accessibility, captions, subtitles, asr, on-device, visual-substitution, deaf, hard-of-hearing, hearing-aid-strategy.
- **`wiki/entities/apple-hearing-features.md`** — Added both new sources to frontmatter; expanded the prior "Pre-WWDC 2026 Accessibility Drop" section into a "Pre-WWDC + WWDC 2026 Confirmation" section that covers Generated Subtitles + Name Recognition 50+-language confirmation + MfI handoff parity across iOS/iPadOS/macOS/visionOS + Vision Pro hearing accessibility footprint + FaceTime Sign Language Inserts API for third-party app integration; bumped `updated:` to 2026-06-11.
- **`wiki/concepts/companion-phone-speech-pipeline.md`** — Added both new sources to frontmatter; added `visual-substitution-hearing-accessibility` to related; new **"June 2026 Update — The Pipeline Now Carries Visual Substitution and Semantic Alerts"** section documenting that the companion-phone tier is no longer only an audio-cleaning host for the HA — it is increasingly a multi-modal accessibility substrate carrying audio cleaning + caption generation + semantic alerting all running on the same chip; strategic implication that OEMs building only audio-cleaning workloads on the phone tier will find themselves competing for share of a stack that the platform is using to ship parallel accessibility pathways for free; bumped `updated:` to 2026-06-11.
- **`wiki/index.md`** — Added new top-of-file ingest entry covering both sources and the visual-substitution concept page; added `visual-substitution-hearing-accessibility` row to Concepts table; bumped Apple Hearing Features entity row to 2026-06-11 with new tags `generated-subtitles, wwdc-2026, ios-27, visual-substitution`; companion-phone-speech-pipeline row date and tags already bumped earlier today.

### Underlying LinkedIn posts
1. **Apple just shipped a hearing-substitute layer to a billion devices** — iOS 27 / iPadOS 27 / macOS 27 / tvOS 27 / visionOS 27 all get Generated Subtitles on-device, default-on, private. For 30 years hearing-aid AI has competed on a single axis (how well the audio gets cleaned) and Apple just industrialized a parallel pathway — visual substitution — at consumer scale. The wearer's strategy stack now has two layers not one. If captions are universally available everywhere the wearer looks, what does audio enhancement need to deliver that text doesn't?
2. **Apple just made "wake on your name" an OS service in 50+ languages** — WWDC 2026 Name Recognition goes global on-device + MfI hearing aids get reliable cross-device handoff across iOS / iPadOS / macOS / visionOS. Two compounding shifts: (a) a semantic listening primitive — wake-on-your-name — moves from OEM differentiator to platform service with on-device inference and global language coverage; (b) MfI hearing aids become a first-class device class with proper lifecycle management, the way AirPods already are. The OEM question gets sharper — which of your features survive being absorbed into the platform layer, and which become commodity plumbing once Apple ships them in 50 languages on a billion devices?

### Editorial notes
- Both posts anchored to the WWDC 2026 keynote (Mon Jun 8) — same news hook but distinct angles: Post 1 is the visual-substitution-pathway-at-platform-scale frame, Post 2 is the platform-absorbs-OEM-primitives + ecosystem-stickiness frame. Topic histories confirmed Name Recognition, Generated Subtitles, MfI handoff, captions, and subtitles had not been LinkedIn-posted before today.
- The Name Recognition / MfI handoff hook was previewed in Apple's 19 May Newsroom drop (already ingested as `apple-pre-wwdc-accessibility-may-2026.md`) but never turned into a post; the WWDC 2026 keynote confirms-and-ships made it valid as fresh news.
- WWDC 2026 has now produced three ingested source files in four days (Custom EQ on Jun 10, Generated Subtitles + Name Recognition/MfI today) — Apple is occupying a disproportionate share of the recent ingest pipeline, consistent with the "Apple owns more of the accessibility surface area each release" thesis now formalized on the new visual-substitution concept page.
- The new visual-substitution concept page is structurally a sibling to `companion-phone-speech-pipeline` and `on-device-ml-hearing-aids` — three pages now triangulate the platform / phone / chip tier of the 2026 hearing-accessibility stack. Next reinforcing data point (regulatory recognition of captions as primary accommodation, OEM hybrid caption+sound product, or smart-glasses caption maturity benchmark) will be worth either a synthesis page or a comparison page (visual-substitution vs audio-enhancement).

**Pages touched this ingest: 5** (2 new sources, 1 new concept page, 2 page updates, +1 index update, +1 log entry).

---

## Ingest — 2026-06-11 (Daily hearing+AI digest ingest)

**Source of operation:** Daily hearing+AI digest emailed to door.punch_4o@icloud.com (subject: "🎧 Hearing + AI Daily Digest — 11 Jun 2026"), Discord confirmation posted.

### New source files
- **`sources/arxiv-2606-12328-halo-half-frame-rate-se-jun-2026.md`** — Zhao et al., HALO: Half-Frame-Rate Adaptive Learnable Operator for Lightweight STFT-Based Speech Enhancement (arXiv:2606.12328, submitted 10 Jun 2026). Drop-in module that halves internal frame rate via dynamic-conv rate reduction + restoration, reinvests saved compute as wider channels, leaves STFT pipeline untouched. DNS3 evaluation shows consistent gains across multiple lightweight SE baselines at fixed FLOP budget.
- **`sources/arxiv-2606-08580-gmapse-gmm-prior-matching-jun-2026.md`** — Zhu et al., G-MaP-SE: Guided Speech Enhancement via GMM-Based Prior Matching (arXiv:2606.08580, Interspeech 2026 accepted). GMM prior over clean-speech speaker embeddings, snap noisy embeddings to nearest mode at inference, gated fusion into TF-domain SE backbone. Closes most of the gap to oracle clean-conditioning without enrollment audio.
- **`sources/trihear-cleartv-launch-jun-2026.md`** — Trihear ClearTV launch 4 Jun 2026. App-free wireless TV streamer, two SKUs ($99 BT for Phonak/Unitron, $119 ASHA for Oticon/Signia/Widex/Starkey/ReSound/Jabra/Philips), on-board LCD, 12 hr battery.
- **`sources/sterkens-joins-center-for-hearing-access-jun-2026.md`** — Dr. Juliëtte Sterkens joins CHA as Hearing Access Advocate, eff. 1 Jun 2026. Wisconsin loop rollout (1,000+ venues), 1.3M-view TEDx. CHA consolidation as US ALS advocacy hub at Auracast venue rollout inflection.
- **`sources/rethinking-audiologic-evaluation-fhh-jun-2026.md`** — FHH 2026 panel (8 Jun 2026) publicly arguing PTA-anchored test battery is obsolete; speech-in-noise, OAEs, central screening, teleaudiology, AI-driven diagnostic workflows positioned as next standard.
- **`sources/sound-pitch-buzz-7-soundhub-denmark-jun-2026.md`** — SOUND Pitch & Buzz #7 today (11 Jun 2026). Eight SoundTech accelerator startups pitching to Demant/WSA-adjacent investor cluster. Sound Hub historically a leading indicator of Demant partnership/acquisition interest.

### Wiki page updates
- **`wiki/concepts/speech-enhancement-neural-networks.md`** — Added HALO + G-MaP-SE sources; bumped `last_change` to note HALO as orthogonal axis to DBHN-Net (branch fusion) / SB-RF (inference steps) / Khanagha (RIR encoding), and G-MaP-SE as no-enrollment target-SE primitive. Bumped `updated:` to 2026-06-11.
- **`wiki/concepts/auracast-bluetooth-le-audio.md`** — Added Sterkens-CHA + Trihear ClearTV sources to frontmatter. Bumped `updated:` to 2026-06-11.
- **`sources/hlaa-2026-convention-opens-june-2026.md`** — Added confirmed Friday Research Symposium speakers (Blustein NYU, Lesica UCL, Robler UAMS) with note that Lesica's presence signals biology-in-the-loop HA ML / DAL-direction normalization for consumer-advocacy audience.
- **`wiki/index.md`** — Added new top-of-file ingest entry covering all six new sources and the three updated pages.

### Editorial notes
- Today's ingest is biased toward news-of-the-week rather than research-paper-of-the-week, consistent with HLAA convention week and FHH 2026 dropping in the same calendar slot. Two papers (HALO, G-MaP-SE) keep the SE pipeline current.
- HALO + G-MaP-SE + DBHN-Net (yesterday) + Khanagha-RIR-encoder + SB-RF + FPGA SuDoRM-RF++ now form a six-paper June 2026 cluster on lightweight / on-device / target-conditioned SE. Worth flagging that next ingest day as a candidate for a synthesis page (e.g., `june-2026-lightweight-se-cluster.md`) if the trend continues another 1-2 papers deep.
- The Sterkens-CHA appointment + FHH "Rethinking the Audiologic Evaluation" panel + HLAA Friday Symposium together form a coherent week-of-June-8 narrative: the consumer-advocacy and clinical-leadership sides of US hearing health are simultaneously moving toward AI-driven workflows and Auracast-era ALS — a useful three-data-point reinforcement of the "hearing-care funnel is being rebuilt" thesis already on `wiki/concepts/hearing-care-funnel-attribution.md`.
- Skipped re-ingesting items already covered in yesterday's digest (DBHN-Net, FPGA SuDoRM-RF++, BIHIMA Q1, Phonak Awards, Microsoft Edge 148, Synaptics Astra SR80, Frontiers cognitive-decline review, Auracast rollout summary) and the previously-ingested DAL paper — but re-flagged DAL in today's digest because the HLAA Friday speaker confirmation (Lesica/UCL) makes it newly relevant context.

**Pages touched this ingest: 10** (6 new sources, 2 concept-page updates, 1 source update, 1 index update, +1 log entry).

## 2026-06-12 — LinkedIn-drafts ingest (HALO + Gumbel-BEARD)

Drafted two LinkedIn posts for review:
- **Post 1:** HALO (arXiv:2606.12328, Jun 10 2026) — half-frame-rate adaptive learnable operator. Framed as the fourth on-chip lever (alongside Olalere FPGA memory-bandwidth Jun 4, DBHN-Net SNN+ANN sparsity Jun 5, SB-RF one-step generative SE Jun 4). Argument: four orthogonal axes in two weeks; competitive moat shifts from a single architectural bet to a search over the cross-product.
- **Post 2:** Gumbel-BEARD (arXiv:2606.11429, Jun 9 2026, UCLA SPAPL, Interspeech 2026) — end-to-end-trainable Gumbel-Softmax selector over Whisper encoder layers. Closes the loop the Ciferri Whisper-ECoG paper (Jun 3) opened — provides a deployment-grade mechanism for the brain-aligned-layer hypothesis. 13× sample-efficiency gain on MyST pediatric ASR; also delivers on CORAAL dialectal speech.

Ingest actions:
- **New source file:** `sources/arxiv-2606-11429-gumbel-beard-layer-selection-jun-2026.md`
- **HALO source already existed** (`sources/arxiv-2606-12328-halo-half-frame-rate-se-jun-2026.md`) — no duplicate created.
- **Updated concept page:** `wiki/concepts/brain-aligned-speech-foundation-models.md` — added Gumbel-BEARD as deployment-grade mechanism for the layer-choice hypothesis; updated frontmatter (added source, related cross-lifespan, gumbel-softmax tag); added a new "Deployment-Grade Mechanism" section; added Gumbel-BEARD to Sources block.
- **New synthesis page:** `wiki/syntheses/on-chip-hearing-ai-levers-june-2026.md` — catalogs the four levers (bandwidth, sparsity, inference steps, frame rate), why they are separable, and the cross-product strategic implication. Sources: Olalere FPGA, DBHN-Net, SB-RF, HALO.
- **Updated `wiki/index.md`** — added the new synthesis page under the syntheses table.

Pages touched this ingest: **5** (1 new source, 1 concept-page update, 1 new synthesis, 1 index update, +1 log entry).

---

## Ingest — 2026-06-13 (C2D microphone projection + Fraunhofer gen-vs-disc)

**Source of operation:** Ad-hoc ingest of two June-2026 arXiv papers explicitly flagged by user: (1) Nakatani et al. NTT C2D microphone projection (arXiv:2606.13109, ICASSP 2026), (2) Saha Shetu, Habets & Brendel Fraunhofer IIS generative-vs-discriminative SE empirical comparison (arXiv:2606.02913, Jun 1 2026).

### New / re-ingested source files
- **`sources/arxiv-2606-13109-c2d-microphone-projection-nakatani-jun-2026.md`** — NEW. C2D method: dual-microphone field recordings (close-talk lavalier + distant array) projected through PMWF (Parametric Multichannel Wiener Filter) yield real paired training data without simulated mixing. Outperforms Guided Source Separation (GSS) on CHiME6 dinner-party benchmark. Reframes SE training-data axis as a data-collection problem, not a synthesis problem.
- **`sources/arxiv-2606-02913-generative-vs-discriminative-se-jun-2026.md`** — RE-INGESTED (was thin, originally ingested 2026-06-08). Expanded multi-axis comparison: discriminative wins in-distribution / stationary noise; generative wins OOD / non-stationary / unseen reverberation; first empirical quantification of generative-SE hallucination via WER + phoneme similarity rather than PESQ/STOI/HASPI. Hallucination phenomenon now established as paradigm-level (LM-SE → diffusion-SE), not architecture-specific to L3-SE.

### New wiki pages
- **`wiki/concepts/close-to-distant-microphone-projection.md`** — NEW concept page. Positions C2D as counter-paradigm to synthetic-data taxonomies on the training-data substrate axis; complement to DFC-IL (dynamics-side closure) on the training-deployment distribution gap; partial upstream mitigation of the generative-SE hallucination risk by narrowing the OOD region every paradigm must extrapolate across.

### Wiki page updates
- **`wiki/concepts/synthetic-data-for-hearing-ai.md`** — Added C2D row to training-data approach table; added "Counter-Paradigm: Real Paired Data via C2D Microphone Projection (Jun 2026)" section.
- **`wiki/concepts/training-deployment-distribution-gap.md`** — Added new item #6 in "What Closes the Gap" list framing C2D as data-side closure paired with DFC-IL dynamics-side closure (stackable).
- **`wiki/concepts/speech-enhancement-neural-networks.md`** — Added two new body sections: C2D training-substrate and Fraunhofer first-empirical-hallucination-quantification. Both new sources added to frontmatter.
- **`wiki/concepts/linguistic-hallucination-speech-enhancement.md`** — Added "First Empirical Quantification on the Diffusion-SE Branch" section framing Fraunhofer as the *magnitude* of the L3-SE-named failure mode; extended from LM-SE to generative-SE-general.
- **`wiki/concepts/probabilistic-generative-models-hearing-ai.md`** — Enriched "Where Generative vs Discriminative Sit Today" section with WER + phoneme-similarity hallucination framing and paradigm-vs-architecture distinction. Added "Training-Substrate Complement (C2D)" subsection.
- **`wiki/concepts/differentiable-cochlear-models.md`** — Light cross-link to C2D in Related Pages (DAL reshapes loss function inside training loop; C2D reshapes noisy-clean pairs the loop trains on — stackable).
- **`wiki/syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md`** — Added "Update — 13 June 2026: The Linguistic-Faithfulness Crack Gets Its First Empirical Magnitude" section with before/after framing and note on C2D as upstream mitigation.
- **`sources/arxiv-2606-05575-sbrf-schrodinger-bridge-jun-2026.md`** — Added "Companion / Counter-Findings" section connecting SB-RF (latency floor closed) to Fraunhofer (content-fidelity gate still open) and C2D (upstream training-data mitigation).
- **`wiki/index.md`** — Added 2026-06-13 ingest entry to top-of-file change log; added Close-to-Distant (C2D) Microphone Projection row to Concepts table.

### Editorial notes
- The Fraunhofer paper turns the L3-SE / linguistic-hallucination thread from a single-data-point claim into a paradigm-level empirical finding. The SE-evaluation-stack synthesis now has a quantified third-crack metric (WER + phoneme similarity) and an explicit population-asymmetry argument (lexical artifacts hurt residual-hearing / pediatric / CI-margin populations disproportionately).
- C2D + DFC-IL together form a "data side + dynamics side" pair on the training-deployment distribution gap. Pattern-match to the DAL + BiEAR afferent/efferent pair (2 papers, 24 hours apart) — June 2026 is producing complementary-pair drops at high frequency.
- The Fraunhofer hallucination quantification is methodologically portable to factor-graph probabilistic-generative SE (AIDA-2 et al.) — flagged as the obvious next controlled head-to-head.

**Pages touched this ingest: 11** (1 new source, 1 re-ingested source, 1 SB-RF source update, 1 new concept page, 6 concept-page updates, 1 synthesis update, 1 index update, +1 log entry).

---

## Ingest — 2026-06-13 (Daily digest: DeepGESI + classroom-children SE + Tiny-DL survey arXiv ID)

**Source of operation:** Daily hearing+AI email digest, sources surfaced via web research; email sent to door.punch_4o@icloud.com.

### New source files
- **`sources/arxiv-2512-19374-deepgesi-non-intrusive-hi-intelligibility.md`** — NEW. Reference-free intelligibility predictor tuned for hearing-impaired listeners; positioned as candidate training-objective for hearing-aid DSP pipelines that never see a clean reference. Linked from `wiki/concepts/non-intrusive-intelligibility-prediction.md`.
- **`sources/arxiv-2511-07677-speech-separation-hi-children-classroom.md`** — NEW. Speech separation targeted at HI children in reverberant multi-talker classroom conditions — an under-served population/domain combination relative to adult-voice / low-reverb benchmarks.

### Source file updates
- **`sources/tiny-ml-to-tiny-dl-survey-acm-2026.md`** — Added `arxiv: 2506.18927` cross-identifier and `last_referenced: 2026-06-13` field. The arXiv preprint and the ACM Computing Surveys version are the same survey; consolidated rather than duplicated.

### Wiki page updates
- **`wiki/concepts/non-intrusive-intelligibility-prediction.md`** — Added DeepGESI to `sources` frontmatter, bumped `updated`, added Sources-section entry framing it as an HI-tuned non-intrusive metric and a candidate DSP training objective.

### Editorial notes
- Today's digest was deliberately short on novelty: most flagged items (Phonak Virto R Infinio AI Excellence Award, AirPods country expansion, Orka O1 Pro at AWE 2026, GN ReSound Enzo IA / Smart Fit 2.3, DBHN-Net, the Tiny-DL survey) were already ingested in prior log entries — no new pages or source files needed for those. The two genuinely new ingests are both evaluation/data-side contributions rather than model-architecture papers, which matches the pattern noted in the 11 Jun and earlier June logs that the SE-evaluation stack is the cracking surface this quarter.
- DeepGESI joins the foundation-model-fusion Nakazawa work (frame-aligned Canary × WavLM) as the second 2026 entry on the non-intrusive intelligibility prediction page — the page is starting to accumulate a distinct HI-tuned reference-free lineage. Worth watching whether the Clarity Prediction Challenge organizers adopt one of these as the CPC4 baseline.

**Pages touched this ingest: 5** (2 new sources, 1 source-file metadata update, 1 concept-page update, +1 log entry).

---

## Ingest — 2026-06-14 (Ad-hoc: ModeratorLM turn-taking arXiv + HLAA 2026 Convention)

**Source of operation:** Ad-hoc ingest task; two sources covering the engineering and patient-voice rungs of the same fortnight.

### New source files
- **`sources/moderatorlm-adaptive-turn-taking-arxiv-june-2026.md`** — NEW. Mitra, Pandey, Jain, Sahith, Girish (Amazon), arXiv:2606.13544, submitted 11 Jun 2026, Interspeech 2026. Chunk-wise streaming speech-LLM voice agent for multi-party conversation; role-conditioned turn-taking + reasoning-enhanced chain-of-thought variant; RolePlayConv synthetic corpus; +40% turn-taking precision and >70% recall over the strongest non-role-conditioned baseline. Hearing-AI framing: multi-party as #1 unsolved wearer complaint; reactive→predictive shift in beamforming / gain ramps / attention steering; generative cousin to the dyadic-interaction-preservation diagnostic at the interactional layer.
- **`sources/hlaa-2026-convention-louisville-june-2026.md`** — NEW. HLAA 41st Annual Convention, 10-12 Jun 2026, Galt House Louisville KY. Captioning for every session + hearing loops in every meeting room as consumer-scale accessibility deployment. Fri Jun 12 NIDCD-supported Research Symposium "The AI Revolution in Hearing Health: Smarter Tech, Greater Access" — first US patient-side convention with AI as headline plenary. Patient-voice rung of the three-rung discourse ladder alongside HEAL 2026 Padua (clinical) and arXiv-week (engineering). Complements the previously-ingested `sources/hlaa-2026-convention-opens-june-2026.md`.

### New wiki pages
- **`wiki/concepts/turn-taking-prediction-hearing-ai.md`** — NEW concept page. Turn-taking prediction as a pragmatic primitive for hearing AI; reactive→predictive scene-control shift; role-conditioning mechanism transferable to wearer-side host/guest/listener; companion-phone substrate; sub-primitive of the interactional axis alongside dyadic-interaction-preservation in the five-axis evaluation stack.
- **`wiki/entities/hlaa.md`** — NEW entity page. Hearing Loss Association of America. Three-rung-discourse-ladder framing (engineering / clinical / patient); annual-convention table; accessibility-substrate-deployment angle; legislative weight (Veterans Hearing Aid Improvement Act endorser).
- **`wiki/concepts/patient-advocacy-hearing-health.md`** — NEW concept page. Anchors the wearer-voice rung. HLAA + WHO + ACI Alliance as canonical anchors; the contested-AI-questions list at the patient rung in 2026 (DNN noise reduction now table-stakes; on-demand AI clarity boost contested; conversation memory / name recognition feature-acceptance question; audiogram-vs-self-fit divided; real-time captioning broadly accepted).

### Wiki page updates
- **`wiki/concepts/dyadic-interaction-preservation.md`** — Added `turn-taking-prediction-hearing-ai.md` to `related:` frontmatter; added a Related-Pages line flagging ModeratorLM as the generative cousin to the diagnostic. Bumped `updated` to 2026-06-14.
- **`wiki/index.md`** — Added 2026-06-14 ingest entry to top-of-file change log; added Turn-Taking Prediction and Patient Advocacy rows to Concepts table; added HLAA row to Entities table.

### Editorial notes
- The interactional axis of the SE evaluation stack now has both a **diagnostic** (speaker-switch / DDM, arXiv:2606.02185, 1 Jun 2026) and a **generative** (ModeratorLM, arXiv:2606.13544, 11 Jun 2026) operationalization in the same fortnight. Same construct (interactional layer), different operation (evaluate vs act).
- The patient-voice rung surfacing AI as the headline plenary (HLAA Fri 12 Jun) in the same fortnight as the engineering rung (arXiv flow) and clinical rung (HEAL 2026 Padua, 4-6 Jun) is the first time all three rungs of the discourse ladder have produced an AI-in-hearing-health headline in the same week. Pattern worth tracking for cross-rung translation lag (how long does engineering→patient typically take, and is it compressing).
- Role-conditioning is the architecturally portable piece of ModeratorLM for hearing AI — the same mechanism that lets a voice agent be a moderator vs an expert lets a hearing aid be tuned for "wearer is host" vs "wearer is invited guest" vs "wearer is the quiet listener." Natural locus for personalization at the interactional layer.

**Pages touched this ingest: 7** (2 new sources, 3 new wiki pages, 1 wiki-page update, 1 index update, +1 log entry).

## Ingest — 2026-06-14 (Daily digest: Tetteh-et-al UAIS SE review + Consumer Reports OTC head-to-head)

**Source of operation:** Daily hearing+AI email digest, sources surfaced via web research; email sent to door.punch_4o@icloud.com.

### New source files
- **`sources/uais-tetteh-se-techniques-hearing-aids-review-2026.md`** — NEW. Tetteh, Mensah Gyening, Arthur, *Universal Access in the Information Society*, DOI 10.1007/s10209-026-01342-7, Apr 2026. Systematic review of AI-driven SE for hearing aids 2017–2025 across classical DSP / deep learning / hybrid AI+adaptive filtering taxonomy. Confirms field-wide that DL beats classical SE in complex acoustic scenarios, hybrids occupy the embedded-deployment middle ground. Linked from `wiki/concepts/speech-enhancement-neural-networks.md`.
- **`sources/consumer-reports-otc-hearing-aid-review-jun-2026.md`** — NEW. Consumer Reports first head-to-head test of 14 OTC hearing aids, updated 12 Jun 2026. Covers Apple, Eargo, Lexie, Sennheiser + MDHearing / Audien / Yeasound / Soundbright / Elehear / Concha Labs. Lab measurement + HI-user panel; ease-of-use / performance / sound-quality axes; trial-period UX flagged as the binding bottleneck. Linked from `wiki/concepts/otc-hearing-aids.md`.

### Wiki page updates
- **`wiki/concepts/speech-enhancement-neural-networks.md`** — Added Tetteh review to `sources` frontmatter; bumped `updated` to 2026-06-14; bumped `last_change` to note the literature-level confirmation framing against single-study work (FPGA SuDoRM-RF++, DAL).
- **`wiki/concepts/otc-hearing-aids.md`** — Added Consumer Reports review to `sources` frontmatter; bumped `updated` to 2026-06-14; added bottom-Sources entry framing it as the consumer-electronics-isation marker (Apple as default comparator) and trial-period-as-binding-bottleneck data point.
- **`wiki/index.md`** — Added 2026-06-14 daily-digest entry to top-of-file change log (demoted the earlier-today ad-hoc ModeratorLM/HLAA entry to "_Earlier_").

### Editorial notes
- Mostly a re-reference day: 8 of the 11 digest items mapped to already-ingested sources (DAL, FPGA SuDoRM-RF++, DFingerNet, Veterans Act, Widex Allure AI, Demant Q1/Zeal, Starkey Auracast, Auracast UK theatres). The two net-new ingests are both review-class / consumer-test-class items rather than primary research — consistent with the pattern noted in the 11-13 Jun log entries that the SE-evaluation and consumer-channel stacks are where the action is this quarter, not new architectures.
- The Tetteh review covers 2017–2025, so it pre-dates the 2026 generative-SE wave (AIDA-2, GMAPSE, SBRF, DriftSE, DFingerNet at its IEEE conference version) and the L3-SE / linguistic-hallucination naming work. Useful as a literature-level anchor for the "DL > classical" claim but explicitly not yet covering the generative-vs-discriminative tradeoff the Fraunhofer 13 Jun ingest quantified.
- The CR test methodology — combining lab measurement with HI-user panels across three axes — is closer to a mini-Clarity-Prediction-Challenge framing than to a typical consumer-electronics review. Worth tracking whether the CR test set becomes a de facto reference cohort for OEM marketing claims in 2026–2027, since the prior CR OTC coverage was paragraph-scale not test-driven.
- Apple's promotion to default OTC comparator in CR is the cleanest single signal of OTC consumer-electronics-isation we've logged.
- The Veterans Hearing Aid Improvement Act was attributed in the digest email to "5 Jun 2026" based on a news re-report, but the underlying Mullin press release dates the House introduction to **1 Jun 2026** — see `sources/veterans-hearing-aid-improvement-act-house-jun-2026.md`. The wiki sticks with the press-release date.

**Pages touched this ingest: 5** (2 new sources, 2 concept-page updates, 1 index update, +1 log entry).

---

## Lint — 2026-06-14

**Pages scanned:** 111 (69 concepts, 26 entities, 4 comparisons, 12 syntheses)
**Sources inventoried:** 297
**Issues found:** 18
**Auto-fixed:** 14
**Needs human judgment:** 4 (carried from prior lints)

### Index vs filesystem
- ✅ All 111 index entries resolve to real files.
- ✅ All 111 wiki files are listed in index.md.

### Broken `related:` links — FIXED

**`syntheses/on-chip-hearing-ai-levers-june-2026.md`** — all 5 `related:` entries were bare filenames resolving to the wrong directory (syntheses/ instead of concepts/). Fixed: added `../concepts/` prefix to all 5 entries. Also added `../concepts/tinyml-edge-ai.md` as a 6th related entry (the SNN+ANN paper sourced there directly). Updated date to 2026-06-14.

**`concepts/efferent-moc-feedback-hearing-ai.md`** — `binaural-beamforming.md` in `related:` does not exist anywhere in the wiki. Fixed: removed broken link; replaced with `speech-enhancement-neural-networks.md` (the BiEAR paper targets SE/localization). Updated date to 2026-06-14. Note: if a `binaural-beamforming.md` page is created in future, add the cross-reference back.

### Orphan pages — FIXED

**`syntheses/on-chip-hearing-ai-levers-june-2026.md`** — had zero incoming links (plus the 5 broken outgoing links above). Fixed: added `../syntheses/on-chip-hearing-ai-levers-june-2026.md` to `related:` in:
- `concepts/hearing-aid-chip-architectures.md` (updated 2026-06-14)
- `concepts/on-device-ml-hearing-aids.md` (updated 2026-06-14)
- `concepts/tinyml-edge-ai.md` (updated 2026-06-14)

### Missing cross-references — FIXED

**`concepts/turn-taking-prediction-hearing-ai.md`** was not linked from `care-partner-dyad-models.md` or `communication-accessibility-metric.md` despite body-text references. Fixed: added `turn-taking-prediction-hearing-ai.md` to `related:` in both pages. Updated both dates to 2026-06-14.

**New pages `entities/hlaa.md` and `concepts/patient-advocacy-hearing-health.md`** (created 2026-06-14, only linked to each other). Fixed: added both to `related:` in `concepts/auracast-bluetooth-le-audio.md` (HLAA is a named source in that page's `sources:` list). Also added `patient-advocacy-hearing-health.md` to `related:` in `concepts/communication-accessibility-metric.md`. Updated both pages' dates to 2026-06-14.

Also added `continual-learning-hearing-ai.md` to `related:` in `concepts/on-device-ml-hearing-aids.md` (body text discusses continual adaptation but did not link to the concept page).

### Stale sources
- **`entities/amplifon.md`** — single source dated 2026-01-01 (165+ days old). Page describes the GN Hearing acquisition as ongoing strategic transformation; situation has evolved. Flagged for next entity refresh cycle.
- 15 additional pages last updated between 2026-04-15 and 2026-04-26 on fast-moving topics (AI architectures, chip hardware, market data, regulation). Not structurally broken; flagged as candidates for the next ingest wave.

### Oversized pages
- `concepts/speech-enhancement-neural-networks.md` — 359 lines (was 313 at 2026-06-07 lint). Growing ~15 lines/week from SE paper ingestions. Trajectory to 500 lines within ~10 weeks. No split needed yet; flag again at next lint.
- `concepts/otc-hearing-aids.md` (280 lines), `concepts/dnn-in-hearing-aids.md` (254 lines) — within acceptable range.

### Potential duplicates
- No new duplicate candidates found. `dnn-in-hearing-aids.md` vs `dnn-architectures-hearing-aids.md` confirmed distinct (noted in prior lints).

### Needs human judgment (persistent)
1. **Missing source `autoresearch-karpathy-april-2026.md`** — cited in `syntheses/pretraining-corpus-as-moat-hearing-ai.md`. Unresolved since 2026-06-07 lint. Either ingest under the correct name or update the frontmatter reference.
2. **`entities/who-hearing-program.md`** — `sources: []` empty. Only wiki page with no source grounding. Add at least one source file.
3. **`syntheses/hearing-ai-research-landscape-2025.md`** — title says "2025" but content draws on 2026 sources. Rename to `hearing-ai-research-landscape-2026.md` or update title in frontmatter. Noted since 2026-05-31 lint.
4. **`entities/amplifon.md`** stale — see Stale Sources above.

### Summary of files modified this lint
1. `syntheses/on-chip-hearing-ai-levers-june-2026.md` — fixed 5 broken related: paths + added tinyml cross-link
2. `concepts/efferent-moc-feedback-hearing-ai.md` — removed broken binaural-beamforming.md link; added speech-enhancement-neural-networks.md
3. `concepts/care-partner-dyad-models.md` — added turn-taking-prediction-hearing-ai.md
4. `concepts/communication-accessibility-metric.md` — added turn-taking-prediction-hearing-ai.md + patient-advocacy-hearing-health.md
5. `concepts/hearing-aid-chip-architectures.md` — added on-chip-hearing-ai-levers-june-2026.md
6. `concepts/on-device-ml-hearing-aids.md` — added on-chip-hearing-ai-levers-june-2026.md + continual-learning-hearing-ai.md
7. `concepts/tinyml-edge-ai.md` — added on-chip-hearing-ai-levers-june-2026.md
8. `concepts/auracast-bluetooth-le-audio.md` — added hlaa.md + patient-advocacy-hearing-health.md

**Pages touched this lint: 9** (8 wiki pages updated + this log entry).

---

---

## Ingest — 2026-06-15 (LinkedIn drafts: HIDVAS dataset + MeCo one-step corrector)

**Source of operation:** Daily LinkedIn-post drafting; two arxiv-week items selected after checking 538-line post history for non-repeat angles. Posts written and shipped to Discord channel 1492462147127742565 and emailed to door.punch_4o@icloud.com. This log entry covers the wiki-ingestion leg.

### New source files
- **`sources/arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md`** — NEW. Roebben, Bernardi, Wouters, van Waterschoot, Moonen (KU Leuven); HIDVAS — Hearing Instrument Dataset in Various Acoustical Scenarios; arXiv:2606.14175; accepted EURASIP Journal on Audio, Speech, and Music Processing (June 12, 2026); CC-BY-4.0. Dummy-head + BTE/RIC shell + eardrum-level mic recordings; 8 external loudspeakers + 2 reference room mics; speech / SSN / singing / strings / wind / percussion stimuli; T30 = 0.09 / 0.47 / 0.73 / 1.48 s; **open / semi-open / closed / no-RIC dome configurations as a structured published variable** (the headline novelty for ML pipelines that have inherited single-dome distribution mismatch). Both IRs and audio published.
- **`sources/arxiv-2606-09677-meco-meanflow-corrector-jun-2026.md`** — NEW. Kim & Choi (KAIST); MeCo — discriminative estimator followed by a one-step **MeanFlow**-based generative corrector for multi-channel speech separation; Interspeech 2026; arXiv:2606.09677; **DSO (Data-Space Optimization)** loss combining x_r-loss (perceptual displacement) with endpoint SI-SDR (signal fidelity). Reported SOTA in-domain and out-of-domain with minimal compute overhead.

### New wiki pages
- **`wiki/concepts/hidvas-dataset.md`** — NEW. Standalone concept page for HIDVAS as a public-substrate benchmark; covers composition, why-it-matters (real-vs-simulated, dome configuration as first-class variable, IR+audio substrate framing, KU Leuven public-substrate program continuity with SparrKULee / AV-GC-AAD), limitations (no listener-perception labels, no pediatric, no bilateral fitting feedback). Cross-linked to training-deployment-distribution-gap, room-aware-dereverberation, synthetic-data-for-hearing-ai, speech-enhancement-neural-networks, dnn-architectures-hearing-aids, close-to-distant-microphone-projection.
- **`wiki/concepts/one-step-generative-correction.md`** — NEW. Concept page naming the **discriminative-front + one-step-generative-corrector** pattern as a mid-2026 architectural unit ties together: (1) SB-RF Schrödinger-Bridge-Rectified-Flow (Lu, Lv, Hu, Xu, arXiv:2606.05575, Jun 4 2026), (2) MeCo MeanFlow corrector (Kim & Choi, arXiv:2606.09677, Jun 8-9 2026), (3) Saha Shetu / Habets / Brendel hallucination receipts (arXiv:2606.02913, Jun 1 2026) as the constraint that motivates the pattern. Covers latency-floor crossing, hallucination mitigation as architectural choice, DSO hybrid losses, multi-channel hearing-aid mic-array relevance, and open pieces (HASPI/STOI/CPC3 ports, chip-budget claims, hallucination quantification on the one-step corrector class itself).

### Wiki page updates
- **`wiki/concepts/training-deployment-distribution-gap.md`** — Added HIDVAS as the **evaluation-substrate** instance of the closure tactic (alongside DFC-IL on the dynamics side and C2D on the paired-data side). Added closure-tactic #7 to the body text, added arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md to `sources:` frontmatter, added hidvas-dataset.md to `related:`, bumped `updated:` to 2026-06-15. New tag: real-paired-data, simulation-to-reality-gap.
- **`wiki/concepts/speech-enhancement-neural-networks.md`** — Added arxiv-2606-09677-meco-meanflow-corrector-jun-2026.md and arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md to `sources:` frontmatter; bumped `updated:` to 2026-06-15 with last_change note covering both ingests.
- **`wiki/concepts/linguistic-hallucination-speech-enhancement.md`** — Added Kim & Choi MeCo as the constructive architectural answer to Saha Shetu's hallucination quantification (one week apart, structurally complementary). Added new section "The Constructive Architectural Answer (Kim & Choi, MeCo, Jun 2026)" reframing hallucination as a pipeline-position question rather than a paradigm choice. Added MeCo source to frontmatter + bottom Sources list; added one-step-generative-correction.md to `related:`; bumped `updated:` to 2026-06-15; updated last_change note.
- **`wiki/index.md`** — Added two new concept entries (hidvas-dataset and one-step-generative-correction); added 2026-06-15 daily-ingest entry to top-of-file change log.

### Editorial notes
- Two-axis ingest: **data substrate (HIDVAS) + architecture (MeCo)**. Mirrors the explicit 2026 split the wiki has been tracking — the moat is shifting from architecture to substrate, but the architectural axis is still moving in parallel (SB-RF Jun 4 → MeCo Jun 8-9 means the field went from "first one-step generative SE works" to "one-step generative as a corrector after a discriminative front" in 4 days).
- MeCo's framing closes a loop that has been open in the wiki since the May 14 L3-SE ingest: the discriminative-vs-generative debate is mis-framed; the right primitive is "where does the corrector live and what does its velocity field point at." Surfaced this explicitly in both `linguistic-hallucination-speech-enhancement.md` and the new `one-step-generative-correction.md` concept page.
- HIDVAS's dome-configuration axis is the first published-dataset surface for vent acoustics in a public-substrate context. Almost every ML pipeline silently assumes a single dome configuration. Worth tracking whether downstream SE / dereverb / beamforming benchmarks adopt HIDVAS as a structured factor or continue training on dome-agnostic mixtures.
- The DSO loss (x_r-loss + endpoint SI-SDR) is the most concrete example of the hybrid-loss direction the [[listening-effort-evaluation]] page has been pointing toward. Likely template for the next round of HASPI-adjacent training objectives.
- Open hallucination question carried forward: is the one-step corrector class measurably less hallucination-prone than its multi-step ancestors? Saha Shetu's harness should be run against MeCo to close this loop. Logged in the open-pieces section of `one-step-generative-correction.md` and the body of `linguistic-hallucination-speech-enhancement.md`.

**Pages touched this ingest: 7** (2 new sources, 2 new wiki pages, 3 wiki-page updates, 1 index update, +1 log entry).

---

## Ingest — 2026-06-15 (Daily hearing+AI digest)

**Source of operation:** Daily hearing+AI digest email compiled and sent to door.punch_4o@icloud.com (subject: 🎧 Hearing + AI Daily Digest — 15 Jun 2026). 7 items covered across Research Papers / Industry News / AI-ML Developments / Worth Watching / Quick Stats. This log entry covers the wiki-ingestion leg.

### New source files
- **`sources/arxiv-2606-14120-faconformer-aad-jun-2026.md`** — NEW. Wang, He, Jia, Wang, Wu (Huazhong Univ. of Sci. & Tech.); FAConformer — Frequency-Aware Convolutional Transformer for Auditory Attention Decoding; arXiv:2606.14120, 12 Jun 2026. Per-band EEG encoding + cross-band attention module on top of a Conformer trunk. ~5% accuracy gain over prior AAD baselines on standard public datasets.
- **`sources/arxiv-2606-13095-llm-asr-diarization-jun-2026.md`** — NEW. Zheng, Lin, Tian, Li, Lin, Xiao, Tu (Huawei); Balancing ASR and Diarization in End-to-End LLMs for Multi-Talker Speech Recognition; arXiv:2606.13095, 11 Jun 2026. Separate semantic + speaker encoders, interleaved tokens, speaker-attribution loss, adaptive overlap threshold. 18% rel. WER drop on AliMeeting / 24% on AISHELL-4 vs strongest open-source multi-talker baselines.
- **`sources/arxiv-2606-13450-endpoint-anticipation-jun-2026.md`** — NEW. Udupa et al.; Endpoint Anticipation for Low-Latency Spoken Dialogue; arXiv:2606.13450, 11 Jun 2026. Predicts speech endpoints from acoustic + lexical cues before the silence threshold elapses, shaving turn-taking latency.

### Wiki page updates
- **`wiki/concepts/auditory-attention-decoding.md`** — Added arxiv-2606-14120-faconformer-aad-jun-2026.md to `sources:` frontmatter; new "FAConformer — Frequency-Aware Conformer for AAD (June 2026)" section at the top of Recent Academic Advances; `updated:` bumped to 2026-06-15.
- **`wiki/index.md`** — New 2026-06-15 daily-digest entry at top, prior 2026-06-14 entry preserved as "Previously updated".

### Items mapped to already-ingested sources (no new files needed)
- Veterans Hearing Aid Improvement Act → `veterans-hearing-aid-improvement-act-house-jun-2026.md`
- HLAA 2026 Louisville convention → `hlaa-2026-convention-louisville-june-2026.md`
- Widex Allure AI RIC rollout → `widex-allure-ai-launch-june-2026.md`
- Consumer Reports 2026 OTC refresh → `consumer-reports-otc-hearing-aid-review-jun-2026.md`
- AccLock earbud BCG biometric auth → `acclock-earbud-bcg-biometric-may-2026.md`

### Editorial notes
- Sunday digest — light news cycle post-HLAA. Three arXiv items dominate; industry news is mostly tail-of-the-week resolution.
- FAConformer lands in the AAD lineage that has been steadily compounding since the May 2026 Mesgarani-lab Nature Neuroscience closed-loop ECoG result reframed AAD's loss function from signal-side to attention-side. Band-wise decomposition is the inductive-bias axis — it does not need more electrodes or more compute, just smarter use of the spectrum the device already has.
- The Huawei multi-talker-ASR work is the substrate for the "who said what" UX that Apple's WWDC 2026 generated-subtitles announcement hinted at. Phone-side LLM + speaker-conditioning is the natural deployment substrate; on-aid is not feasible at these model sizes.
- Endpoint anticipation joins the low-latency-floor family (SB-RF, HALO, FPGA SuDoRM-RF++, DriftSE) — the field is converging on "every 10-50 ms matters" as the operating constraint.

**Pages touched this ingest: 5** (3 new sources, 1 wiki concept update, 1 index update, +1 log entry).

---

## Ingest — 2026-06-16 (LinkedIn-research ingest, three arXiv sources)

**Source of operation:** Three arXiv sources researched for the daily LinkedIn post on 2026-06-16: FAConformer (cortex-side AAD, band-axis), plus two Xunying Liu / CUHK INTERSPEECH 2026 papers on elderly ASR. This entry covers the wiki-ingestion leg.

### Source files
- **`sources/arxiv-2606-14120-faconformer-aad-jun-2026.md`** — UPDATED. Existing 2026-06-15 source file refined with the full extraction detail: Frequency-Aware Attention (FAA) module treats band-wise features as tokens; Band-wise Auxiliary Supervision (BAS) prevents weak-branch under-optimisation; +4.9% over strongest of 12 baselines; two public AAD datasets, three decision-window lengths; explicit "neuro-steered hearing systems" framing.
- **`sources/arxiv-2606-16539-elderly-asr-online-adaptation.md`** — NEW. Chengxi Deng, Xurong Xie, Shujie Hu, Mengzhe Geng, Tianzi Wang, Youjun Chen, Huimeng Wang, Haoning Xu, Jiajun Deng, Xunying Liu (CUHK); "Decoding while Adapting: Zero-Shot Online Speaker Adaptation via Audio-Textual Prompts for Elderly Speech Recognition"; arXiv:2606.16539, 15 Jun 2026, accepted INTERSPEECH 2026. Cross-utterance audio-textual prompts fused cross-modally into compact speaker prompt; beats i-vector / x-vector / ECAPA-TDNN. **−0.61% absolute WER on DementiaBank Pitt (English)**, **−1.22% absolute CER on JCCOCC MoCA (Cantonese)**, **9.83× RTF speedup** vs offline batch adaptation, statistically significant.
- **`sources/arxiv-2606-16546-elderly-asr-pseudo-labeling.md`** — NEW. Chengxi Deng, Xurong Xie, Shujie Hu, Jiajun Deng, Mengzhe Geng, Youjun Chen, Huimeng Wang, Haoning Xu, Guinan Li, Xunying Liu (CUHK); "Confidence Score Guided Incremental and Speaker Adaptive Pseudo-Labeling for Semi-Supervised Elderly Speech Recognition"; arXiv:2606.16546, 15 Jun 2026, accepted INTERSPEECH 2026. High-to-low confidence curriculum on pseudo-labeled unlabeled speech + speaker-adaptive training with learnable prompts. **−1.45% abs WER (6.21% rel) on Pitt**, **−2.27% abs CER (6.98% rel) on JCCOCC MoCA** vs baseline semi-supervised methods.

### New wiki pages (4)
- **`wiki/concepts/elderly-speech-recognition.md`** — Dedicated older-edge concept page. Frames elderly ASR as the older-edge failure mode of cross-lifespan generalization; the inference-time × training-time two-paper pair from CUHK; bracketed against Jialu Li's pediatric adapter to make the lifespan-closure point; explicit list of the five routing variables (age band, speaker identity, layer choice, room, EEG band) that have converged on the same small-learnable-hook-over-frozen-FM pattern.
- **`wiki/entities/dementiabank-pitt-dataset.md`** — Dataset entity. English clinical-interview corpus; Cookie Theft picture description; first wiki appearance; ASR + diagnosis-classification + linguistic-feature-extraction tasks; tabulated June 2026 CUHK benchmark gains.
- **`wiki/entities/jccocc-moca-dataset.md`** — Dataset entity. Cantonese MoCA recordings, CUHK-built; first wiki appearance. Non-Indo-European tonal-language elderly-ASR benchmark; CER (not WER); larger absolute gains than Pitt in both CUHK papers, consistent with the prior that non-English elderly speech is further from the FM pre-training distribution.
- **`wiki/entities/xunying-liu-cuhk-speech-group.md`** — Research-group entity for the CUHK speech line. Core team list from the June 2026 pair (Chengxi Deng first author, Xunying Liu senior); three research threads (elderly/dysarthric, Cantonese-language, learnable-prompt-over-frozen-FM); Asia-Pacific OEM strategy angle (GN / Sonova / Phonak / Cochlear / Widex Cantonese-market exposure).

### Existing wiki page updates (4)
- **`wiki/concepts/auditory-attention-decoding.md`** — Refined the FAConformer entry in Recent Academic Advances with the full extraction (FAA, BAS, +4.9%, 12 baselines, 2 datasets, 3 windows, explicit hearing-systems framing). Added cortex × periphery band-axis duo pairing with BiEAR. Added `efferent-moc-feedback-hearing-ai` to `related:`. `updated:` → 2026-06-16.
- **`wiki/concepts/cross-lifespan-speech-models.md`** — Added "Bracketing the Lifespan" section with a three-way comparison table (Jialu Li pediatric / Deng et al. inference-time elderly / Deng et al. training-time elderly), called out the non-English Cantonese channel and the training-time × inference-time decomposition. Added both elderly sources to `sources:` and the four new pages to `related:`. Updated `Sources` section. `updated:` → 2026-06-16.
- **`wiki/concepts/efferent-moc-feedback-hearing-ai.md`** — Added "The Cortex × Periphery Band-Axis Duo (June 2026)" section pairing FAConformer with BiEAR at opposite ends of the auditory hierarchy along the frequency-band axis. Added FAConformer source to `sources:`. `updated:` → 2026-06-16.
- **`wiki/concepts/brain-aligned-speech-foundation-models.md`** — FAConformer noted as band-axis complement to Gumbel-BEARD's layer-axis; both treated as learnable-hyperparameter routing over structured substrate. `updated:` → 2026-06-16.

### Index and log
- **`wiki/index.md`** — New 2026-06-16 entry prepended to "Last updated"; prior 2026-06-15 entry preserved as "Previously updated". Concepts table: new Elderly Speech Recognition row; AAD / Cross-Lifespan / Efferent-MOC / Brain-Aligned rows refreshed to 2026-06-16 with refined tags. Entities table: three new rows (DementiaBank Pitt, JCCOCC MoCA, Xunying Liu group).
- **`wiki/log.md`** — This entry.

### Editorial notes
- The unifying frame across this ingest: **a small learnable conditioning hook over a frozen / mostly-frozen foundation backbone, routed by a clinical / demographic / structural variable**. The variable now spans age band (Jialu Li), speaker identity (Deng et al. × 2), layer choice (Gumbel-BEARD), room acoustics (Khanagha-Gerkmann), and EEG band (FAConformer). Same primitive, five axes — the strongest single architectural pattern of the June 2026 research wave.
- FAConformer is most interesting as a complement to BiEAR. The two papers operationalise **frequency-band routing at opposite ends of the auditory hierarchy** (BiEAR: periphery-side gain control; FAConformer: cortex-side attention decoding). A future closed-loop system would decode attention from cortical band activity and steer periphery band gain — closing the AAD loop *through* the auditory band structure rather than around it.
- The CUHK elderly pair makes the cross-lifespan generalization frame symmetric. Twelve days separates Jialu Li's pediatric adapter from the Deng et al. elderly twin pair; the same small-learnable-hook pattern is now demonstrated at both lifespan edges. The Cantonese channel is new — almost all elderly-ASR literature is English-only.
- Did not create a dedicated `adapter-tuning` or `prompt-tuning` concept page even though it was floated. The pattern is now better represented as a recurring axis across `cross-lifespan-speech-models`, `elderly-speech-recognition`, `brain-aligned-speech-foundation-models`, and `continual-learning-hearing-ai` — splitting it out would be more taxonomy than content. Reconsider if a fifth or sixth instance lands.
- Did not create a `neuro-steered-hearing-aids` synthesis page; the existing `auditory-attention-decoding` concept page now covers the FAConformer/BiEAR duo and the cortex × periphery framing without needing a separate synthesis.

**Pages touched this ingest: 12** (1 source updated, 2 new sources, 4 new wiki pages, 4 existing wiki pages updated, 1 index update, +1 log entry).

---

## Ingest — 2026-06-16 (Daily hearing+AI digest, 11 sources reviewed)

**Source of operation:** Daily hearing+AI digest for 16 Jun 2026 — 11 candidate sources reviewed; 8 already ingested under existing source files, 3 net-new source files created.

### Source files — already present (skipped, mapped to existing):
- DAL (arXiv:2606.04103) → `dal-differentiable-auditory-loop-google-june-2026.md` (already ingested 4 Jun 2026)
- FPGA Time-Domain DNN SE (arXiv:2606.04221) → `fpga-sudormrf-feasibility-radboud-june-2026.md` (already ingested 4 Jun 2026)
- AI predicts CI language outcomes (92% on pre-implant MRI, 278 children Hong Kong/Australia/US) → `ai-predicts-ci-language-outcomes.md` and `pediatric-ci-language-prediction-transfer-learning-2025.md` (already ingested)
- Phonak Virto R Infinio 2026 Red Dot Award → `phonak-virto-r-infinio-red-dot-april-2026.md` (already ingested)
- Amplifon + GN combination plans → `amplifon-gn-acquisition-2026.md` (already ingested)
- Apple AirPods Hearing Aid expansion to 100+ countries → `airpods-hearing-aid-country-expansion-may-2026.md` (already ingested)
- NeuralAids — Wireless Hearables w/ Programmable Speech AI Accelerators (arXiv:2503.18698) → `wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md` (already ingested)
- FHH 2026 Virtual Conference → `fhh-2026-virtual-conference-may.md` (already ingested)

### Source files — net-new (3):
- **`sources/jamia-open-ci-eligibility-audiogram-2026.md`** — JAMIA Open ML pipeline that flags CI-eligible adults from routine audiograms; outperforms common referral rules; framed as a clinical-utility / deployment-lessons paper, not a benchmark race. Eligibility prediction is a distinct ML problem from outcome prediction; audiogram-as-input is realistic and EHR-deployable. Companion to the audiologist-shortage thread as a workflow-side response.
- **`sources/starkey-omega-ai-update-may-2026.md`** — Starkey blog post consolidating the spring 2026 Omega AI firmware wave. Net-new artifacts vs. the Jan 2026 and May Govt-Services sources: **StarLink Edge LE Adapter** (first OEM-branded LE Audio bridge dongle from a top-5 manufacturer), **DNN 360 +28% speech / +8 dB SNR** marketing claims, **2026 BIG Innovation Award** (distinct from the BIG AI Excellence Awards), **Edge AI + Vision Alliance award** (first hearing-aid recognition from the cross-industry edge-AI consortium that typically recognises Qualcomm/Intel/Nvidia silicon).
- **`sources/auracast-venue-deployments-2026.md`** — HearingTracker venue-tracker wave covering National Theatre Dorfman (Man and Boy trial), Bridge Theatre (London), Sydney Opera House (Australia — second Asia-Pacific Auracast install after the May 26 Seoul jazz club), and CCI at University of the Arts London (first academic-creative-space install). First *flagship* cultural-venue cluster after the April Everyman/Contact regional pilots.

### Existing wiki page updates (4):
- **`wiki/concepts/cochlear-implant-ai.md`** — added new "AI for CI Eligibility / Referral (JAMIA Open, 2026)" subsection under Outcome Prediction; bumped `updated:` to 2026-06-16; added `jamia-open-ci-eligibility-audiogram-2026.md` to `sources:` and to bottom Sources list.
- **`wiki/concepts/automated-audiometry.md`** — added new bullet to "2026 Updates" section pointing to the JAMIA Open audiogram-to-CI-eligibility pipeline as a third audiogram-as-input ML pathway alongside the LLM-PTA and Bisgaard loudness-scaling threads; bumped `updated:` to 2026-06-16; added source.
- **`wiki/entities/starkey.md`** — added new "Omega AI Connectivity & Convenience Update (May 2026)" section immediately above the Government Services section, covering StarLink Edge LE Adapter, DNN 360 claims, 2026 BIG Innovation Award, Edge AI + Vision Alliance award; bumped `updated:` to 2026-06-16; added source.
- **`wiki/concepts/auracast-bluetooth-le-audio.md`** — added new "Flagship Cultural-Venue Deployments — UK + Australia + UAL (Mid-2026)" section above the April UK regional theatre subsection, naming Dorfman / Bridge / Sydney Opera House / CCI UAL; bumped `updated:` to 2026-06-16; added both new sources (venue deployments + Starkey May 2026 for the StarLink LE adapter cross-reference).

### Index and log
- **`wiki/index.md`** — no update; no new wiki pages created.
- **`wiki/log.md`** — this entry.

### Editorial notes
- The high duplication rate (8/11 sources already covered) reflects the daily-digest pipeline working as intended — the wiki is now mostly current with the hearing+AI news flow, and ingest passes catch the genuinely new artifacts cleanly.
- The StarLink Edge LE Adapter is the most strategically interesting net-new artifact today — first OEM-branded LE Audio bridge dongle from a top-5 manufacturer. It's the source-side complement to the device-side Auracast rollout: wearers have LE-Audio hearing aids but their TVs / conference rooms / partners' phones don't. Trihear ClearTV (June 4) plays the same role cross-OEM; the StarLink Adapter is the vendor-locked version. Watch for whether Sonova, Demant, and WSA ship competitors.
- The Auracast flagship-venue wave (Dorfman + Bridge + Sydney Opera House + CCI UAL) is a cleaner-than-expected qualitative shift from "regional pilots" to "cultural flagships" inside two months. The Sydney Opera House install is the most consequential by social-proof reach.
- The JAMIA Open CI-eligibility paper is the venue-shift signal — CI under-referral is now being treated as a *clinical informatics* problem, not an audiology research problem. Different reader base, different deployment pathway. Pairs with the audiologist-shortage workforce-response thread.
- Did not create a new wiki page for any of the three net-new sources — each cleanly extends an existing concept page (CI AI / automated audiometry / Starkey entity / Auracast). The bar for new pages today was the substrate-shift criterion; these are incremental updates to existing substrates.

**Pages touched this ingest: 8** (3 new sources, 4 existing wiki pages updated, +1 log entry).

---

## 2026-06-17 — LinkedIn-Pair Ingest (Band-Axis Triangle + Speech-as-Cognition Pipeline)

**Operation:** Ingested the underlying arXiv sources for the 2026-06-17 daily LinkedIn pair into the wiki.

### Source files — net-new (4):
- **`sources/arxiv-2606-12662-basenet-band-adapted-se-jun-2026.md`** — Martins Gomes & Capman, arXiv:2606.12662, 10 Jun 2026. **BASENet**: CRN-family SE with Bark-scale critical-band partition, scaled-capacity per-band encoder, **linear-complexity cross-band attention** over frequency-pooled per-band representations, inverted residual + dense connectivity backbone. **3.55 PESQ / ~96% STOI / 0.83 M params / 7.3 GMACs** on VoiceBank+DEMAND; **causal variant 3.44 PESQ** surpasses several non-causal baselines — streaming-capable.
- **`sources/arxiv-2606-18054-cognitive-linguistic-features-dementia-jun-2026.md`** — Xu, Kadambi, Goldinger, Berisha, Mueller, Liss, arXiv:2606.18054, 16 Jun 2026. Seven cognitive-linguistic constructs for Cookie Theft; Claude 3.5 Sonnet emits **both score and explanation**; **85% accuracy on ADReSS**; **3.99/5 expert agreement on generated explanations** (the auditability number that matters for a clinical screening tool).
- **`sources/arxiv-2606-18019-llm-dementia-depression-clinical-interviews-jun-2026.md`** — Braun, Rüggeberg, Ranzenberger, Lehfeld, Hillemacher, Bocklet, Riedhammer (TH Nürnberg + Paracelsus Medical Univ), arXiv:2606.18019, 16 Jun 2026. 154 German history-taking interviews; open-weights Mistral 3.1 / DeepHermes / Qwen3 score GDS (dementia) + observer-based Global Depression Scale. **MAE 0.60 depression zero-shot**, **MAE 0.78 dementia with structured feature extraction**, **up to 35% error reduction**; pause-enriched transcripts approach human-transcription quality. Open-weights at clinical-grade quality removes the closed-API blocker for on-device / on-prem deployment.
- **`sources/arxiv-2606-17254-cross-lingual-alzheimer-detection-jun-2026.md`** — Girish et al., arXiv:2606.17254, 16 Jun 2026. Zero-shot cross-lingual Alzheimer detection via **language-invariant multimodal bi-geometric adversarial learning**.

### New wiki pages (2):
- **`wiki/syntheses/band-axis-shared-coordinate-system-june-2026.md`** — three independent groups, eleven days, **same operator (cross-band attention) on the same axis (Bark / critical bands)** at three different layers of the auditory pipeline: BiEAR at the periphery (Jun 5), BASENet at SE (Jun 10), FAConformer at the cortex (Jun 12). Names the unbuilt unified band-axis control bus, the end-to-end three-module demo, and band-conditioned HASPI/STOI/HASQI as the missing benchmark piece.
- **`wiki/syntheses/speech-as-passive-cognition-biomarker-pipeline-june-2026.md`** — the microphone → elderly-adapted ASR → LLM cognitive-linguistic scoring → longitudinal trajectory pipeline became fully populated on arXiv in **nine days, Jun 8 (Jialu Li pediatric adapter) → Jun 15 (CUHK elderly-ASR pair) → Jun 16 (three LLM cognitive-scoring papers)**. Frames the hearing aid as the longest-baseline ear-worn passive cognition sensor any consumer industry has shipped. Names the **three unbuilt pieces**: (1) PCCP regulatory shape with the construct rubric as the anchored artefact while ASR/LLM update inside pre-specified bounds, (2) daily-life prompt substrate beyond Cookie Theft, (3) false-positive clinical-harm cost (anxiety, behavioural change, premature healthcare utilisation, insurance friction) — not addressed by any paper in the nine-day window.

### Existing wiki page updates (4):
- **`wiki/concepts/speech-enhancement-neural-networks.md`** — added "Band-Adapted CRN — BASENet (Martins Gomes & Capman, Jun 2026)" subsection between the Implicit RIR Encoders subsection and the legacy CRN/Conv-TasNet block; added BASENet source to `sources:` frontmatter; bumped `updated:` to 2026-06-17 and rewrote `last_change:` to reflect the BASENet addition and the band-axis-triangle framing.
- **`wiki/concepts/auditory-attention-decoding.md`** — extended the FAConformer "Recent Academic Advances" entry to close the band-axis duo into a triangle with BASENet at the SE mid-stage; added cross-link to the new band-axis synthesis. (No frontmatter sources change — BASENet sits in the SE concept page, not the AAD page.)
- **`wiki/concepts/efferent-moc-feedback-hearing-ai.md`** — extended the "Cortex × Periphery Band-Axis Duo (June 2026)" section with a paragraph noting that the duo became a triangle on Jun 10 with BASENet at the SE mid-stage; linked the BASENet source and the new synthesis.
- **`wiki/concepts/digital-phenotyping-cognitive-decline.md`** — added new "Audio-to-Cognition Pipeline — June 2026 Snapshot" section covering the Xu / Braun / Girish trio; added 3 new sources to `sources:` frontmatter; added 3 cross-links (`elderly-speech-recognition`, `medical-domain-edge-llms`, new synthesis) to `related:` and Related Pages; added 3 new entries to the Sources list; bumped `updated:` to 2026-06-17.
- **`wiki/concepts/elderly-speech-recognition.md`** — added 3 downstream-scoring sources to `sources:` frontmatter and to the Sources list; added the biomarker-pipeline synthesis to `related:`; bumped `updated:` to 2026-06-17. (No new prose section — the page already covers the upstream ASR substrate; the scoring layer lives in `digital-phenotyping-cognitive-decline.md` and the new synthesis.)

### Index update
- **`wiki/index.md`** — added the two new synthesis entries to the Syntheses table; updated the "Last updated" preamble paragraph with a detailed 2026-06-17 ingest summary; pushed the previous 2026-06-16 paragraph down to "Previously updated".

### Editorial notes
- **Did NOT create new concept pages.** Per the surgical-changes rule, each net-new artefact fit cleanly into an existing concept page or one of the two new syntheses. The bar for new concept pages was not met.
- **Did NOT update `concepts/dnn-architectures-hearing-aids.md`** or `concepts/hearing-loss-dementia-link.md` even though both are adjacent. Neither needed structural changes from this ingest — BASENet is a CRN-family extension that lives most naturally in `speech-enhancement-neural-networks.md`, and `hearing-loss-dementia-link.md` is an epidemiology page, not a measurement-pipeline page. The pipeline framing lives in `digital-phenotyping-cognitive-decline.md`.
- **Did NOT create new entity pages** for the TH Nürnberg / Paracelsus Medical Univ Braun et al. group or the Girish et al. group. The Braun group is a credible candidate for a future entity page once a second corroborating paper appears; flagged for the next ingest pass.
- **Open question for next pass:** `arxiv-2606-17254-cross-lingual-alzheimer-detection-jun-2026.md` was ingested with partial extraction (author affiliations, exact headline numbers). A follow-up read of the paper is warranted; the source file flags this explicitly.

**Pages touched this ingest: 11** (4 new sources, 2 new syntheses, 4 existing wiki pages updated, +1 log entry, +1 index update).

---

## 2026-06-17 — Daily hearing+AI digest ingest

**Operation:** Ingested the unique source from the 2026-06-17 daily hearing+AI digest email into the wiki. Other digest items mapped to already-ingested sources and did not need duplicate creation.

### Source files — net-new (1):
- **`sources/arxiv-2606-16464-cnac-se-vq-codec-zhao-madhu-jun-2026.md`** — Zhao & Madhu, arXiv:2606.16464, 15 Jun 2026. Head-to-head **cNAC-SE (continuous-latent)** vs **dNAC-SE (discrete-token)** under the same VQ neural-audio-codec backbone. Fully fine-tuned **cNAC-SE consistently outperforms all dNAC-SE variants** on **DNS-MOS**, leading among generative SE methods. Mechanism claim: VQ's robustness benefit is **clean-prior-constrained regularisation**, **transferable to other continuous methods** independent of the discretisation itself. Splits the codec-prior axis from the discrete-token axis that has been conflated in the LM-based SE literature since 2024.

### Source files — already present, mapped only (8):
- `dal-differentiable-auditory-loop-google-june-2026.md` — arXiv:2606.04103, DAL framework (digest item).
- `fpga-sudormrf-feasibility-radboud-june-2026.md` — arXiv:2606.04221, fixed-point SuDoRM-RF++ on Kria KV260, 9.7 ms first-sample latency.
- `arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md` — In-the-loop deep feedback cancellation.
- `arxiv-2606-05911-dbhn-net-snn-ann-fan-jun-2026.md` — Dual-branch SNN+ANN low-complexity SE.
- `uais-tetteh-se-techniques-hearing-aids-review-2026.md` — Springer UAIS systematic review of SE techniques for hearing aids (digest's "systematic review" item).
- `phonak-ai-excellence-award-march-2026.md` — Phonak Virto R Infinio / Ultra Sphere 2026 AI Excellence Award.
- `airpods-hearing-aid-country-expansion-may-2026.md` — Apple AirPods Pro Hearing Aid feature expansion to Italy, Romania, Czechia (May 12, 2026 MacRumors article).
- `hlaa-2026-convention-louisville-june-2026.md` — HLAA 41st annual convention, Louisville, Jun 10–12 2026.
- `auracast-rollout-2025-2026.md` / `auracast-european-public-venue-rollout-2026.md` (multiple) — Bluetooth SIG 2026 Auracast outlook framing.

### Existing wiki page updates (1):
- **`wiki/concepts/llm-based-speech-enhancement.md`** — added new "**cNAC-SE / dNAC-SE (Zhao & Madhu, Jun 2026) — Codec Prior Without Discretisation**" subsection between the L3-SE section and the "Relationship to Other SE Paradigms" table. Explicitly names the two-axis split (codec-prior vs discrete-token) the Zhao & Madhu result enables, the non-autoregressive continuous-latent SE direction it points to, and the latency-floor implication for any future on-ear deployment of LM-based SE. Added Zhao & Madhu source to `sources:` frontmatter; added `companion-phone-speech-pipeline` to `related:`; added `vector-quantisation` tag; bumped `updated:` to 2026-06-17 with a `last_change:` note.

### Index update
- **`wiki/index.md`** — added a 2026-06-17 (digest) preamble paragraph summarising the cNAC-SE ingest and the page touched; pushed the earlier 2026-06-17 (LinkedIn) paragraph down to "Previously updated".

### Editorial notes
- **Did NOT create new concept or entity pages.** Per the surgical-changes rule, the cNAC-SE result fit cleanly into the existing `llm-based-speech-enhancement.md` page — adding a new concept page would have produced near-duplication with that one.
- **Did NOT update `wiki/concepts/probabilistic-generative-models-hearing-ai.md`** despite the codec-prior cross-reference noted in the source file. The Zhao & Madhu paper does not introduce a new probabilistic-generative *model*; it observes that the existing VQ codec acts as a clean-prior regulariser. The cross-link in `related:` is sufficient — no structural update needed yet. Flagged for re-evaluation if a follow-up paper formalises the codec-as-Bayesian-prior framing.
- **Did NOT touch `concepts/companion-phone-speech-pipeline.md`** despite the non-autoregressive latency-floor implication. Wanted to keep the page focused on already-shipping pipelines; the cNAC-SE direction is two-plus years from a realistic deployment. The cross-link from `llm-based-speech-enhancement.md` makes the connection discoverable without padding the companion-phone page with speculative content.

**Pages touched this ingest: 3** (1 new source, 1 existing wiki page updated, +1 index update, +1 log entry).

## 2026-06-18 — LinkedIn-research ingest (daily LinkedIn pair, 18 Jun 2026)

### Sources created (2)
- **`sources/merkin-prize-cochlear-implant-pioneers-june-2026.md`** — Broad Institute / Merkin Prize Foundation announcement, 17 Jun 2026. Recipients: Graeme Clark, Erwin Hochmair, Ingeborg Hochmair, Michael Merzenich, Blake Wilson. $400,000 jointly for the modern cochlear implant. Hochmair multi-channel hardware 1977, Clark FDA-approved multi-channel 1985, Merzenich neurophysiological basis + Advanced Bionics commercialization, Wilson CIS sound-coding strategy 1989. Ceremony September 2026. Source for LinkedIn Post 1.
- **`sources/arxiv-2606-18611-qc-gan-quaternion-conformer-jun-2026.md`** — Yamauchi, Tamori, Sakai, Yamano, Nitta. arXiv:2606.18611, 17 Jun 2026. Quaternion Conformer GAN + MetricGAN training. Full variant 0.89 M params / PESQ 3.48; **compact variant 0.035 M params (35K) / PESQ 3.23 on VoiceBank+DEMAND** — first 2026 arXiv SE result living natively inside a HA memory budget (<40KB in INT8). Hamilton-product weight sharing collapses ~4 real-valued layers into 1 quaternion-valued layer; phase preserved by construction. Source for LinkedIn Post 2.

### Wiki pages updated (4)
1. **`concepts/cochlear-implant-ai.md`** — Added new "Foundational Layer Recognition — 2026 Merkin Prize" section (placed first under H1). Framed Wilson's 1989 CIS as the persistent fixed-rule signal-processing primitive on top of which the ML/AI layer (Nucleus Nexa Jan 2026, BiEAR/FAConformer/BASENet June 2026 band-axis cluster) is being built. Added Merkin source to `sources:` frontmatter, added `band-axis-shared-coordinate-system-june-2026` to `related:`, added tags `cis-strategy / merkin-prize / foundational-layer`, bumped `updated:` to 2026-06-18 with `last_change:` note.
2. **`concepts/speech-enhancement-neural-networks.md`** — Inserted new "Algebraic Weight-Sharing — QC-GAN (Yamauchi et al., Jun 2026)" section before the BASENet section, with full/compact variant table, Hamilton-product mechanism description, phase-preservation-by-construction framing, and fifth-on-chip-lever cross-link. Added QC-GAN source to frontmatter; added tags `quaternion-conformer / metricgan / hamilton-product / algebraic-weight-sharing`; bumped `updated:` to 2026-06-18 with `last_change:` note.
3. **`concepts/model-compression.md`** — Inserted new "Algebraic Weight Sharing (Quaternion Networks)" subsection under Core Techniques (between Quantization and Knowledge Distillation), explicitly positioned as a structurally different lever from quantization (precision-side) and pruning (post-hoc). Added QC-GAN paper data with variant table, Hamilton-product mechanism, stereo-mic native-quaternion use case, and cross-link to the on-chip-levers synthesis as Lever 5. Added QC-GAN source to frontmatter; added `speech-enhancement-neural-networks` and `on-chip-hearing-ai-levers-june-2026` to related; added tags `quaternion-networks / algebraic-weight-sharing / hamilton-product`; bumped `updated:` to 2026-06-18 with `last_change:` note.
4. **`syntheses/on-chip-hearing-ai-levers-june-2026.md`** — Extended the synthesis from four levers to **five**: added Lever 5 "Quaternion Weight Sharing (arXiv:2606.18611, QC-GAN, Jun 17)" with mechanism description, headline numbers (compact 35K / 3.23 PESQ; full 0.89M / 3.48 PESQ), and implication framing (algebraic constraint is a different lever than precision-side quantization or post-hoc pruning). Updated the "Five Levers" heading + observation paragraph (date range now Jun 4–17). Added quaternion row to the separability table. Updated Unbuilt Pieces to include cross-axis benchmark over five axes, "Quaternion + half-frame-rate combination" and "Stereo-mic native quaternion evaluation" as new entries. Renumbered "fifth axis" → "sixth axis" in the brain-aligned-layer cross-link. Added QC-GAN to `sources:` frontmatter and bottom Sources list. Bumped `updated:` to 2026-06-18 with `last_change:` note.

### Conscious non-decisions
- **Did NOT create a new concept page for "quaternion neural networks."** The QC-GAN result is currently one paper; creating a dedicated page would produce a near-orphan that has to be regularly refreshed against very few new sources. Instead, the quaternion lever is documented in three existing pages (`speech-enhancement-neural-networks`, `model-compression`, `on-chip-hearing-ai-levers-june-2026`) where its three different framings already live. Flag for re-evaluation when a second quaternion-SE / quaternion-classification result for hearing AI lands.
- **Did NOT create a new entity page for any Merkin Prize laureate.** Wilson, Merzenich, the Hochmairs and Clark each individually deserve entity pages — but creating five entity stubs in one ingest produces orphans without the supporting biographical research to make them load-bearing. The Merkin source file itself documents the contributions; entity pages will be created lazily when a future ingest references a specific laureate directly.
- **Did NOT update the `band-axis-shared-coordinate-system-june-2026` synthesis** despite the Merkin / Clark speech-coding cross-link. The band axis synthesis is specifically about the three-paper June 2026 cluster (BiEAR / BASENet / FAConformer); inserting a Merkin/CIS sidebar would weaken its narrative focus. The cross-link from `concepts/cochlear-implant-ai` is sufficient.
- **Did NOT touch the `cochlear-implant-access-economics` synthesis** despite the Merkin announcement being directly upstream of the access story. That synthesis is structured around payer / referral / capacity economics; adding the Merkin-prize material would dilute its argument. The Merkin source file is cross-linked from `concepts/cochlear-implant-ai` for discoverability.

**Pages touched this ingest: 7** (2 new sources, 4 existing wiki pages updated, +1 index update, +1 log entry).

## 2026-06-18 — Daily hearing+AI digest ingest

**Operation:** Ingested net-new sources from the 2026-06-18 daily hearing+AI digest email into the wiki. Other digest items mapped to already-ingested sources and did not need duplicate creation.

### Source files — net-new (2):
- **`sources/bihima-2026-audiologist-survey-launch-jun-2026.md`** — BIHIMA 2026 UK & Ireland audiologist survey launch (Hearing Review, mid-June 2026). First UK/Ireland transatlantic counterpart to the Auditdata US time-crisis instrument. 2026 instrument explicitly pulls on workforce-shortage signals, AI-tooling adoption in clinical workflow, patient-demand shifts (OTC / Apple AirPods / Auracast venues), and system-reform priorities. NHS-vs-independent split is the unique-to-BIHIMA axis with no US analogue.
- **`sources/aware-hearable-v2-ghp-biometric-award-2026.md`** — Aware (same vendor as Aware Defense, FY26 +$7.5M DoD biometric-hearing-protection programme) wins **Best Biometric Hearables Platform Developer 2026** + **Continuous Neural Monitoring Innovation Award 2026** in the GHP Biotech & Lifesciences Awards. Hearable V2 platform integrates **EEG + PPG + ECG + core temperature + bioimpedance + SpO₂** in one deep-in-canal form factor — the civilian commercialisation of the defense-subsidised sensor stack predicted by `large-sensor-models.md` section 7, materialising on the shorter end of the predicted 2–4-year transfer lag.

### Source files — already present, mapped only (6):
- `phonak-infinio-if-design-award-2026.md` — Phonak Infinio Ultra Sphere + Virto R Infinio 2026 iF Design Award (digest's Phonak item).
- `airpods-hearing-aid-country-expansion-may-2026.md` — Apple AirPods Hearing Aid feature country expansion (digest's Apple item).
- `brain-controlled-hearing-nature-neuroscience-may-2026.md` — Nature Neuroscience brain-decoded cocktail-party result (digest's Worth-Watching item).
- `biear-meng-2026-arxiv.md` — BiEAR auditory-inspired binaural front-end (arXiv:2606.06795, digest's BiEAR item).
- `arxiv-2606-02913-generative-vs-discriminative-se-jun-2026.md` — Generative-vs-Discriminative SE benchmark (Shetu et al., digest's Generative-vs-Discriminative item).
- `low-latency-dnn-noise-reduction-frontiers-2025.md` — Frontiers in Audiology & Otology low-latency DNN noise reduction across NH / HI / CI listeners (digest's Frontiers item).

### Existing wiki page updates (2):
- **`wiki/concepts/audiologist-workforce-shortage.md`** — added new section 8 "**BIHIMA 2026 UK & Ireland Audiologist Survey — Transatlantic Counterpart (Jun 2026)**" between the Auditdata section and the Market Impact section. Frames the BIHIMA + Auditdata pair as a transatlantic measurement axis on the back-office-AI thesis. Notes BIHIMA's broader scope (workforce + AI-adoption + demand, vs Auditdata's narrower admin-time-loss focus). Calls out the NHS-vs-independent split as the unique-to-BIHIMA structural question that has no US analogue. Added BIHIMA source to `sources:` frontmatter; added `uk-ireland` tag; added BIHIMA source to bottom Sources list; bumped `updated:` to 2026-06-18 with `last_change:` note.
- **`wiki/concepts/large-sensor-models.md`** — added new "**Defense-to-Civilian Transfer Confirmed — Aware Hearable V2 (Jun 2026)**" sub-section under the existing FY26 DoD section (section 7). Three implications: (1) LSM substrate is now real not speculative — six-modality in-ear platform with consumer ambitions is the most concrete near-term source of multi-modal training data the LSM concept needs; (2) in-canal EEG (if SNR holds) is the consumer-grade surrogate for scalp-electrode setups behind the Nature-Neuroscience cocktail-party-decoding result, bridging lab-grade `auditory-attention-decoding` to a shippable spotlight-mode HA; (3) inherit-vs-replicate question for Sonova/Demant/GN/Starkey determines who controls the LSM training corpus once volumes scale. Added Aware source to `sources:` frontmatter; added `auditory-attention-decoding` to `related:`; added `biometric-hearables` tag; added the same to Related Pages list at bottom; bumped `updated:` to 2026-06-18 with `last_change:` note.

### Index update
- **`wiki/index.md`** — added a 2026-06-18 (digest) preamble paragraph summarising the BIHIMA + Aware Hearable V2 ingest and the two pages touched; pushed the earlier 2026-06-18 (LinkedIn) paragraph down to "Previously updated."

### Editorial notes
- **Did NOT create a new entity page for Aware** despite its growing footprint (FY26 DoD programme, 2026 GHP awards, the in-canal EEG bridge to attention decoding). A dedicated `entities/aware.md` page would be load-bearing if and only if Aware ships at consumer volume and either becomes a third-party platform OEMs license from, or directly competes with Sonova/Demant/GN/Starkey. Both are open questions in the source's "Carry-Forward Flags." Per the entity-page-stub-orphan policy, defer entity creation until a second independent source on Aware lands (commercial volume figure, OEM partnership, or M&A interest). The Aware source file + LSM-page sub-section preserve discoverability without producing a near-orphan.
- **Did NOT create a new concept page for "biometric hearables" or "in-ear sensor fusion."** The Aware V2 result fits cleanly under the existing `large-sensor-models.md` framing (in-ear multi-modal sensors as the substrate for the LSM concept); a separate biometric-hearables page would produce near-duplication with the LSM page's section 7 and adjacent sections of `digital-phenotyping-cognitive-decline`. Flag for re-evaluation if a second independent biometric-hearables vendor (Valencell, Samsung, Apple's next AirPods generation) ships a comparable multi-modal in-canal stack — at that point a comparison-page or concept-page becomes load-bearing.
- **Did NOT update `concepts/auditory-attention-decoding.md`** with the Aware in-canal EEG bridge. The connection is real and structurally important — but the `large-sensor-models` page's new sub-section already documents it from the substrate side, and adding a parallel section on the AAD page would duplicate the same observation without new information. The cross-link in `related:` is sufficient. Will re-evaluate if Aware (or anyone) publishes in-canal-EEG attention-decoding results.
- **Did NOT create a "transatlantic workforce instrument pair" synthesis** for the BIHIMA + Auditdata pairing despite the symmetric structure. The two surveys are not yet *findings* — both are open instruments with publication dates later in 2026. A synthesis page now would be speculation; ingest the aggregated benchmarks when they publish, then write the synthesis on real data.

**Pages touched this ingest: 4** (2 new sources, 2 existing wiki pages updated, +1 index update, +1 log entry).


## 2026-06-20 — LinkedIn-research ingest

**Operation:** Ingested research for the 2026-06-20 daily LinkedIn pair into the wiki.

### Source files — net-new (3):
- **`sources/vcca2026-pre-conference-workshops-jun-19-2026.md`** — VCCA 2026 pre-conference workshops, June 18–19, 2026. Three workshops; Workshops 2 (Saddler/DTU — "A Practical Introduction to Machine Learning for Hearing Science," hands-on Jupyter, materials on GitHub) and 3 (Banerjee/Harvard-MIT — "Computational Models of the Auditory Periphery: From Normal Hearing to Impairment") on June 19. First time the audiology community's flagship virtual conference runs a hands-on ML + computational-periphery lab pair in its foundational pre-conference slot, taught by audiology-systems researchers rather than borrowed from a CS department. Discipline-formation signal that pairs with the WCA Seoul 2026 "computational audiology becomes a track" observation (May 26 post) but is one notch deeper — host community now runs the tutorial.
- **`sources/saddler-mcdermott-2024-nature-comms-temporal-coding.md`** — Saddler & McDermott, Nature Communications 2024. Task-optimized DNNs trained on biophysically faithful cochlear simulators as in-silico models of human auditory perception. High-fidelity auditory-nerve phase locking yields more human-like sound localization and speech perception. Critical finding: temporal-coding precision required to match human behavior is **task-dependent**, not universal — a falsifiable claim about how the auditory system uses neural timing.
- **`sources/saddler-clarity6-2025-individualized-hi-models.md`** — Saddler, Dau, McDermott, Proceedings of the 6th Clarity Workshop 2025. Extension of the task-optimized-DNN program to HI listeners. Jointly optimized localization + recognition through individualized hearing-loss simulations predicts intelligibility. Calibration finding: **majority of variance in the prediction dataset comes from the hearing aid itself, not the listener** — a clarifying, slightly humbling result for "personalized AI" marketing claims.

### Wiki pages created (2):
- **`wiki/concepts/task-optimized-dnn-as-auditory-model.md`** — new concept page formalising the inverse-modelling framing (train DNN end-to-end on a peripheral simulator, compare mistakes to humans, treat the model as a falsifiable scientific hypothesis). Establishes the upstream/downstream relationship with `differentiable-cochlear-models` — task-optimized DNNs say *which* peripheral features are load-bearing and *against which behavioral target*; differentiable cochleae say *how* to train a hearing-aid network through that periphery. Open questions: stimulus-set generalization, per-wearer individualization scaling, multi-task objective design, regulatory PCCP framing of "fitting = training run."
- **`wiki/entities/mark-saddler.md`** — DTU Hearing Systems postdoc, ex-McDermott lab MIT. Three research strands: auditory-nerve phase locking, pitch perception, hearing loss / assistive technology. VCCA 2026 Pre-Conference Workshop 2 instructor. Strategic-relevance section flagged for industry.

### Existing wiki pages updated (1):
- **`wiki/concepts/differentiable-cochlear-models.md`** — new "Upstream Pair: Task-Optimized DNNs as Auditory Models" sub-section explicitly placing the Saddler program as the upstream complement to DAL / CARFAC. Added 2 Saddler sources + `task-optimized-dnn-as-auditory-model` concept + `mark-saddler` entity to frontmatter; new tag `task-optimized-dnn`; bumped updated/last_change to 2026-06-20.

### Existing source page extended (1):
- **`sources/vcca2026-conference.md`** — pre-conference workshop bullet expanded with the three workshop titles, presenters, and a cross-link to the new pre-conference source file; added `date_updated: 2026-06-20`.

### Index update
- **`wiki/index.md`** — added a 2026-06-20 preamble paragraph summarising the LinkedIn-research ingest; pushed the 2026-06-18 (digest) paragraph down to "Previously updated."

### Editorial notes
- **Did NOT create an entity page for Annesya Banerjee** despite her Workshop 3 visibility. Her wiki footprint is currently a single workshop slot — the auditory-periphery-models framing already lives across `differentiable-cochlear-models` and the new `task-optimized-dnn-as-auditory-model`. If she or her Harvard/MIT auditory-periphery program publishes a substantive arXiv paper in the next 6 months, revisit and stand up the entity page.
- **Did NOT create an entity page for Tobias Goehring** despite his VCCA 2026 Session 4A chair role. Same reasoning — a session chair role alone is too thin to support an entity page without risking a near-orphan. Re-evaluate when a Goehring-lab paper lands or his AAA / Cambridge group's program gets a non-conference citation.
- **Did NOT update `entities/clarity-prediction-challenge`** with the Saddler-Dau-McDermott Clarity-6 result. The Clarity-6 paper is positioned as a key sub-finding of the task-optimized-DNN program in the new concept page rather than as a Clarity-Challenge benchmark milestone. The cross-link in `related:` on the new concept page is sufficient; full Clarity-page update reserved for when a Clarity Challenge leaderboard or methods-comparison paper lands.
- **Did NOT create a `wiki/syntheses/discipline-formation-computational-audiology.md`** consolidating the WCA-Seoul-track + VCCA-workshops-foundational-lab observations. Two data points is a near-miss for a synthesis; queue for re-evaluation if a third independent discipline-formation signal lands (e.g. an audiology body's formal ML curriculum requirement, a journal launching an ML-track, or a regulatory body recognising computational audiology as a clinical specialty).

**Pages touched this ingest: 7** (3 new sources, 2 new wiki pages, 1 wiki page updated, 1 source extended, +1 index update, +1 log entry).

## 2026-06-23 — Ad-hoc arXiv ingest (OVC + DDSP-EQ)

**Operation:** Ingested two June 2026 arXiv preprints into the wiki. Both papers are eess.AS preprints from the third week of June, ingested ad-hoc rather than from a daily digest or LinkedIn cycle.

### Source files — net-new (2)

- **`sources/arxiv-2606-23332-ovc-own-voice-cancellation-jun-2026.md`** — Mads Østergaard, Alexander Neergaard Zahid, Karl Ulbæk, Andreas Hansen Bagge, Kenny Falkær Olsen, Rasmus Malik Høegh Lindrup, arXiv:2606.23332, **22 Jun 2026**. Introduces **Own-Voice Cancellation (OVC)** as a first-class far-field SE objective: given an enrolled-speaker embedding, **cancel** that speaker from noisy multi-speaker far-field audio while preserving everything else. **Architecture:** TD-SpeakerBeam baseline + **Mamba-MinGRU masker variant** (Mamba blocks for state-space temporal modelling + MinGRU temporal mixing for a complementary recurrent context profile) + a **linear-RNN auxiliary encoder** replacing the original ConvTasNet-based aux for the enrolled-voice embedding. **2 ms algorithmic latency.** Metrics: SDR + predicted MOS. **Conceptual shift:** own-voice goes from a binary state-machine flag (OVD → program branch in OVP) to a continuous SE conditioning signal (enrolled-voice embedding → continuous masker output). Bridges Phonak/Sonova OVP, Oticon OVD, Signia OVP, and the March 2026 single-mic OVD paper (arXiv:2603.02724) to modern speaker-extraction architectures.
- **`sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md`** — F. Marcos-Macias, M. P. Daza-Llin, M. Camara, J. L. Blanco, arXiv:2606.22563, **21 Jun 2026**, accepted **DAFx26**. A **Differentiable DSP (DDSP)** framework for adaptive room equalisation under time-varying acoustic conditions that **recovers classical filtered-x LMS (FxLMS) as a special case** under specific filter / loss / optimiser choices. Different EQ topologies, perceptual losses, and modern optimisers all plug in without re-deriving update rules. Reported: **~70% reduction in system distance**, **13% worst-case mel-spectral distance improvement** vs unequalised baseline. Open-source. Unifies hearing-aid feedback cancellation, vent-EQ, and room-EQ under a single differentiable operator family. Stacks with HIDVAS (KU Leuven, Jun 12 2026) as the measurement substrate; parallels DAL (Google Research Australia, Jun 4 2026) on the perceptual side.

### Wiki pages created (3)

1. **`wiki/concepts/own-voice-processing.md`** — new concept page consolidating the OVD → OVP → OVC progression. Documents the three primitives (binary detection / state-machine processing / continuous SE conditioning), OEM implementations (Phonak, Oticon, Signia, GN/Starkey), the March 2026 single-mic OVD sim-to-real bridge (arXiv:2603.02724), the June 2026 OVC paper (this ingest), and the open questions around on-chip cost, enrolment workflow, biometric / privacy regulation, single-mic OVC, and interaction with band-axis SE / RIR-conditioning / DDSP-EQ. Cross-linked to speech-enhancement-neural-networks, dnn-architectures-hearing-aids, mamba-architecture, state-space-models, on-device-ml-hearing-aids, companion-phone-speech-pipeline, and the three OEM entity pages.
2. **`wiki/concepts/differentiable-dsp.md`** — new concept page formalising DDSP as a hearing-AI operator family. Three June 2026 beachheads: DDSP-EQ (this ingest), DAL (Jun 4), HIDVAS (Jun 12 — substrate). The unifying architectural move ("re-express analytical algorithms as parametric operators in an autodiff graph"). Why FxLMS recasting matters for hearing aids (unifies feedback cancellation, vent-EQ, and room-EQ). Relationships to neural feedback cancellation (DFC-IL), RIR encoders, differentiable cochleae (DAL), and task-optimized DNNs (Saddler). Open questions on on-chip cost at deployment, stability guarantees for learned topologies, joint training stacks, per-wearer fitting workflow, and regulatory framing.
3. **`wiki/concepts/fxlms-adaptive-filtering.md`** — new concept page on the classical FxLMS algorithm. Algorithm summary, hearing-aid use cases (feedback cancellation, vent/dome compensation, room EQ for streaming audio, multi-mic noise reduction), strengths (cheap, mature, stable), weaknesses recent work targets (locked topology, slow under non-stationary paths, bias under correlated inputs, no native perceptual coupling), the June 2026 DDSP recast, and a three-way table comparing classical FxLMS vs DDSP-EQ recast vs neural DFC-IL.

### Wiki pages updated (5)

1. **`wiki/concepts/speech-enhancement-neural-networks.md`** — added the OVC source to `sources:` frontmatter; added `own-voice-processing` and `differentiable-dsp` to `related:`; added new tags `own-voice-cancellation / ovc / td-speakerbeam`. Inserted a new "Own-Voice Cancellation — OVC (Østergaard et al., Jun 2026)" section just before the BASENet section, with full architecture description (TD-SpeakerBeam + Mamba-MinGRU + linear-RNN aux), 2 ms latency callout, OVP→OVD→OVC framing, and stack-up notes for band-axis SE, RIR-conditioning, and DDSP-EQ. Bumped `updated:` to 2026-06-23 with `last_change:` note.
2. **`wiki/concepts/acoustic-feedback-cancellation.md`** — added the DDSP-EQ source to `sources:` frontmatter; added `differentiable-dsp`, `fxlms-adaptive-filtering`, `room-aware-dereverberation` to `related:`; added tags `fxlms / ddsp`. Inserted a new "The Classical FxLMS Track — DDSP Recast (Marcos-Macias et al., Jun 21 2026)" section with a three-way table comparing classical FxLMS vs DDSP-EQ recast vs neural DFC-IL, and a note that a shipping product likely runs all three in a complementary stack. Extended Open Questions with joint-training and stability-proof items. Added the DDSP-EQ source to the bottom Sources list. Bumped `updated:` to 2026-06-23 with `last_change:` note.
3. **`wiki/concepts/room-aware-dereverberation.md`** — added the DDSP-EQ source to `sources:` frontmatter; added `differentiable-dsp / fxlms-adaptive-filtering / acoustic-feedback-cancellation / hidvas-dataset` to `related:`; added tags `ddsp / fxlms`. Inserted a new "Adaptive-Filter Parallel — DDSP-EQ (Marcos-Macias et al., Jun 21 2026)" section with a two-row table contrasting RIR-encoder (SE side, continuous embedding conditioning) vs DDSP-EQ (adaptive-filter side, parameterised differentiable filter). Bumped `updated:` to 2026-06-23 with `last_change:` note.
4. **`wiki/concepts/hidvas-dataset.md`** — added the DDSP-EQ source to `sources:` frontmatter; added `differentiable-dsp / fxlms-adaptive-filtering / acoustic-feedback-cancellation` to `related:`; added tags `ddsp / fxlms`. Inserted a new "DDSP-EQ Use Case (Marcos-Macias et al., Jun 21 2026)" section calling out HIDVAS's **4 dome configurations × 4 reverberation conditions with impulse responses** as the natural training substrate for the DDSP-EQ framework, with per-dome personalisation studies and joint-training-with-DFC-IL as the architecturally straightforward but unpublished extensions. Bumped `updated:` to 2026-06-23 with `last_change:` note.
5. **`wiki/concepts/differentiable-cochlear-models.md`** — added the DDSP-EQ source to `sources:` frontmatter; added `differentiable-dsp / fxlms-adaptive-filtering / room-aware-dereverberation` to `related:`; added tag `ddsp`. Inserted a new "Acoustic-Physical-Side DDSP Pair (Added 2026-06-23)" sub-section pairing DAL on the perceptual side with DDSP-EQ on the acoustic-physical side; argues 2026 is the year adaptive hearing processing moves from per-component analytical rules to a single end-to-end differentiable graph spanning cochlea (DAL), room/vent (DDSP-EQ), feedback (DFC-IL), and downstream SE. Bumped `updated:` to 2026-06-23 with a new `last_change:` note that preserves the 2026-06-20 task-optimized-DNN context.

### Index update

- **`wiki/index.md`** — added a 2026-06-23 preamble paragraph summarising the OVC + DDSP-EQ ingest with both source IDs, both papers' headline numbers, the three new concept pages, and the five existing concept pages updated. Pushed the 2026-06-22 (digest) paragraph down to "Earlier". Added three new rows to the Concepts table (`own-voice-processing`, `differentiable-dsp`, `fxlms-adaptive-filtering`). Bumped the `Updated` column for the five modified concept pages (`speech-enhancement-neural-networks`, `acoustic-feedback-cancellation`, `differentiable-cochlear-models`, `room-aware-dereverberation`, `hidvas-dataset`) to 2026-06-23 and extended their tag lists.

### Editorial notes

- **Did NOT create a new synthesis page for the "everything becomes differentiable in June 2026" thread** (DAL + DDSP-EQ + DFC-IL + RIR-encoders + DAL + task-optimized DNNs as a single discipline-formation moment). The pattern is real and named in the new `differentiable-dsp` concept page's "Unifying Architectural Move" section + the new sub-section on the `differentiable-cochlear-models` page. A standalone synthesis is queued for re-evaluation if a fourth independent differentiable-block paper lands in July (candidates: differentiable beamformer, differentiable AGC, differentiable scene classifier as an end-to-end soft router). Two-paper synthesis is a near-miss; wait for the third or fourth datapoint.
- **Did NOT create an entity page for the Østergaard et al. authorship cluster.** The author list looks like a Demant/Oticon-adjacent Danish group (Lindrup is the senior co-author), but the affiliations aren't named in the available metadata. Per the entity-page-stub-orphan policy, defer until a second corroborating paper or a confirmed lab/company affiliation lands.
- **Did NOT create an entity page for the Marcos-Macias / Daza-Llin / Camara / Blanco group.** Same reasoning — single paper, no published affiliation in the metadata, and the DDSP-EQ contribution lives most usefully in the operator-family concept page rather than under a thin entity page.
- **Did NOT update the OEM entity pages (`entities/phonak.md`, `entities/demant-oticon.md`, `entities/ws-audiology-signia.md`)** with the OVC framing. The new `own-voice-processing` concept page documents the OEM landscape and links back to each entity page in its `related:` block; adding a parallel OVC section to each OEM page would produce three near-duplicate inserts. Re-evaluate if an OEM publicly announces an OVC-style product or if a corresponding patent / press release lands.
- **Did NOT update the on-chip-levers synthesis (`syntheses/on-chip-hearing-ai-levers-june-2026.md`)** with the OVC or DDSP-EQ result. OVC is an SE-architectural addition rather than a new on-chip lever (the five-lever cluster is specifically about model-size / latency / throughput axes); DDSP-EQ is also not a new lever per se (it's an operator-family recast). Both fit better in the new concept pages than as extensions to that synthesis. Flagged for re-evaluation if a follow-up DDSP paper reports an on-chip footprint number that materially affects the lever taxonomy.
- **Did NOT update the band-axis synthesis (`syntheses/band-axis-shared-coordinate-system-june-2026.md`)** despite OVC and DDSP-EQ both being band-axis-friendly. The synthesis is tightly scoped to the BiEAR / BASENet / FAConformer three-paper June 2026 cluster; folding in OVC + DDSP-EQ would dilute its narrative. Cross-discoverability via the new concept pages is sufficient.

**Pages touched this ingest: 11** (2 new sources, 3 new wiki pages, 5 existing wiki pages updated, +1 index update, +1 log entry).

## 2026-06-23 — Daily hearing+AI digest ingest (Phonak AutoSense OS 7.0)

**Operation:** Ingested the most material net-new vendor announcement surfaced by today's daily digest email (sent to door.punch_4o@icloud.com, ~700 words, 2 arXiv papers + 4 industry news + 2 AI/ML synthesis notes + 2 worth-watching items + 6 quick stats). The two arXiv preprints featured in the digest body (OVC + DDSP-EQ) were already ingested in the earlier 2026-06-23 ad-hoc ingest above; the Veterans Hearing Aid Improvement Act and the Sonova FY 2025/26 results were already in the wiki (`veterans-hearing-aid-improvement-act-house-jun-2026.md` and `sonova-fy-2025-26-results-may-2026.md`); the HearingLife Fairfax retail-center opening (Jun 16) and the Starkey Omega AI connectivity refresh were both judged too thin for net-new source files per the "prefer updating existing pages over creating near-duplicates" convention.

### Source files — net-new (1)

- **`sources/phonak-autosense-os-7-jun-2026.md`** — Phonak whitepaper, announced June 2026 as part of the Infinio Ultra firmware refresh. AutoSense OS 7.0 expands the scene-classifier training database **18×** vs v6.0, delivering **+24%** classification precision, **+30%** battery efficiency, **one-step Bluetooth pairing**, and faster feedback management. Same firmware push brings **Spheric Speech Clarity 2.0** to Sphere models. Free firmware upgrade via Target for existing Infinio / Infinio Sphere wearers. Establishes a ~twice-a-year cadence of post-deployment model updates (Oct 2025 → Jun 2026).

### Wiki pages updated (1)

1. **`wiki/entities/phonak.md`** — added the new source to `sources:` frontmatter; bumped `updated:` to 2026-06-23 with `last_change:` note. Expanded the "Firmware & Ongoing Model Updates" section with the AutoSense OS 7.0 bullet (18× scene database, +24% precision, +30% battery efficiency, one-step BT pairing, Spheric Speech Clarity 2.0 on Sphere) and added an explicit framing that AutoSense OS sits *upstream* of the DEEPSONIC AI feature blocks — it's the soft router that decides which block(s) to engage. Added the source to the bottom Sources list.

### Editorial notes

- **Did NOT create a new concept page for AutoSense OS / automatic scene classification.** The scene-classifier concept is sufficiently covered across `dnn-in-hearing-aids.md`, `on-device-ml-hearing-aids.md`, and the OEM entity pages. Re-evaluate if a second OEM ships a comparable named scene-classifier upgrade in the next 60 days (Oticon "Intent Aware" refresh, Signia "Augmented Focus" next-gen, etc.) — at that point a horizontal `automatic-scene-classification` concept page would have three datapoints and could pull cross-OEM comparison work out of the entity pages.
- **Did NOT create a source file for the HearingLife Fairfax retail opening (Jun 16, 2026).** A single retail-center ribbon-cutting doesn't materially change the Demant retail-footprint story; folded into the Demant/Oticon entity page on the next substantive Demant ingest.
- **Did NOT create a source file for the Starkey Omega AI connectivity refresh (Auracast assistant + Google Fast Pair + Push-to-Talk).** This is a minor extension of the Jan 2026 Edge AI Auracast firmware refresh already documented in `entities/starkey.md`. Re-evaluate if Starkey publishes a whitepaper on the connectivity stack or if Push-to-Talk turns into a named feature with clinical/UX data.
- **Did NOT update `entities/sonova-ag.md` with the AGM / FY 2025/26 7% growth bullet** — `sources/sonova-fy-2025-26-results-may-2026.md` and the existing Sonova entity page already cover the May 20 results release; the Jun 16 AGM is the formal vote, not a new disclosure.
- **Did NOT update `concepts/dnn-in-hearing-aids.md` or `concepts/on-device-ml-hearing-aids.md`** with the AutoSense OS 7.0 detail. The Phonak entity page is the natural home for OEM-specific firmware-update milestones; folding model-update bullets into the cross-OEM concept pages would dilute their abstraction level. Re-evaluate at the next horizontal concept-page lint pass.
- **Did NOT update `wiki/index.md` Phonak row date** in this ingest. The earlier 2026-06-23 ad-hoc OVC + DDSP-EQ ingest already pushed the index header to today's date; the Phonak entity row's Updated column carries a stale 2026-05-05 date and should be bumped to 2026-06-23 at the next index sweep along with the new `last_change` note in the entity page header.

**Pages touched this ingest: 3** (1 new source, 1 wiki page updated, +1 log entry).
