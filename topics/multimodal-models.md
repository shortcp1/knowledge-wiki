---
tags: [3d-unet, audio-latency, audio-video-alignment, autoregressive-reasoner, chameleon, concurrent-processing, ddim, diffusion-models, diffusion-transformers, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, flipbook, flow-matching-decoder, full-duplex-interaction, gemma, gemma-4, generative-ui, grok-imagine, hierarchical-mlp, image-to-video, inference-speed, inference-speedups, iteration-speed, mixture-of-experts, mixture-of-transformers, modality-processing, model-simplification, multi-agent-orchestration, multimodal-alignment, multimodal-architecture, multimodal-fusion, multimodal-models, multimodal-reasoning, muse-spark, native-multimodal, neural-os, open-weights, open-weights-pivot, real-time-inference, realtime-voice, reasoning-modes, sparse-models, step-distillation, synthetic-captions, temporal-compression, temporal-consistency, text-to-image, text-to-video, thinking-machines, thought-compression, training-efficiency, unified-multimodal, v-parameterization, vaes, video-agents, video-generation, video-models, vision-language-models, voice-activity-detection, world-models]
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

### Meta Muse Spark: Natively Multimodal Reasoning Model (Meta, April 2026)
- **Design philosophy**: "Natively multimodal reasoning model" - Meta's first closed model departure from open-weights Llama strategy
- **Input/Output**: Text, image, speech input (up to 262,000 tokens), text output
- **Undisclosed details**: Parameter count, architecture specifics, training data/methods, output size limit
- **Training efficiency claim**: Matches Llama 4 Maverick's capabilities with "over an order of magnitude less processing" devoted to training
- **Multi-agent orchestration**: Contemplating mode launches multiple agents that "propose solutions, refine them, and aggregate the results in parallel"
- **Domain specialization**: Health reasoning enhanced via 1,000+ physicians helping curate training data

### Benchmark Performance: Muse Spark (April 2026)
- **Artificial Analysis Intelligence Index**: 4th place (52) behind Gemini 3.1 Pro Preview + GPT-5.4 (tied 57) and Claude Opus 4.6 (53)
- **Token efficiency**: ~59M tokens to complete index vs ~158M (Claude Opus 4.6) and ~116M (GPT-5.4)
- **CharXiv Reasoning** (charts/figures): 86.4% (1st place, per Meta) vs GPT-5.4 (82.8%) and Gemini 3.1 Pro (80.2%)
- **MMMU Pro** (multidisciplinary visual): 81% (2nd place) behind Gemini 3.1 Pro (82%)
- **Coding Index weakness**: 47 vs GPT-5.4 (57), Gemini 3.1 Pro Preview (56), Claude Sonnet 4.6 (51)
- **Humanity's Last Exam**: 39.9% (Thinking mode, Artificial Analysis) vs 58% (Contemplating mode, Meta's tests) - note significant mode-dependent variance
- **HealthBench Hard**: 42.8% (1st place, Meta's tests) vs GPT-5.4 (40.1%)
- **DeepSearchQA** (agentic browsing): 74.8% (1st place) vs Claude Opus 4.6 Max (73.7%)
- **Performance gaps acknowledged by Meta**: Coding and general agentic tasks