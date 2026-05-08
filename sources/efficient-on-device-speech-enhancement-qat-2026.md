---
title: "Efficient On-Device Speech Enhancement with Quantization-Aware Training"
source: arXiv eess.AS
date: 2026-04-25
ingested: 2026-04-25
tags: [quantization-aware-training, int8, speech-enhancement, on-device, arm, edge-ai]
---

# Efficient On-Device Speech Enhancement with Quantization-Aware Training

## Key Claims
- INT8 quantization of speech enhancement models via quantization-aware training (QAT)
- 3x speedup on ARM processors with minimal quality degradation
- QAT trains with quantization in the loop, producing models that are robust to reduced precision
- Demonstrates practical deployment path for speech enhancement on mobile/edge ARM hardware

## Significance for Hearing AI
- **ARM processors** are relevant to hearing aids: some newer designs use ARM Cortex-M class cores alongside DSPs
- **3x speedup** from INT8 quantization means either faster inference (lower latency) or the ability to run larger/more accurate models within the same latency budget
- **Minimal quality loss** validates QAT as superior to post-training quantization for speech enhancement — important because hearing aid users are sensitive to quality degradation
- Extends the quantization literature specifically to speech enhancement (most QAT work targets LLMs/vision)
- Direct relevance to Aizip and similar platforms running AI on standard (non-NPU) hearing device hardware

## Technical Details
- Quantization-aware training: simulates INT8 arithmetic during training so the model learns to be robust to reduced precision
- ARM-specific optimization: likely leverages NEON SIMD instructions for INT8 matrix operations
- 3x speedup is meaningful for hearing aid deployment where every cycle counts against the <10ms latency budget

## Relevance to Wiki
- Directly extends [[model-compression]] with QAT evidence for speech enhancement
- Relevant to [[on-device-ml-hearing-aids]] — ARM deployment path
- Connects to [[speech-enhancement-neural-networks]] — quantized speech enhancement
- Relevant to [[hearing-aid-chip-architectures]] — ARM-based designs
