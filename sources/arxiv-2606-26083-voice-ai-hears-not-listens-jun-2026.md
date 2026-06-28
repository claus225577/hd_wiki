---
title: "Real-Time Voice AI Hears but Does Not Listen"
type: source
source_type: arxiv-preprint
date_published: 2026-06-24
date_ingested: 2026-06-28
authors: [Martijn Bartelds, Federico Bianchi, James Zou]
identifier: arXiv:2606.26083
url: https://arxiv.org/abs/2606.26083
venue: arXiv eess.AS
tags: [voice-ai, paralinguistics, vocal-affect, perception-action-gap, safety, hearing-aid-salience, conversational-ai, emotional-intelligence]
---

# Real-Time Voice AI Hears but Does Not Listen

## Bibliographic
- **Authors:** Martijn Bartelds, Federico Bianchi, James Zou
- **Affiliations:** Stanford University (Bianchi, Zou) and collaborators
- **arXiv ID:** 2606.26083 (eess.AS)
- **Submitted:** 24 Jun 2026
- **URL:** https://arxiv.org/abs/2606.26083

## Headline Claim
Four production voice-AI systems show a **perception–action gap**: vocal-affect cues (fear, distress, sarcasm) are detectable from the audio — the systems can *name* the emotional state when prompted — yet the same systems do not let those cues influence high-stakes decisions, approving wire transfers from frightened callers and ending calls with distressed users.

## Methodology
- Four production-grade real-time voice-AI systems were evaluated on tasks where vocal delivery should change the rational action (financial requests in fearful voice; complaint calls in distressed voice; sarcastic acknowledgements).
- Two parallel evaluations:
  1. **Action evaluation** — what does the system *do* given the audio?
  2. **Naming evaluation** — when explicitly asked, can the system identify the emotional state in the audio?
- Comparison shows perception is mostly intact; action is not.

## Reported Findings
- Production voice-AI systems **privilege lexical content over paralinguistic delivery** in decision-making.
- Concrete failure modes documented:
  - Wire-transfer approvals despite clear fear cues.
  - Call-ending behaviours despite clear distress cues.
- **3 of 4 systems correctly identified** the emotional state they had just ignored when prompted directly.
- The gap is framed as **perception vs action**, not perception vs ignorance.

## Why This Matters for Hearing-Aid R&D
1. **Same gap, different industry.** Hearing aids amplify, compress, transmit. Modern HAs have far better *perception* (DNN-NR, neural beamforming, foundation-model SE) than they have *action policy* — what they *do* with what they hear has barely moved.
2. **Salience-aware processing is the obvious next compression rule.** Spousal frightened question vs polite-stranger question are processed identically today. Salience-modulated gain is a credible next NR/WDRC interface.
3. **Vocal-affect is the unused wellness signal.** Cortisol-correlated vocal features are extractable from the existing mic signal. The HA wellness story has been step-count and fall-detection; affect is bigger.
4. **Regulatory category waiting to happen.** "Heard but did not act" precedent in voice-AI fintech will flow into hearing devices that route, amplify, or summarise calls.
5. **Foundation-model alignment problem maps cleanly to HA fitting.** "The model knew, but did not act on what it knew" is the same complaint hearing-aid wearers have voiced for decades about their devices in social settings.

## Limitations / Open Questions
- Four systems only — narrow sample of the production landscape.
- Action-policy is a function of system prompt + tool-use orchestration as much as of the audio model; the paper does not separate the two contributions cleanly.
- Hearing-impaired listeners may have *more* difficulty conveying vocal affect (e.g. own-voice monitoring loss); the implication for HA design is the inverse problem to the one the paper investigates.
- No connection drawn to clinical paralinguistics or to mental-health monitoring through speech — that connection is the obvious next paper.

## Cross-References Inside This Wiki
- `wiki/concepts/vocal-affect-paralinguistics-hearing-ai.md` (new) — primary concept.
- `wiki/concepts/salience-aware-gain.md` (new) — direct downstream of the perception-action gap framing.
- `wiki/syntheses/ai-understanding-gap-hearing-industry.md` — the synthesis page this paper most directly extends.
- `wiki/concepts/large-sensor-models.md` — voice-AI agents = on-ear voice-AI agents in 18-24 months.
- `wiki/concepts/turn-taking-prediction-hearing-ai.md` — affect is the missing dimension of turn-taking models.
- `wiki/concepts/listening-effort-evaluation.md` — listener effort and speaker affect are coupled.
- `wiki/concepts/dyadic-interaction-preservation.md` — the dyad is where affect shows up.
- `wiki/concepts/eu-ai-act-medical-devices.md` — "heard but did not act" is an EU AI Act high-risk category candidate.
- `wiki/syntheses/clinical-ml-convergence-june-2026.md` — voice-affect maps into clinical paralinguistics for depression / anxiety screening.
