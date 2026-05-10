---
title: Speech Enhancement Neural Networks
type: concept
created: 2026-04-15
updated: 2026-05-10
sources: [dnn-noise-reduction-intelligibility-2026.md, sub-millisecond-speech-enhancement-hearables-2025.md, multichannel-deep-speech-enhancement-ha-2024.md, speech-foundation-models-hearing-impaired-2024.md, ssl-loss-functions-hearing-aid-enhancement-2024.md, phonak-dnn-noise-reduction-clinical-trial-april-2026.md, deezer-44pct-ai-generated-audio-april-2026.md, wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md, samsung-galaxy-s26-audio-eraser-realtime-2026.md, adobe-speechmatics-on-device-stt-april-2026.md, korhonen-natural-vs-dnn-hearing-aids-april-2026.md, dat-cftnet-ci-speech-enhancement-icassp-2026.md, tokense-mamba-ci-speech-enhancement-2026.md, gap-urgenet-urgent-challenge-icassp-2026.md, target-speaker-extraction-ultra-low-latency-2026.md, ssl-pretraining-robust-ha-speech-enhancement-2026.md, efficient-on-device-speech-enhancement-qat-2026.md, mdpi-speech-separation-survey-2026.md, spatial-magnifier-multichannel-se-arxiv-2026.md, ndf-plus-neural-directional-filtering-arxiv-2026.md, predictive-generative-drift-decomposition-arxiv-2026.md, aida-2-bayesian-generative-se-arxiv-2026.md]
related: [on-device-ml-hearing-aids.md, small-language-models-edge-ai.md, dnn-architectures-hearing-aids.md, auditory-attention-decoding.md, cochlear-implant-ai.md, vcca-computational-audiology.md, state-space-models.md, ../comparisons/dnn-vs-natural-processing.md, mamba-architecture.md, active-noise-cancellation.md, eu-ai-act-medical-devices.md, probabilistic-generative-models-hearing-ai.md]
tags: [deep-learning, speech, noise-reduction, dnn, hearing-aids, crn, transformer, mamba, generative-predictive, bayesian-counter-paradigm]
---

# Speech Enhancement Neural Networks

Neural network architectures designed to improve speech intelligibility by separating speech from noise, enhancing clarity, and adapting to listener preferences. This is the primary ML workload in modern hearing aids.

## Evolution
1. **Classical DSP** — Wiener filters, spectral subtraction (pre-2015)
2. **Simple DNNs** — Feedforward networks for noise estimation (2015-2018)
3. **RNNs/LSTMs** — Temporal modeling for non-stationary noise (2018-2021)
4. **CRN (Convolutional Recurrent Networks)** — CNN spatial + RNN temporal, now the dominant production architecture (2020-present)
5. **Attention/Transformer variants** — SepFormer and similar, better long-range dependencies (2021-present)
6. **State-space / Mamba variants** — Linear-time alternative to attention; competitive at hearing-aid latency budgets per the 2026 MDPI survey (`mdpi-speech-separation-survey-2026.md`). Field is converging on the arc U-Net → Wave-U-Net → Conv-TasNet → Transformer → Mamba.
7. **Emerging: Diffusion-based** — Generative approaches for speech reconstruction (research stage)

## Key Architectures in Hearing Aid Research

### Convolutional Recurrent Networks (CRN) — Current Optimal
CRN is considered the optimal architecture for production hearing aids: CNN layers extract spatial/spectral features while RNN layers model temporal dynamics. This combination handles both stationary and non-stationary noise effectively within tight latency budgets.
- CNN branch: captures spectral patterns and multi-mic spatial information
- RNN branch: models temporal evolution of noise and speech
- Fusion: combines spatial and temporal representations for mask prediction

### SepFormer (Transformer-based)
- Self-attention mechanism captures long-range temporal dependencies
- Competitive on DNS Challenge benchmarks
- Compute cost remains a barrier for direct deployment; used as teacher model for distillation

### Legacy Architectures (Research Baseline)
- **Conv-TasNet** — Time-domain speech separation, influential architecture. Schulz et al. 2026 demonstrated 1ms latency variant with significant CI benefit (+5.7 dB). Originally considered too large for HA chips, but optimization work continues.
- **DCCRN** — Deep Complex Convolution Recurrent Network, good real-time performance
- **FullSubNet** — Full-band and sub-band fusion, strong on DNS Challenge benchmarks
- **TinyRecurrentUNet** — Designed for low-resource devices, closer to hearing aid constraints

## Time-Domain vs Frequency-Domain Approaches
| Approach | Pros | Cons | Example Models |
|----------|------|------|----------------|
| Frequency-domain | Interpretable, well-studied, integrates with existing DSP | Phase reconstruction artifacts | DCCRN, FullSubNet |
| Time-domain | No phase problem, end-to-end | Higher compute, harder to control | Conv-TasNet, DEMUCS |
| Hybrid | Best of both | Complex training | CRN variants |

## Ultra-Low Latency Requirements
- Hearing aids require < 10ms algorithmic latency (users perceive delay above this threshold)
- Some implementations target **1ms latency** for DNN noise reduction blocks
- This forces time-domain causal processing and small receptive fields
- Future lookahead is limited to a few milliseconds at most

## Training Data Scales
Leading manufacturers train on massive datasets to cover real-world acoustic diversity:
- **13.5M to 22M synthetic sound scenes** reported in recent manufacturer publications
- Scenes combine speech (various languages, accents, mic distances) with noise (stationary, non-stationary, multi-source)
- Hearing aid microphone simulation is critical — models trained on clean recordings generalize poorly to HA mics

## Generative Audio AI and Speech Enhancement

The boundary between generative audio AI and speech enhancement is blurring. Deezer reports that **44% of songs uploaded daily** are AI-generated (April 2026), with 85% of AI-music streams flagged as fraudulent. While this is a music/streaming story, it signals the maturity of neural audio generation at scale.

**Relevance to hearing aid speech enhancement:**
- Generative audio models (diffusion, GANs, flow-matching) share architectural DNA with speech enhancement networks — both model and manipulate audio spectrograms
- **Generative enhancement** — instead of masking noise (traditional approach), generative models can reconstruct clean speech from degraded signals, potentially achieving better quality than mask-based approaches
- **Synthetic training data** — generative models could produce diverse, realistic training data for hearing aid DNN training at lower cost
- **Personalized audio rendering** — generating audio optimized for individual hearing profiles, rather than applying frequency-dependent gain to existing audio
- The 44% figure demonstrates that neural audio generation has reached production-scale quality and throughput

## Challenges Specific to Hearing Aids
- Model must run in < 10ms (algorithmic latency budget); 1ms targets emerging
- Must handle hearing loss-specific processing (frequency-dependent amplification per audiogram)
- Training data rarely matches real-world hearing aid microphone characteristics
- Need to preserve spatial cues for localization (binaural processing)
- Must work across all environments without user intervention
- Cannot degrade music quality while enhancing speech

## Evaluation Metrics
- **PESQ** — Perceptual Evaluation of Speech Quality
- **STOI** — Short-Time Objective Intelligibility
- **SI-SNR** — Scale-Invariant Signal-to-Noise Ratio
- **DNS Challenge** — Industry benchmark for real-time speech enhancement
- **Subjective listening tests** — Still gold standard; ML metrics don't fully capture perceived quality for hearing aid users

## Recent Academic Advances (2024–2026)

### Sub-Millisecond Latency (2025)
Achieved 0.32–1.25 ms mean algorithmic latency using minimum-phase FIR filter for sample-by-sample processing on hearables. Eliminates comb-filter artifacts entirely (arXiv, 2025).

### Ultra-Low Latency DNN Noise Reduction — Listener Group Analysis (Schulz et al. 2026)
Conv-TasNet achieving 1 ms latency, tested across three listener groups (Frontiers in Audiology and Otology, Jan 2026):
- **CI users: +5.7 dB** SNR benefit — largest improvement
- **Hearing-impaired: +0.8 dB** — modest positive benefit
- **Normal-hearing: slightly degraded** — DNN may interfere with good baseline perception
- **Key finding:** Benefit inversely correlates with baseline hearing deficit — DNN noise reduction is most valuable for users with the worst baseline, particularly cochlear implant users

### Binaural Deep Speech Enhancement (2024)
IEEE/ACM TASLP paper comparing monaural vs. binaural DNN processing. Shows binaural processing preserves spatial cues (ITD/ILD) while enhancing speech — solving a key limitation of earlier independent-ear processing.

### Self-Supervised Speech Models as Loss Functions (2024)
Novel approach using self-supervised speech representations in the loss function during training (not as input features). Produces enhancement models better aligned with hearing-impaired perceptual quality. Connected to Clarity Challenge; funded by WS Audiology and Toshiba.

### Foundation Models for Intelligibility Prediction (2024)
Self-supervised speech models (e.g., NVIDIA Parakeet, 600M params, 120k hours) correlate better with human intelligibility ratings than PESQ/STOI. Opens path to non-intrusive quality prediction without listener panels.

### Phonak DNN Noise Reduction Clinical Trial (April 2026)
Sonova/Phonak registered an interventional clinical trial (NCT07526428) specifically evaluating DNN noise reduction for moderate-to-severe hearing loss. First registered trial targeting DNN efficacy at more severe hearing loss levels, where SNR requirements differ from mild-to-moderate populations.

### Samsung Galaxy S26 Real-Time Audio Eraser (April 2026)
Samsung's Galaxy S26 transitions Audio Eraser from post-production editing to **real-time sound separation** during live capture. Significance for hearing AI:
- Consumer smartphones now have sufficient ML inference for real-time source separation — sets user expectations
- The "post-production to real-time" transition mirrors hearing aids' own evolution from offline fitting to real-time DNN processing
- Technology transfer: smartphone-grade models could be distilled for hearing aid deployment
- Competitive pressure: as phones gain hearing-aid-like capabilities, prescription devices must demonstrate superior performance

### Multi-Stage Phase-Aware Enhancement (arXiv, April 2026)
Novel system (arXiv:2508.04283) operating in both magnitude and complex domains:
- **Two-stage:** magnitude-domain noise reduction, then complex-domain phase refinement
- **Asymmetric window pair** — different analysis/synthesis window lengths for higher frequency resolution within **5ms latency**
- **Head rotation integration** — uses head motion data to guide spatial processing (connects to Oticon 4D sensor trend)
- Phase utilization is a key frontier: most production systems discard phase information, losing speech naturalness
- Asymmetric windowing is hardware-friendly and implementable in firmware without new silicon

### End-to-End Audio-Visual CI Sound Coding (arXiv, April 2026)
First end-to-end audio-visual system for cochlear implant sound coding (arXiv:2508.13576v1):
- Combines microphone audio with **lip-reading video** to produce CI electrodograms
- Noise-robust: visual signal provides independent information when audio is degraded
- End-to-end learning jointly optimizes audio processing, visual processing, and electrodogram generation
- Practical deployment: likely first as a smartphone app, not standalone CI processor
- Extends multimodal AI to cochlear implants. See [[cochlear-implant-ai]].

### Programmable Speech AI Accelerators (arXiv 2025)
Custom silicon co-designed with speech AI models (arXiv:2503.18698v2):
- **Mixed-precision quantization** — different bit widths per layer for optimal accuracy-efficiency tradeoff
- **28-participant human evaluation** — perceptual validation, not just PESQ/STOI
- Programmable design allows model updates post-deployment

### Target Speaker Extraction at Sub-5ms Latency (Hsu et al., April 2026)
Hsu et al. (arXiv eess.AS) demonstrate **causal target speaker extraction** at sub-5ms latency for hearing assistive devices:
- Uses **speaker embeddings** to identify and extract a specific target speaker from multi-talker mixtures
- Sub-5ms causal processing — well within hearing aid latency constraints
- **TSE vs general enhancement:** Instead of enhancing "all speech," extracts a specific speaker identified by a pre-enrolled embedding (e.g., spouse, caregiver)
- **Connection to AAD:** Could be steered by EEG-based auditory attention decoding signals rather than manual selection — see [[auditory-attention-decoding]]
- Speaker embeddings could be enrolled via companion app, enabling personalized listening profiles
- Represents a shift from "enhance speech" to "enhance the right speech"

### Self-Supervised Pre-Training for Hearing Aid Enhancement (April 2026)
SSL pre-training on unlabeled audio improves speech enhancement model generalization to unseen noise conditions (arXiv cs.SD):
- Models pre-trained with self-supervised objectives generalize better to real-world noise not represented in training data
- **Eliminates annotation bottleneck:** Unlabeled audio is vastly more abundant than the 13M-22M annotated scenes used by manufacturers
- Distinct from prior SSL work (2024) that used SSL representations as loss functions — this uses SSL for the model's own pre-training
- Could enable hearing aid models that are more robust to the "long tail" of rare acoustic environments
- Pre-trained representations could serve as better starting points for manufacturer-specific fine-tuning

### INT8 Quantization-Aware Training for Speech Enhancement (April 2026)
Efficient on-device speech enhancement via QAT (arXiv eess.AS):
- **INT8 quantization** with quantization-aware training achieves **3x speedup on ARM processors** with minimal quality loss
- QAT (training with quantization in the loop) outperforms post-training quantization for speech enhancement
- ARM relevance: some hearing aid designs use ARM Cortex-M class cores
- 3x speedup means either lower latency or the ability to run larger/more accurate models within the same latency budget
- See [[model-compression]] for broader quantization context

### Spatial-Magnifier — Spatial Upsampling for Multichannel SE (Lee et al., May 2026)
arXiv eess.AS (Meta Reality Labs and collaborators) tackles the **mic-spacing wall** that bounds wearable beamformer selectivity:
- Learns a spatial-upsampling stage that maps a small wearable mic array's signals to features representative of a denser/larger array, then runs a downstream multichannel SE network on the upsampled representation.
- Spatial-domain analogue of image super-resolution: solve the small-array problem in software rather than industrial design.
- Directly relevant to hearing-aid beamforming + DNN cascades, where physical mic spacing is the dominant ceiling on directional selectivity.
- Open question: latency cost, calibration sensitivity, and composition with bilateral (binaural) processing where the virtual array is already much wider than monaural.
- See [[../sources/spatial-magnifier-multichannel-se-arxiv-2026]].

### NDF+ — Joint Neural Directional Filtering and Diffuse Sound Extraction (Huang et al., May 2026)
arXiv eess.AS (Habets group, Fraunhofer IIS / FAU Erlangen-Nürnberg):
- A single network that **jointly performs directional filtering and diffuse-sound extraction** rather than treating them as separate pipelines.
- Cocktail-party scenes are simultaneously directional + diffuse — exactly where hearing-impaired listeners struggle most. Classical beamformers can null directional sources but not spatially-spread babble.
- Pairs naturally with sub-5ms target-speaker extraction (Hsu et al. 2026) — the field is converging on a **directional / speaker-identity / diffuse** three-way scene decomposition.
- Habets' group is upstream of Phonak/Sonova's spatial-audio research; expect this thread to surface in production silicon one-to-two generations later.
- See [[../sources/ndf-plus-neural-directional-filtering-arxiv-2026]].

### AIDA-2 — Probabilistic Generative Counter-Paradigm (Hidalgo-Araya et al., March 2026)
arXiv 2603.28436 (GN Advanced Science + TU Eindhoven + Lazy Dynamics, 30 Mar 2026):
- **Not a neural network at all.** Reformulates the spectral-enhancement pipeline as a **single Bayesian generative model** with signal processing, learning, and personalization expressed as inference variants in the same factor graph.
- **~85 effective parameters** competitive with Wiener filtering on VoiceBank+DEMAND (PESQ 2.17 vs 2.22) — six orders of magnitude fewer than the deep networks above.
- Variational message passing in **RxInfer.jl** as the inference engine.
- Personalization as **Bayesian posterior updating** on user appraisals — collapses fitting into the same machinery that does denoising.
- Significant because GN Advanced Science (research arm of GN Hearing/ReSound) is co-author. Probabilistic generative modeling is being advanced from inside a Big-Five OEM, not just academic ELLIS labs.
- Open question: matches *Wiener*, not modern DNN baselines, on PESQ. Argument is parameter efficiency and structural advantages, not raw quality. Does it scale?
- See [[probabilistic-generative-models-hearing-ai]] (primary home) and [[../sources/aida-2-bayesian-generative-se-arxiv-2026]].

### Predictive-Generative Drift Decomposition (Richter et al., May 2026)
arXiv eess.AS (MERL / U Hamburg / Paderborn — same lineage as GAP-URGENet):
- Decomposes the SE target into a **predictive (deterministic, mask-based) component** and a **generative drift component** that refines the residual the predictive path leaves.
- Directly addresses the "robotic over-suppression" failure mode that is the dominant user complaint about modern HA DNN noise reduction — predictive models cause it; generative refinement could fix it.
- The decomposition gives a **personalization knob**: a scalar predictive↔generative weight exposes a perceptual-comfort vs. fidelity slider without retraining.
- Continuation of the GAP-URGENet generative-predictive fusion thread; same group, more principled formulation.
- Implementation question: generative inference is expensive — can the generative path be **gated conditionally** (only when the predictive residual is high) to fit a 10 ms HA budget?
- See [[../sources/predictive-generative-drift-decomposition-arxiv-2026]].

## Related Pages
- [[dnn-architectures-hearing-aids]] — Deep dive on hardware-specific DNN architectures and chip implementations
- [[on-device-ml-hearing-aids]] — Deployment target for these networks
- [[small-language-models-edge-ai]] — Compression techniques applicable to speech models
- [[auditory-attention-decoding]] — Next frontier: steering enhancement based on where user is listening; TSE + AAD enables brain-steered speaker selection
- [[cochlear-implant-ai]] — Speech enhancement DNNs adapted for cochlear implant users
- [[vcca-computational-audiology]] — Central topic across all VCCAs
- [[eu-ai-act-medical-devices]] — Regulatory framework affecting AI speech enhancement in hearing aids

### DAT-CFTNet: Attention-Based Dual-Path RNN for CI (ICASSP 2026)
Mamun & Hansen (arXiv:2604.06744, April 2026) propose an attention-based dual-path RNN for CI speech enhancement:
- **Outperforms CFTNet and DCCRN** — established baselines for real-time speech enhancement
- **Eliminates musical artifacts** — a critical problem for CI users where spectral processing remnants are highly disruptive through electrode stimulation
- Dual-path architecture handles both intra-chunk (local) and inter-chunk (global) temporal patterns
- Attention mechanism focuses on speech-relevant time-frequency regions
- Validates dual-path RNN + attention as viable for CI-constrained enhancement

### TokenSE: Mamba-Based Speech Enhancement for CI (April 2026)
Chiang & Hansen (arXiv:2604.12246) demonstrate the first Mamba (selective SSM) based speech enhancement for CI:
- **Linear O(n) complexity** vs quadratic O(n^2) for Transformer approaches — critical for CI processor compute budgets
- Operates on **discrete speech tokens** — compression/abstraction before SSM processing
- **Subjective tests with actual CI users** confirm intelligibility gains (not just objective metrics)
- See [[mamba-architecture]] for detailed Mamba analysis

### GAP-URGENet: 1st Place URGENT 2026 Challenge (ICASSP 2026)
Won 1st place in the URGENT (Universal speech Restoration with Generative approaches) 2026 Challenge at ICASSP (arXiv:2604.01832):
- **Generative-predictive fusion framework** for universal speech enhancement
- Handles multiple degradation types simultaneously: noise, reverb, bandwidth limitation, clipping, codec artifacts
- **Predictive path:** Direct mask estimation (fast, reliable)
- **Generative path:** Diffusion/flow-based speech reconstruction (higher quality ceiling)
- **Fusion:** Combines both for reliability + quality — addresses the key tradeoff for hearing aid deployment
- "Universal" enhancement aligns with hearing aid reality: devices face all degradation types simultaneously

## Sources
- [Sub-ms Latency Speech Enhancement](../sources/sub-millisecond-speech-enhancement-hearables-2025.md)
- [Low-Latency DNN Noise Reduction](../sources/dnn-noise-reduction-intelligibility-2026.md)
- [Binaural Deep Speech Enhancement](../sources/multichannel-deep-speech-enhancement-ha-2024.md)
- [SSL Loss Functions for HA Enhancement](../sources/ssl-loss-functions-hearing-aid-enhancement-2024.md)
- [Speech Foundation Models for HI Prediction](../sources/speech-foundation-models-hearing-impaired-2024.md)
- [Wireless Hearables Programmable Speech AI Accelerators](../sources/wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md)
- [Samsung Galaxy S26 Audio Eraser](../sources/samsung-galaxy-s26-audio-eraser-realtime-2026.md)
- [Adobe + Speechmatics On-Device STT](../sources/adobe-speechmatics-on-device-stt-april-2026.md)
- [DAT-CFTNet CI Speech Enhancement](../sources/dat-cftnet-ci-speech-enhancement-icassp-2026.md) — Attention dual-path RNN, eliminates musical artifacts
- [TokenSE Mamba CI Speech Enhancement](../sources/tokense-mamba-ci-speech-enhancement-2026.md) — First Mamba-based SE for CI with subjective validation
- [GAP-URGENet URGENT 2026 Winner](../sources/gap-urgenet-urgent-challenge-icassp-2026.md) — Generative-predictive fusion, universal enhancement
- [Multi-Stage Low-Latency Enhancement for HAs](../sources/multi-stage-low-latency-enhancement-ha-arxiv-2026.md) — Phase-aware multi-stage, asymmetric windowing, head rotation, 5ms latency
- [End-to-End Audio-Visual CI Sound Coding](../sources/end-to-end-audiovisual-ci-sound-coding-arxiv-2026.md) — Audio + lip-reading for CI electrodogram generation
- [Target Speaker Extraction Sub-5ms](../sources/target-speaker-extraction-ultra-low-latency-2026.md) — Causal TSE with speaker embeddings for hearing assistive devices
- [SSL Pre-Training for HA Speech Enhancement](../sources/ssl-pretraining-robust-ha-speech-enhancement-2026.md) — Self-supervised pre-training improves generalization to unseen noise
- [INT8 QAT Speech Enhancement](../sources/efficient-on-device-speech-enhancement-qat-2026.md) — 3x ARM speedup via quantization-aware training
- [Spatial-Magnifier (Lee et al., May 2026)](../sources/spatial-magnifier-multichannel-se-arxiv-2026.md) — Learned spatial upsampling for small wearable mic arrays
- [NDF+ (Huang et al., May 2026)](../sources/ndf-plus-neural-directional-filtering-arxiv-2026.md) — Joint directional filtering + diffuse extraction
- [Predictive-Generative Drift Decomposition (Richter et al., May 2026)](../sources/predictive-generative-drift-decomposition-arxiv-2026.md) — Decomposes SE into predictive + generative components for fidelity-vs-comfort knob
- [AIDA-2 — Probabilistic Generative Speech Enhancement (Hidalgo-Araya et al., Mar 2026)](../sources/aida-2-bayesian-generative-se-arxiv-2026.md) — GN Advanced Science + TU Eindhoven; ~85-parameter Bayesian generative model competitive with Wiener at six orders of magnitude fewer parameters than DNNs
