---
tags: [3d-unet, chameleon, ddim, diffusion-models, encoder-free-early-fusion, full-duplex-interaction, mixture-of-experts, multimodal-fusion, multimodal-models, realtime-voice, temporal-consistency, thinking-machines, v-parameterization, video-generation, vision-language-models, voice-activity-detection]
---

# Multimodal Models

Tracks the expansion of AI models beyond text: vision-language models (VLMs), audio understanding, video generation, and unified multimodal architectures. Covers GPT-4V, Gemini, Claude's vision, and the techniques for training across modalities.

Key questions tracked: Where are multimodal models actually being deployed in production? What is the gap between text-only and multimodal capability? How does video understanding change the product surface?

## Key Claims
<!-- agent-maintained -->

### Interaction Models: Native Real-Time Multimodal Architecture (Thinking Machines, May 2026)
- **TML-Interaction-Small**: 276B total parameters with 12B active parameters (MoE architecture)
- **Design philosophy**: "Trained from scratch for real-time interaction" rather than layering speech/vision onto turn-based LLMs
- **Core capability**: Full-duplex multimodal interaction as first-class model capability—models "listen, speak, watch, think, search, and react concurrently" without explicit turn boundaries
- **Architecture approach**: Encoder-free early fusion processing images and audio <200ms latency, similar to Meta's [[model-architecture]] Chameleon
- **Temporal granularity**: Operates on "time-aligned microturns" of 200ms each for continuous interactivity
- **Visual proactivity**: Zero-shot capabilities like "tell me when I start slouching" or "count my pushups" emerge as native primitives rather than requiring special-purpose systems
- **Benchmark performance**: Reports beating GPT-Realtime-2 and Gemini 3.1-Flash on BigBench Audio, IFEval, and FD-bench
- **New internal benchmarks** (developed for interaction-specific evaluation):
  - **TimeSpeak**: Tests model's ability to initiate speech at user-specified times (e.g., "remind me to

### Video Generation: Diffusion Models (Lilian Weng, April 2024)
- **Challenge expansion**: Video generation is "a superset of the image case" with extra requirements:
  - Temporal consistency across frames demanding more world knowledge encoded in models
  - Data scarcity: More difficult to collect large amounts of high-quality, high-dimensional video data and text-video pairs
- **Parameterization approaches**:
  - **v-prediction parameterization** ($\mathbf{v} = \alpha_t \boldsymbol{\epsilon} - \sigma_t \mathbf{x}$): Proposed by Salimans & Ho (2022), shown to be "helpful for avoiding color shift in video generation compared to $\boldsymbol{\epsilon}$-parameterization"
  - Derived using angular coordinate trick with $\phi_t = \arctan(\sigma_t / \alpha_t)$
- **Architecture**: 3D U-Net and DiT (Diffusion Transformer) used for video generation from scratch
- **Adaptation strategies**: Two approaches to leverage pre-trained image models for video:
  - Fine-tuning on video data
  - Training-free adaptation
- **Forward process**: Gaussian noise-adding process with differentiable noise schedule defined by $\alpha_t, \sigma_t$
- **DDIM sampling**: Uses log signal-to-noise-ratio $\lambda_t = \log[\alpha^2_t / \sigma^2_t]$ for updates