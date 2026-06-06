---
tags: [activation-capping, agentic-coding-tools, agentic-reasoning, agentic-tasks, ai-coding-productivity, ai-safety, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autoregressive-reasoner, benchmark-vs-deployment, bert-architecture, character-stability, claude-code, coding-agents, compositional-control, concurrent-processing, context-length, deepseek, diffusion-models, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-model-competition, gated-attention, gemini, gemma, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-speed, inference-throughput, iterative-composition, iterative-evaluation, latent-moe, layer-outputs, llm-architecture, low-precision-training, mamba-attention-hybrid, mixture-of-experts, mixture-of-transformers, model-architecture, model-architecture-comparison, model-efficiency, model-specialization, model-training-pipeline, msa, mtp, multi-head-attention, multimodal-architecture, multimodal-models, nemotron, nope, nvfp4, nvidia, open-closed-model-gap, open-weight-models, open-weights, persona-drift, positional-encoding, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, recursive-self-improvement, relative-position-encoding, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, scene-graphs, self-attention, self-correction, sliding-window-attention, sparse-attention, sparse-models, staged-generation, streaming-asr, swe-bench, text-to-image, text-to-image-generation, transformer-architecture, unified-architecture, unified-model-architecture, unsupervised-pretraining, weak-to-strong-supervision, world-models]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging archi

## NVIDIA Nemotron 3 Ultra

**Architecture (June 2026)**: 550B parameter MoE model with 55B active parameters, 1M context length. Combines:
- **Hybrid Mamba/attention**: Integrates state-space (Mamba) and attention mechanisms
- **LatentMoE**: Advanced mixture-of-experts routing
- **Native MTP** (Model Tensor Parallelism): Built-in parallelization strategy

**Training**: Pretrained on 20T tokens using NVFP4 (NVIDIA's 4-bit floating point format), representing a new scale regime for low-precision pretraining. Released under OpenMDW 1.1 license with full weights, synthetic data, reward checkpoints, quantized variants, and training recipes.

**Performance**: Scores 47.7 on Intelligence Index (NVFP4 weights) / 48.2 (BF16), making it the strongest US open-weights model tested as of June 2026, though behind Kimi K2.6. Optimized for long-running agent workloads with claimed 5x speed improvement and 30% cost reduction for agentic tasks.

See also: [[inference-efficiency]], [[ai-engineering-agents]]