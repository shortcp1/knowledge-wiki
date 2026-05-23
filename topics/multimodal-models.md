---
tags: [3d-unet, audio-latency, chameleon, concurrent-processing, ddim, diffusion-models, encoder-free-early-fusion, encoder-free-fusion, flow-matching-decoder, full-duplex-interaction, hierarchical-mlp, mixture-of-experts, multimodal-fusion, multimodal-models, real-time-inference, realtime-voice, temporal-consistency, thinking-machines, v-parameterization, video-generation, vision-language-models, voice-activity-detection]
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
  - **FD-bench V1**: Measures audio latency in conversational turns (TML-Interaction-Small: 0.40s vs GPT-Realtime-2 minimal reasoning: 1.18s)
  - **FD-bench V1.5**: Gauges interruption handling, interjections like "uh huh", and foreground vs background speech (TML-Interaction-Small: 77.8 average quality vs GPT-Realtime-2 xhigh reasoning: 47.8)
  - **Audio MultiChallenge**: Tests reasoning and instruction-following in multi-turn audio dialogue (TML-Interaction-Small: 43.4% APR vs GPT-Realtime-2 xhigh reasoning: 48.5% APR)

#### Technical Architecture Details (May 2026)
- **Two-component system**: Fast interaction model + asynchronous background reasoning model
- **Interaction model**: Processes 200ms micro-turns, interleaving input processing and output generation rather than alternating turns
- **Input processing**:
  - Discretized audio tokens (direct, no large pretrained encoder like Whisper)
  - Image patch embeddings of 40×40 pixels via hierarchical multilayer perceptron (MLP)
  - Text embeddings
  - All streams processed in parallel
- **Output generation**: Flow-matching decoder for audio and text
- **Training approach**: Transformer, hierarchical MLP, and flow-matching decoder trained together from scratch ("encoder-free early fusion" - skips large pretrained encoders)
- **Background model**: Handles reasoning, web browsing, and tool calls asynchronously; shares context with interaction model; outputs woven into conversation when appropriate
- **Architecture undisclosed**: Background model architecture, training data/methods, knowledge cutoff, context window not publicly revealed
- **Performance tradeoff**: Leads on interactivity benchmarks but trails GPT-Realtime-2's strongest reasoning mode on intelligence benchmarks (BigBench Audio: 96.5% vs 96.6% for GPT-Realtime-2 high reasoning)
- **Availability**: Closed research preview in coming months, wider release later in 2026; pricing undisclosed

### Cross-Reference Links
- See [[model-architecture]] for encoder-free early fusion and MoE transformer details
- See [[inference-efficiency]] for latency optimization techniques enabling <200ms processing