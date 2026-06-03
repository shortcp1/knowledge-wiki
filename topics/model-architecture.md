---
tags: [activation-capping, agentic-coding-tools, ai-safety, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autoregressive-reasoner, benchmark-vs-deployment, bert-architecture, character-stability, claude-code, compositional-control, concurrent-processing, context-length, deepseek, diffusion-models, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-model-competition, gated-attention, gemini, gemma, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-speed, inference-throughput, iterative-composition, layer-outputs, llm-architecture, low-precision-training, mixture-of-experts, mixture-of-transformers, model-architecture, model-architecture-comparison, model-efficiency, model-specialization, model-training-pipeline, msa, multi-head-attention, multimodal-architecture, multimodal-models, nope, open-closed-model-gap, open-weight-models, open-weights, persona-drift, positional-encoding, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, relative-position-encoding, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, scene-graphs, self-attention, self-correction, sliding-window-attention, sparse-attention, sparse-models, staged-generation, text-to-image, text-to-image-generation, transformer-architecture, unified-architecture, unified-model-architecture, unsupervised-pretraining, weak-to-strong-supervision, world-models]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging architectures. Focuses on what architectural choices affect capability and efficiency.

Key questions tracked: Is MoE the dominant path to scale? Where are SSMs competitive with transformers?

## Mixture-of-Transformers Architecture

### NVIDIA Cosmos 3 (June 2026)
- **Architecture pattern**: Mixture-of-Transformers pairing an autoregressive reasoner tower with a diffusion generator tower
- **Model sizes**:
  - Nano: 16B total (8B reasoner + 8B generator)
  - Super: 64B total (32B reasoner + 32B generator)
- **Modality coverage**: Unified language, image, video, audio, and action in single architecture
- **Interface design**: Generator uses structured JSON prompts; can be driven by external prompt-upsampling harness or its own reasoner branch
- **Performance claim**: #1 open-weight model on Text-to-Image and Image-to-Video leaderboards (Artificial Analysis, June 2026)
- **Cross-reference**: See [[multimodal-models]] for world model applications

### NVIDIA Nemotron 3 Ultra (June 2026)
- **Architecture**: 550B total parameters, ~55B active (MoE)
- **Sparsity characteristics**: ~10% active parameters (less sparse than DeepSeek V4/Kimi K2 at ~3% active)
  - *Note*: Higher activation rate may affect both serving economics and model behavior vs. ultra-sparse alternatives
- **Inference claims**: Reports of 300+ tokens/sec serving speeds in some configurations (unverified)
- **Performance positioning**: Described as "strongest U.S. open model" as of June 2026 (community claims, confidence: medium)
- **Cross-reference**: See [[gpu-architecture-training-infra]] for serving infrastructure implications

## Open Weight Model Ecosystem Dynamics

### MiniMax M3 (June 2026)
- **Configuration**: Open-weight multimodal agent/coding model with 1M context
- **Benchmark claims**:
  - SWE-Bench Pro: 59.0%
  - Terminal Bench 2.1: 66.0%
  - MCP Atlas: 74.2%
- **Ecosystem adoption pattern**: Day-0 support from multiple infrastructure vendors (Novita, Vercel, Cloudflare, OpenClaude, Flowith) suggests coordinated launch
- **Practical use reports**: Strong on frontend generation and visual/game tasks; mixed results on other benchmarks vs. practical deployment