---
title: "Mapping Whisper Representations to Human ECoG Responses with Interpretable Time-Resolved Neural Encoding"
type: source
source_type: arxiv-preprint
date_published: 2026-06-01
date_ingested: 2026-06-03
authors: [Matteo Ciferri, Tommaso Boccato, Michal Olak, Matteo Ferrante, Nicola Toschi]
identifier: arXiv:2606.02305
url: https://arxiv.org/abs/2606.02305
venue: arXiv (q-bio.NC / cs.HC); presented at ICLR 2026 Workshop on Representational Alignment (Re-Align)
tags: [whisper, speech-foundation-models, ecog, brain-alignment, representational-alignment, auditory-cortex, phoneme-encoding, layer-selection, neural-encoding, brain-models]
---

# Mapping Whisper Representations to Human ECoG Responses with Interpretable Time-Resolved Neural Encoding

## Bibliographic
- **Authors:** Matteo Ciferri, Tommaso Boccato, Michal Olak, Matteo Ferrante, Nicola Toschi
- **Posted:** 1 June 2026
- **arXiv:** 2606.02305 (q-bio.NC, cs.HC)
- **Venue:** ICLR 2026 Workshop on Representational Alignment (Re-Align)
- **URL:** https://arxiv.org/abs/2606.02305

## Question
How do internal representations of a speech foundation model (Whisper) align with cortical responses recorded during naturalistic speech listening?

## Approach
A time-resolved neural encoder is built on top of Whisper embeddings, combining the speech embeddings with a **recurrent temporal model** and **soft attention**. This allows layer-by-layer assessment of brain-model alignment using intracranial electrophysiology (ECoG).

## Key Findings
1. **Intermediate Whisper layers correlate most strongly** with ECoG responses in auditory and language-responsive cortex — not the encoder's final hidden state and not its earliest layers.
2. **Temporally structured encoders outperform** simple linear mappings from the same Whisper representations.
3. **Attention maps reveal temporally local alignment** between speech embeddings and neural responses.
4. **Phoneme-category organization** is recoverable across ECoG electrodes and is anatomically coherent — i.e., the encoding-informative electrodes group spatially in a way that matches phoneme categories.

## Why This Matters for Hearing-Aid AI
Speech foundation models are increasingly distilled / quantized / adapter-tuned for hearing-aid downstream tasks (speech enhancement, intelligibility prediction, attention-aware processing). Standard practice is to tap **the last hidden state** of the encoder for downstream features. This paper provides empirical evidence that **intermediate layers** are more representative of how the cortex itself processes speech.

Three direct implications:
- **Layer choice** is a free hyperparameter that hearing-AI engineering teams have largely ignored.
- **Brain-aligned losses** become tractable without recording ECoG at deployment time: anchor the downstream model to the layer the cortex correlates with.
- The next moat in hearing-AI may be *which* layer of *which* foundation model one taps, not *which* foundation model one adopts.

## Caveats
- ECoG cohort and dataset details not fully extracted here — primary source review needed before any clinical claim.
- Workshop paper (Re-Align at ICLR 2026), not yet a full peer-reviewed venue paper.
- Cross-subject generalization is not yet characterized in the extract retrieved.

## Used In
- [[wiki/concepts/brain-aligned-speech-foundation-models.md]] (new)
- [[wiki/concepts/foundation-model-fusion-speech.md]] (update — layer-selection axis)
- [[wiki/concepts/auditory-attention-decoding.md]] (cross-reference — implicit brain model on the encoder side)
- [[wiki/syntheses/pretraining-corpus-as-moat-hearing-ai.md]] (update — layer-tap as moat)
