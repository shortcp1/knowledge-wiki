---
tags: [3d-unet, accessibility, accessibility-ai, active-parameters, ai-beauty-standards, ai-bias, apache-2-license, assistive-ai, assistive-technology, audio-latency, audio-video-alignment, autoregressive-reasoner, be-my-eyes, chameleon, concurrent-processing, ddim, diffusion-models, diffusion-transformers, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, envision-ai, flipbook, flow-matching-decoder, foundation-models, full-duplex-interaction, gemma, gemma-4, generative-ui, gpt-4-vision, grok-imagine, hierarchical-mlp, image-to-video, inference-speed, inference-speedups, inkling, inkling-small, iteration-speed, mixture-of-experts, mixture-of-transformers, modality-processing, model-simplification, multi-agent-orchestration, multimodal-ai, multimodal-alignment, multimodal-architecture, multimodal-fusion, multimodal-models, multimodal-reasoning, muse-spark, native-multimodal, neural-os, open-weights, open-weights-pivot, real-time-inference, realtime-voice, reasoning-modes, sparse-models, step-distillation, synthetic-captions, temporal-compression, temporal-consistency, text-to-image, text-to-video, thinking-machines, thought-compression, training-efficiency, unified-multimodal, v-parameterization, vaes, video-agents, video-generation, video-models, vision-language-models, visual-impairment-ai, vlm-assistive-tech, voice-activity-detection, wearable-ai, world-models]
---

# Multimodal Models

Tracks the expansion of AI models beyond text: vision-language models (VLMs), audio understanding, video generation, and unified multimodal architectures. Covers GPT-4V, Gemini, Claude's vision, and the techniques for training across modalities.

Key questions tracked: Where are multimodal models actually being deployed in production? What is the gap between text-only and multimodal capability? How does video understanding change the product surface?

## Key Claims
<!-- agent-maintained -->

### Interaction Models: Native Real-Time Multimodal Architecture (Thinking Machines, May 2026)
- **TML-Interaction-Small**: 276B total parameters

### Inkling: Native Multimodal MoE Foundation Model (Thinking Machines Lab, July 2026)
- **Architecture**: Mixture-of-Experts transformer reasoning natively over text, image, and audio
- **Inkling**: 975B total / 41B active parameters
- **Inkling-Small**: 276B total / 12B active parameters  
- **Training**: 45T tokens across text, images, audio, and video
- **Context**: Up to 1M tokens (open weights release)
- **License**: Apache 2.0 open weights
- **Design approach**: Foundation model for customization rather than benchmark maximization; controllable reasoning effort

**Note**: This represents TML's first fully released foundation model family (prior release was Interaction models for real-time voice). Positioned as strongest U.S.-based open-weight multimodal model as of July 2026, though still trailing top Chinese open-weight and closed frontier models on some benchmarks.

See also: [[model-architecture]], [[inference-efficiency]]