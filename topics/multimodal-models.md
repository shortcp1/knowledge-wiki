---
tags: [3d-unet, audio-latency, audio-video-alignment, autoregressive-reasoner, chameleon, concurrent-processing, ddim, diffusion-models, diffusion-transformers, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, flipbook, flow-matching-decoder, full-duplex-interaction, gemma, gemma-4, generative-ui, grok-imagine, hierarchical-mlp, image-to-video, inference-speed, inference-speedups, iteration-speed, mixture-of-experts, mixture-of-transformers, modality-processing, model-simplification, multimodal-alignment, multimodal-architecture, multimodal-fusion, multimodal-models, neural-os, open-weights, real-time-inference, realtime-voice, sparse-models, step-distillation, synthetic-captions, temporal-compression, temporal-consistency, text-to-image, text-to-video, thinking-machines, unified-multimodal, v-parameterization, vaes, video-agents, video-generation, video-models, vision-language-models, voice-activity-detection, world-models]
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
- **Architecture approach**: Encoder-free early fusion processing images and audio <200ms latency

### Gemma 4 12B: Unified Encoder-Free Architecture (Google DeepMind, June 2026)
- **Model size**: 12B parameters
- **Architecture**: Unified, encoder-free multimodal model
- **Design philosophy**: Single model handling multiple modalities without separate encoders
- **Trend confirmation**: Continues industry movement toward [[encoder-free-fusion]] architectures (cf. TML-Interaction-Small above)
- **Inference advantage**: Encoder-free design likely reduces latency and architectural complexity compared to encoder-based approaches