---
title: Kv7.4 (KCNQ4) in Outer Hair Cells
type: concept
created: 2026-06-24
updated: 2026-06-24
sources: [acousia-bimokalner-phase-2a-june-2026.md, vcca-2026-main-programme-june-2026.md]
related: [otoprotection-pharmacology.md, hidden-hearing-loss.md, precision-drug-delivery-inner-ear.md, gene-therapy-hearing.md, ../entities/acousia-therapeutics.md, ../syntheses/hidden-hearing-loss-fullstack-june-2026.md]
tags: [molecular-target, ion-channel, kv7-4, kcnq4, potassium-channel, outer-hair-cell, ohc, dfna2, ototoxicity, pharmacology, acousia, bimokalner]
---

# Kv7.4 (KCNQ4) in Outer Hair Cells

Kv7.4 (gene name **KCNQ4**) is a voltage-gated potassium channel expressed predominantly at the basal membrane of **outer hair cells (OHCs)** in the mammalian cochlea, with secondary expression in vestibular hair cells and in spiral ganglion neurons (SGN). It is one of the cleanest molecular targets in inner-ear pharmacology: human loss-of-function mutations cause a known progressive hearing-loss phenotype, the channel is selectively expressed in the cell population that matters most for cochlear amplification, and pharmacological openers exist that cross the round-window membrane after local delivery.

## Why Kv7.4 Matters in OHC Biology

OHCs are the cochlea's mechanical amplifier — they elongate and contract in response to membrane potential changes ("electromotility"), boosting basilar-membrane motion by 40–60 dB and giving the mammalian cochlea its sharp frequency tuning and high sensitivity. OHC electromotility depends on tight maintenance of the resting membrane potential, which in turn requires steady K⁺ efflux.

Kv7.4 is the dominant K⁺ efflux channel at the OHC basal pole. When Kv7.4 function declines (through genetic mutation, ototoxic stress, or age), K⁺ accumulates intracellularly, OHCs depolarise, electromotility degrades, and OHCs eventually die. The audiometric phenotype is **progressive high-frequency hearing loss** — exactly the pattern seen in age-related (presbycusis), noise-induced, and cisplatin-induced HL.

## Human Genetics — DFNA2

Loss-of-function mutations in *KCNQ4* cause **DFNA2** (Deafness, Autosomal Dominant, type 2): progressive bilateral high-frequency sensorineural hearing loss, onset in early adulthood, slow worsening across decades. DFNA2 is one of the most common genetic causes of postlingual non-syndromic deafness in adults.

This genetics-clinic linkage is what makes Kv7.4 a high-confidence pharmacological target:

- **Direction of effect is known**: less Kv7.4 → worse hearing → conversely, more Kv7.4 activity should preserve hearing.
- **Channel is selectively expressed**: pharmacological activation in the cochlea will not co-activate Kv7.4 elsewhere in catastrophic ways (Kv7.2/7.3 in the brain are the related neuronal channels; selectivity-of-opener and local delivery handle the off-target risk).
- **Clinical endpoint exists**: pure-tone audiometry, especially in the EHF range where OHC damage manifests first.

## Pharmacological Activation

Small-molecule Kv7 channel openers were originally developed as antiepileptics (retigabine / ezogabine, opening Kv7.2/7.3 in the brain). The **Kv7.4-selective opener** chemistry is more recent, motivated specifically by hearing-loss prevention.

**Bimokalner (ACOU085)** — Acousia Therapeutics' lead Kv7.4 modulator — is the most advanced clinical-stage compound in this class. Phase 2a positive readout reported 18 Jun 2026 in cisplatin-induced ototoxicity:

- Transtympanic slow-release gel formulation; single application; round-window-membrane diffusion into the cochlea.
- Split-body (within-subject) Phase 2a design — treated ear vs placebo ear in the same cisplatin patient.
- >90% of participants developed measurable ototoxicity in EHF 10–16 kHz range.
- **Treated ear showed clinically meaningful prevention of PTA threshold shifts vs placebo.**

See [[../entities/acousia-therapeutics]] and [[otoprotection-pharmacology]].

## Why It Matters Across the HHL / Otoprotection / HA Stack

### Cisplatin ototoxicity is the cleanest clinical signal

Cisplatin produces dose-dependent, reproducible, predominantly OHC-side, predominantly EHF-onset damage. It is the cleanest setting in which to demonstrate a pharmacological prevention effect against a contralateral within-subject control. A positive Phase 2a here is the necessary precondition to attempt larger trials in messier indications (age-related, noise-induced, idiopathic).

### Same mechanism, broader candidate populations on the horizon

If Kv7.4 activation prevents OHC loss in the chemo-toxicity setting, the next candidate populations are:
- Age-related (presbycusis) — the largest HA candidate cohort by far.
- Noise-induced (military, industrial, recreational) — partially overlapping with the DoD biometric-hearing-protection thread on the device side.
- Aminoglycoside-induced (gentamicin, neomycin) — globally significant, especially in LMICs.
- Idiopathic sudden sensorineural HL — adjunct to existing steroid protocols.

Each progression beyond the chemo signal requires substantially larger trials and substantially different regulatory framing (prophylaxis in a healthy-at-risk population vs add-on to a chemotherapy regimen).

### The same OHC biology underlies the "hidden hearing loss" phenotype on the diagnostic side

The OHC damage that Kv7.4 modulation prevents on the pharmacological side is one of the candidate mechanisms behind the [[hidden-hearing-loss]] phenotype on the diagnostic side (EHF-range damage with normal 0.25–8 kHz audiogram). The fact that the same OHC biology shows up at both ends of the stack — as the target of the drug *and* as the mechanism of the under-diagnosed phenotype — is the structural reason these two threads converge on the same June 2026 publication week. See [[../syntheses/hidden-hearing-loss-fullstack-june-2026]].

### Implications for the ML / personalisation side

If OHC-side prevention becomes routine, the hearing-aid wearer of 2035 is more likely to present with a mixed phenotype (preserved OHC function but synaptopathic or central deficits) than the audiogram-defined sensorineural pattern current fitting algorithms assume. The fitting target shifts from "compensate the audiogram" toward "infer and compensate the suprathreshold deficit pattern" — exactly the substrate the task-optimized-DNN-as-auditory-model and per-wearer simulated-periphery programmes are building.

## Open Questions

- Does Bimokalner cross from the chemo Phase 2a setting to age-related / noise-induced Phase 2/3 with comparable effect size?
- Are there non-Acousia Kv7.4 openers in active clinical development? (The competitive landscape is currently thin.)
- Can chronic dosing (vs single-application gel) be made safe enough for prophylactic use in healthy at-risk populations?
- Does Kv7.4 activation rescue *already-stressed-but-not-yet-dead* OHCs, or is it strictly preventative on healthy OHCs?
- Could Kv7.4-targeted gene therapy (AAV-delivered functional KCNQ4 to OHCs with DFNA2 mutations) follow the OTOF / Otarmeni pathway? Larger packaging-capacity and OHC-tropism challenges versus inner-hair-cell targets like OTOF, but conceptually parallel.

## Related Pages

- [[otoprotection-pharmacology]] — The therapeutic category Bimokalner instantiates.
- [[hidden-hearing-loss]] — The diagnostic phenotype the same OHC biology shows up in.
- [[precision-drug-delivery-inner-ear]] — The transtympanic slow-release substrate Bimokalner uses.
- [[gene-therapy-hearing]] — The adjacent restoration-layer programme; OTOF / Otarmeni is the analogous regulatory pathway for genetic SNHL.
- [[../entities/acousia-therapeutics]] — Sponsor of the lead Kv7.4 programme.
- [[../syntheses/hidden-hearing-loss-fullstack-june-2026]] — Where Kv7.4 sits in the four-layer HHL stack.

## Sources

- [Acousia Bimokalner Phase 2a Positive (Jun 18, 2026)](../../sources/acousia-bimokalner-phase-2a-june-2026.md) — Lead Kv7.4 clinical-stage compound.
- [VCCA 2026 Main Programme](../../sources/vcca-2026-main-programme-june-2026.md) — Hidden HL track context for the diagnostic side of the same OHC biology.
