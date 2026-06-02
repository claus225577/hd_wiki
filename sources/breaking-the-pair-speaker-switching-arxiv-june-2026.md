---
title: "Breaking the Pair: Evaluating Dyadic Interaction via Speaker Switching"
type: source
source_type: arxiv-paper
authors: [Nishchay Nilabh, Neeraj Kumar Sharma]
institution: not disclosed in arXiv metadata
arxiv_id: 2606.02185
url: https://arxiv.org/abs/2606.02185
published: 2026-06-01
ingested: 2026-06-02
tags: [evaluation-metrics, conversational-entrainment, dyadic-interaction, speaker-switch-test, dyadic-distance-matrix, candor-corpus, librispeech, dialogue-modelling, hearing-aid-evaluation]
---

# Breaking the Pair: Evaluating Dyadic Interaction via Speaker Switching

## Bibliographic
- **Authors:** Nishchay Nilabh, Neeraj Kumar Sharma
- **arXiv:** 2606.02185 (cs.CL / eess.AS)
- **Submitted:** 1 June 2026

## Abstract (paraphrased)
The paper introduces a controlled diagnostic for whether dialogue representations capture genuine dyadic coadaptation between two speakers, as opposed to individual speaker traits. The authors propose the **Dyadic Distance Matrix (DDM)** and the **speaker-switch test**: replace one speaker's conversational turns with turns from an unrelated speaker drawn from a different conversation. This preserves turn-level statistics while destroying the original dyadic coadaptation. The framework was evaluated across four embedding types and multiple classifiers (including ResNet-50) on the CANDOR corpus (naturalistic conversation) and LibriSpeech (read speech). Real DDMs are consistently discriminable from speaker-switched DDMs — with **higher discriminability on read speech than on naturalistic conversation**.

## Key Extraction

### Problem
- Speech/dialogue systems are typically evaluated on per-utterance or per-speaker metrics. These cannot distinguish a model that captures interaction dynamics from one that only captures individual speaker traits.
- Conversational entrainment (lexical, prosodic, turn-timing alignment between interlocutors) is the substrate of natural dialogue and is precisely what hearing-impaired listeners struggle to follow.

### Method
- **Dyadic Distance Matrix (DDM):** a representation of a two-speaker conversation that captures inter-speaker distance patterns over the course of the dialogue. Designed to isolate interaction structure from individual-speaker statistics.
- **Speaker-switch test:** replace one speaker's turns with turns from an unrelated speaker from a different conversation.
  - Preserves: per-speaker statistics, turn lengths, distribution of turn-level features.
  - Destroys: dyadic coadaptation, entrainment, mutual conversational structure.
- Classifier task: distinguish real DDMs from speaker-switched DDMs.

### Experimental Setup
- **Corpora:**
  - **CANDOR** — large naturalistic-conversation corpus.
  - **LibriSpeech** — read speech, used as a comparison (less true dialogue, more individual reading).
- **Embeddings:** 4 embedding types compared.
- **Classifiers:** multiple, including ResNet-50.

### Key Finding
- Real vs switched DDMs are reliably discriminable.
- **Discriminability is higher on read speech than on naturalistic conversation** — the opposite of where genuine dyadic structure should live.
- Read this as: current speech/dialogue representations are *less* sensitive to true dyadic entrainment than to spurious read-speech regularities.

### Interpretation
- The speaker-switch test is the first methodologically clean diagnostic of whether a representation captures conversation versus individual-speaker traits.
- The "weaker on naturalistic" result is the most important number in the paper — it implies that current embeddings, including foundation-model speech embeddings, do not yet model conversational entrainment well.

## Why This Matters for Hearing AI
- The dominant evaluation stack for hearing-aid SE is signal-level (PESQ, STOI, HASPI, HASQI, SI-SNR), perceptual surrogates (DNS-MOS), or word-level (WER, CPC3-style intelligibility prediction). None of these test whether the *interaction* is preserved.
- Hearing-aid wearer complaints in the field are almost never "I cannot follow read speech." They are "I cannot follow the conversation."
- The actionable application: run the speaker-switch test on the **input and the output** of a hearing-aid SE pipeline. If the swap discrimination signal collapses after enhancement, the SE pipeline is destroying interactional structure while improving signal-level metrics.
- This adds a fifth axis (interaction preservation) to the field's evaluation stack — alongside signal, perceptual, lexical, and neural-attention metrics.

## Relationship to Recent Work
- **Complement to:** Pichora-Fuller (FUEL, ISA Aram Glorig Award WCA Seoul May 26 2026) — communication accessibility as the construct that signal-level metrics miss.
- **Complement to:** Nakazawa frame-aligned-fusion (arXiv:2605.23619, May 22) and Nakazawa word-level (arXiv:2605.23604, May 22) — those moved the lever on encoder × fusion × granularity; this moves it on **what we evaluate at all**.
- **Adjacent to:** L3-SE linguistic hallucination (arXiv:2605.08608) — both make the same general point: current metrics flatter models that fail in human-relevant ways.

## Open Questions
- Does the speaker-switch test pre/post HA-SE actually correlate with subjective conversation-following ratings in HI listeners?
- Can DDM-style metrics be computed online, on-device, as a runtime signal for personalization?
- How does DDM behave on small group conversation (>2 speakers), which is where HA wearers struggle most?

## Sources Used
- arXiv abstract page and PDF, 2606.02185, accessed 2 June 2026.
