---
tags: [3d-unet, audio-latency, audio-video-alignment, chameleon, concurrent-processing, ddim, diffusion-models, diffusion-transformers, encoder-free-early-fusion, encoder-free-fusion, flipbook, flow-matching-decoder, full-duplex-interaction, generative-ui, grok-imagine, hierarchical-mlp, image-to-video, inference-speedups, iteration-speed, mixture-of-experts, multimodal-alignment, multimodal-fusion, multimodal-models, neural-os, real-time-inference, realtime-voice, step-distillation, synthetic-captions, temporal-compression, temporal-consistency, text-to-video, thinking-machines, v-parameterization, vaes, video-agents, video-generation, video-models, vision-language-models, voice-activity-detection, world-models]
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

## Video Generation Models

### Grok Imagine (xAI, 2026)
- **Development timeline**: Built in 3 months from zero to one at xAI
- **Grok Imagine 0.9**: Includes large-scale audio-video generation capability
- **Core architecture**: Built on diffusion transformers with VAE-based latent space compression
- **Key insight**: "Video models primarily get their intelligence from LLMs, not from training on video data" (Ethan He, xAI)
- **Foundation dependency**: Image models serve as the foundation for video models
- **Training data**: Uses synthetic captions for training (similar to other frontier models)

### Video Agents: The Next Frontier
- **Evolution parallel**: Video generation following similar path to [[agentic-coding-tools]]—moving from one-shot output to multiturn reasoning and planning
- **Agent capabilities**: Systems that can "plan, generate, edit, critique, and iterate across an entire creative task"
- **Grok Imagine Agent**: xAI's video agent system (in development as of mid-2026)
- **Architectural claim**: "Future of video generation may depend more on language models and agents than on diffusion alone"
- **Product hypothesis**: "The next Sora won't be a better video model, but a video agent"

### Audio-Video Alignment
- **Challenge**: Audio-video alignment is harder than text-video alignment
- **Grok Imagine 0.9**: First major xAI release with integrated audio-video generation

### Inference Optimization
- **Step distillation**: Key technique for making video inference "orders of magnitude faster"
- **Consistency models**: OpenAI's sCM (step Consistency Model) as reference implementation
- **GANs**: Also used for fast video inference alongside distillation techniques

### Video Model Capabilities
- **Reference-to-video**: Ability to generate video from reference images/clips
- **Video extension**: Extending existing video clips temporally
- **Long-context video generation**: Managing extended temporal sequences
- **Prompt rewriting**: Critical for video model quality—xAI uses this extensively

## World Models

### Definition and Requirements (Ethan He, xAI)
- **Three key properties**: Real-time, interactive, and long-horizon
- **Temporal compression tradeoff**: Balance between compression efficiency and real-time interactivity requirements
- **Embodied applications**: Robotics and physical AI as key use cases
- **Context**: NVIDIA Cosmos World Model (Ethan He's previous work before xAI)

## Generative UI and Flipbook

### Flipbook Vision
- **Concept**: Video generation as the future interface layer—"from user intent to pixels" without traditional HTML/CSS
- **Alternative names**: Neural OS concept
- **Hypothesis**: As video inference speed and cost improve, custom JIT video UI becomes practical
- **Timeline consideration**: "Future of custom video JIT UI is closer than you think" with improving inference economics

## Training Infrastructure and Costs

### Hidden Costs of Video Models
- **Storage**: Massive video dataset storage requirements
- **Egress costs**: Moving large video datasets between systems
- **GPU hours**: Compute requirements for training
- **Data pipeline bugs**: "Small training bugs can drive huge model quality gains"—debugging data/training pipelines yields outsized returns

### Development Speed
- **Iteration speed**: "Matters more than almost anything in model development"
- **xAI culture impact**: Fast iteration prioritized over meetings enabled 3-month Grok Imagine development

## Safety and Detection

### AI Watermarking
- **SynthID**: Google's watermarking approach for generated media
- **Detection challenge**: Identifying AI-generated video and images