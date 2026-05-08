---
title: Short-term hearing aid use reduces auditory cortical responses to speech-in-noise listening among older adults with age-related hearing loss
type: research-paper
date: 2026-04-16
journal: Frontiers in Aging Neuroscience
authors: Becker, Voss, Martinez-Moreno, Prévost, Zeitouni, Lopez Valdes, de Villers-Sidani
affiliation: McGill University; Trinity College Dublin
url: https://www.frontiersin.org/journals/aging-neuroscience/articles/10.3389/fnagi.2026.1690956/full
doi: 10.3389/fnagi.2026.1690956
tags: [hearing-aids, neuroplasticity, meg, speech-in-noise, older-adults, cortical-reorganization, outcome-measurement]
---

# Short-Term Hearing Aid Use Reduces Auditory Cortical Responses to Speech-in-Noise Listening (Becker et al., 2026)

## Key Extractions

### Study Design
- Within-subject pre/post design with magnetoencephalography (MEG) recordings.
- **n = 12** older adults (mean age 75.8 years) with age-related hearing loss.
- Bilateral hearing aid intervention with individualized amplification (dynamic compression + manufacturer-default noise reduction).
- Required wear time: at least 8 hours/day for 3 months between MEG sessions.
- Speech-in-noise tasks (HINT) administered during MEG recording, matched in difficulty across sessions.

### Findings
- **Significant reductions in MEG activity in right-hemisphere auditory cortical regions** after only 3 months of regular daily HA use.
- Matched-pairs rank biserial correlation effect sizes ranged **0.61 to 1.00** (moderate to large).
- **Left-hemisphere activity reductions correlated more strongly with individual speech-in-noise behavioral improvement** than right-hemisphere reductions.
- Task performance was matched across sessions by design, isolating the neural-efficiency interpretation.

### Authors' Interpretation
- The cortical reduction is **not pure remediation** of hearing loss — task difficulty was held constant.
- Reductions reflect "experience-dependent recalibration of neural processing demands" — i.e., the brain becomes more efficient at handling amplified sound.
- Provides evidence that the aging cortex retains substantial plasticity in response to a sensory aid intervention.

## Relevance to Hearing-Tech Data Science

### 1. Outcome Measurement Layer
- Audiogram and standard speech-in-noise scores at the next clinic visit are sampled at the wrong cadence (months apart) and on the wrong variable (input thresholds, not cortical efficiency).
- The actual prosthetic target is the auditory cortex; the cochlea is the access port. This reframes "good fitting" toward neural efficiency rather than amplification accuracy.

### 2. 12-Week Adaptation Window
- Three months is a meaningful and individual unit of change. Personalization should index off the user's adaptation trajectory, not the clinical visit calendar.
- Suggests fitting should be delivered as a multi-stage protocol that anticipates and tracks cortical recalibration, not a single in-clinic visit.

### 3. Telemetry as Cortical-Efficiency Proxy
- Hearing aids already record usage and acoustic environment.
- With the right model architecture, telemetry could approximate the cortical efficiency signal that MEG captures in this study — at zero marginal cost, every day, for every user.
- Connects directly to longitudinal hearing phenotyping and the closed-loop data flywheel.

## Limitations
- Small sample (n = 12); needs replication.
- Open-label, no sham/placebo arm.
- Single 3-month timepoint — longer-term plasticity trajectory unknown.
- Standardized fitting protocol; effect of personalized AI fitting on cortical reorganization not tested.

## Cross-References Within Wiki
- [[../wiki/concepts/longitudinal-hearing-phenotyping]] — Brain plasticity as the missing variable in current outcome layer
- [[../wiki/concepts/subjective-objective-hearing-gap]] — Reinforces gap between input audiometry and processed-listening experience
- [[../wiki/concepts/closed-loop-data-flywheel]] — Telemetry-derived cortical-efficiency proxy as flywheel feedback signal
- [[../wiki/concepts/on-device-ml-hearing-aids]] — Personalization indexed to neural adaptation curve
- [[../wiki/concepts/dnn-in-hearing-aids]] — Implication that DNN noise reduction may need to be paced to user adaptation
