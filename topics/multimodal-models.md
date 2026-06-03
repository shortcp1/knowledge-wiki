---
tags: [3d-unet, audio-latency, audio-video-alignment, autoregressive-reasoner, chameleon, concurrent-processing, ddim, diffusion-models, diffusion-transformers, encoder-free-early-fusion, encoder-free-fusion, flipbook, flow-matching-decoder, full-duplex-interaction, generative-ui, grok-imagine, hierarchical-mlp, image-to-video, inference-speed, inference-speedups, iteration-speed, mixture-of-experts, mixture-of-transformers, multimodal-alignment, multimodal-architecture, multimodal-fusion, multimodal-models, neural-os, open-weights, real-time-inference, realtime-voice, sparse-models, step-distillation, synthetic-captions, temporal-compression, temporal-consistency, text-to-image, text-to-video, thinking-machines, v-parameterization, vaes, video-agents, video-generation, video-models, vision-language-models, voice-activity-detection, world-models]
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
- **Temporal granularity**: Operates on "time-aligned microturns" of 200ms each for co

## World Models and Physical AI

### NVIDIA Cosmos 3 (June 2026)
- **Architecture**: Mixture-of-Transformers design combining autoregressive reasoner with diffusion generator (see [[model-architecture]] for technical details)
- **Modality unification**: Single model handles language, image, video, audio, and action
- **Model family**:
  - Nano base: 16B (8B reasoner + 8B generator)
  - Super base: 64B (32B reasoner + 32B generator)
  - Super finetuned variants for Text-to-Image and Image-to-Video
- **Performance claims**:
  - #1 open-weight model on both Text-to-Image and Image-to-Video leaderboards (Artificial Analysis, June 2026)
  - Positioned just below Nano Banana 2 in capability
- **Release scope**: Full-stack open release including weights, code, datasets, and fine-tuning recipes
- **Ecosystem strategy**: NVIDIA launched "Cosmos Coalition" with partners including Runway to build open ecosystem for world models
- **Framework integration**: Adoption of OpenMDW framework; day-0 platform integrations (fal, etc.)
- **Use case positioning**: Framed as infrastructure for "physical AI" including robotics applications

### MiniMax M3 (June 2026)
- **Configuration**: Open-weight multimodal agent model with 1M context window
- **Modality support**: Native multimodal processing (specific modalities not detailed)
- **Agent benchmark performance**:
  - SWE-Bench Pro: 59.0%
  - Terminal Bench 2.1: 66.0%
  - MCP Atlas: 74.2%
- **Practical strengths**: Reports of strong performance on frontend generation, visual tasks, and game generation with one-shot outputs
- **Note**: Mixed results between benchmark performance and practical deployment experience reported

## Image and Video Generation Leaderboard Status (June 2026)
- **Open-weight SOTA**: NVIDIA Cosmos 3 Super finetuned variants
- **Closed model frontier**: Nano Banana 2 (positioning relative to open models)