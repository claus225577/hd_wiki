---
title: "Real-time brain-controlled selective hearing enhances speech perception in multi-talker environments"
authors: [Vishal Choudhari, Nima Mesgarani, et al.]
date_published: 2026-05-11
date_ingested: 2026-05-12
url: https://www.nature.com/articles/s41593-026-02281-5
doi: 10.1038/s41593-026-02281-5
type: academic-paper
venue: Nature Neuroscience
tags: [auditory-attention-decoding, aad, ecog, intracranial-eeg, cocktail-party, neurosteering, closed-loop, hearing-aids]
---

# Real-time Brain-Controlled Selective Hearing — First Closed-Loop Human Demonstration

## Summary

First peer-reviewed demonstration of a real-time closed-loop brain-controlled hearing system in humans. The Mesgarani lab (Columbia Zuckerman Institute / Fu Foundation School of Engineering) used high-resolution intracranial electroencephalography (ECoG) in patients undergoing neurosurgery for epilepsy to decode which of multiple simultaneous speakers the listener was attending to, and dynamically amplify that speaker in real time. Published in *Nature Neuroscience* on 11 May 2026.

## Key Result

Across multiple experiments (guided attention and self-initiated attention shifts), the closed-loop system:
- Improved speech intelligibility relative to no-enhancement baselines
- Reduced listening effort
- Was consistently preferred by subjects

This is positioned as the first paper to show that auditory attention decoding (AAD) can provide a *real-time perceptual benefit*, rather than offline classification accuracy alone.

## Methodology

- **Signal modality:** Intracranial ECoG via pre-implanted surgical electrodes (not wearable EEG).
- **Population:** Epilepsy patients already implanted for clinical purposes; exact n not reported in lay coverage.
- **Decoding:** Real-time machine-learning algorithm tracking which voice the listener is attending to (cortical envelope tracking + speaker separation).
- **Audio stimulus:** Two overlapping conversations played simultaneously; system enhances the attended talker and suppresses the others.
- **Collaborating institutions:** Hofstra Northwell School of Medicine; Feinstein Institutes for Medical Research; NYU School of Medicine; UCSF Department of Neurological Surgery.

## Key Quotes

- Mesgarani (senior): "This science empowers us to think beyond traditional hearing aids, which simply amplify sound, toward a future where technology can restore the sophisticated, selective hearing of the human brain."
- Choudhari (first): "For the first time, we have shown that such a system that reads brain signals to selectively enhance conversations can provide a clear real-time benefit."

## Significance for Hearing Aid AI

- **Loss-function shift:** Current hearing-aid AI optimizes signal-side objectives (denoise the scene). This work makes the *listener's attention* the supervision signal — a fundamentally different optimization target.
- **Closes the loop on AAD:** Prior AAD work (TU Denmark 2025, TSF-AADNet 2025, two-node wireless EEG 2026) showed feasibility of decoding attention. This paper is the first to demonstrate that closing the loop in real time produces a measurable perceptual gain in humans.
- **Form-factor gap remains:** ECoG is invasive and won't ship. The translational question is whether ear-EEG (Aarhus Center for Ear-EEG), cEEGrids, or non-neural surrogates (gaze, head motion, conversational priors) can recover enough of the attention signal at hearing-aid power budgets.

## Limitations Acknowledged

- Invasive ECoG only — not yet shown with non-invasive sensing.
- Sample size small (epilepsy surgery candidates).
- Tested in controlled multi-talker conditions, not real-world acoustic scenes.
- Authors explicitly note "a great deal of work is needed before this technology is available in a wearable form."

## Coverage

- NPR (May 11 2026): https://www.npr.org/2026/05/11/nx-s1-5812674
- Neuroscience News (May 11 2026): https://neurosciencenews.com/brain-controlled-hearing-aid-60465/
- Inside Precision Medicine (May 11 2026): https://www.insideprecisionmedicine.com/topics/translational-research/brain-controlled-hearing-aid-singles-out-voices-in-a-crowd/
- EurekAlert! release: https://www.eurekalert.org/news-releases/1127026
- MedicalXpress: https://medicalxpress.com/news/2026-05-brain-isolates-speaker-noisy-human.html

## Related Wiki Pages
- [[auditory-attention-decoding]] — Primary concept page; this paper is the closed-loop human milestone.
- [[dnn-architectures-hearing-aids]] — DNN pipeline that AAD would feed into.
- [[speech-enhancement-neural-networks]] — Conventional enhancement is the alternative paradigm.
- [[on-device-ml-hearing-aids]] — Power/latency budget that any wearable AAD must respect.
