---
title: "Rethinking Continual Learning for Speech and Audio: A Representation-Centric Taxonomy and Open Problems"
type: source
source_type: arxiv-paper
authors: [Yang Xiao, Siyi Wang, Eun-Jung Holden, Ting Dang]
arxiv_id: 2605.24863
url: https://arxiv.org/abs/2605.24863
published: 2026-05-24
ingested: 2026-05-27
status: work-in-progress (4 pages, 1 figure as of v1)
tags: [continual-learning, speech-foundation-models, representation-learning, on-device-adaptation, personalization, hearing-ai, non-stationary-environments]
---

# Rethinking Continual Learning for Speech and Audio: A Representation-Centric Taxonomy and Open Problems

## Bibliographic
- **Authors:** Yang Xiao, Siyi Wang, Eun-Jung Holden, Ting Dang
- **arXiv:** 2605.24863 (eess.AS / cs.SD)
- **Submitted:** 24 May 2026
- **Status (v1):** work-in-progress, 4 pages, 1 figure

## Core Thesis
Continual learning (CL) research for speech and audio systems should be reorganized **around how representation geometry evolves under non-stationary acoustic conditions** rather than around the canonical CL setup of cleanly separable tasks. The hidden mismatch is that **speech foundation models encode highly entangled, continuous representations that jointly encode linguistic, speaker, and paralinguistic factors in a shared latent space** — they do not split cleanly into tasks the way image classification benchmarks do.

## Key Extraction

### The Mismatch
- **Standard CL assumptions:** discrete tasks, clean boundaries, known task identity, often a single output head per task.
- **Speech reality:** continuously drifting acoustic conditions (speaker, channel, room, noise, language), jointly carried in one entangled latent space; no clean task boundaries.
- **Consequence:** rehearsal buffers, regularization (EWC etc.), parameter isolation, and adapter routing — all standard CL toolkits — were designed for cleanly separable tasks and don't naturally fit speech foundation models.

### Proposed Taxonomy (Representation-Centric)
Organize CL methods by **how they alter and preserve the shared representation geometry** under non-stationary inputs:
- Methods that lock geometry (regularize toward old representations)
- Methods that grow geometry (add capacity in directions of new variation)
- Methods that re-coordinate geometry (rotate/re-align without adding capacity)
- Methods that prune / consolidate geometry between sessions

### Open Problems Identified
- How to evaluate CL when the underlying representations are entangled across linguistic / speaker / paralinguistic axes.
- How to maintain language and accent coverage as new data streams in from a single speaker / device.
- How to define forgetting at the representation level when there are no clean task boundaries.
- Memory and update budgets for on-device / wearable deployment.
- The role of foundation-model adaptation interfaces (LoRA, prefix tuning, soft prompts) in CL.

## Why It Matters for Hearing-Aid AI
1. **Personalization is continual learning.** Every fitting visit, every user-toggled adjustment, every in-situ EMA response is an incremental update to a shared user-and-environment representation. The hearing-aid stack has been calling this "personalization" for two decades but has imported almost no formal CL methodology.
2. **Non-stationarity is the default, not the edge case.** Wearer hearing changes with age, environment changes with life, preferences change with experience, device state changes with battery / temperature / earmold drift. Stationary assumptions are routinely violated.
3. **Entanglement matters more here than elsewhere.** The hearing-aid wearer's "preference" is jointly speaker × room × intent × listening history. A representation-centric CL framing handles this natively; a task-centric one does not.
4. **Unit of personalization shifts from parameter to representation.** OEM stacks have added parameter handles (gain, scene weights, push-to-X buttons) for a decade. The paper's framing argues the next-generation update should target the shared latent representation directly.
5. **No mention of audiology in the paper.** That is the field gap — and the opportunity for a hearing-care team to write the canonical CL case study.

## Implications for OEM Roadmaps
- **From per-parameter handles → representation deltas.** Telemetry should record what shifted in the *representation* during a session, not only which slider moved.
- **HA power budgets and CL update cost.** A standard CL update is gradient-based; HA chips have neither the FP throughput nor the energy budget for in-the-ear updates. The natural split is: collect deltas on-device, consolidate on the paired phone, deploy to chip via OTA.
- **Multi-user data schemas re-enter.** A representation drifting under conversational partners and shared environments is structurally a multi-agent CL problem (cf. care-partner dyad models).

## Relations
- Sibling to speech-foundation-model literature on adaptation (Whisper/Canary/Voxtral/Qwen3-ASR family).
- Directly relevant to lifespan-stratified evaluation (age-domain shift is a CL problem).
- Methodologically adjacent to the Bayesian / probabilistic-generative HA framing (in-situ updates as posterior refinement).
- Cross-references the on-device-ML and companion-phone-pipeline split discussed in May 2026 wiki entries.

## Open Questions for the Hearing-Care Field
- What does a representation-delta telemetry record look like? Schema, frequency, privacy envelope?
- Which adaptation interface (LoRA-style adapters, prompts, full-tensor updates) survives HA power budgets when consolidated on the companion phone?
- Can EMA-style ratings, push-button events, and acoustic-context features serve as the supervision signal for representation updates, or do we need a denser label?
- Where does the regulator (FDA / EMA / notified body) sit on "the device updates its own representation in the field"? The medical-device regulatory frame currently assumes a locked model.
