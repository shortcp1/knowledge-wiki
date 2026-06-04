---
tags: [activation-capping, agentic-coding-tools, agentic-reasoning, ai-safety, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autoregressive-reasoner, benchmark-vs-deployment, bert-architecture, character-stability, claude-code, coding-agents, compositional-control, concurrent-processing, context-length, deepseek, diffusion-models, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-model-competition, gated-attention, gemini, gemma, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-speed, inference-throughput, iterative-composition, iterative-evaluation, layer-outputs, llm-architecture, low-precision-training, mixture-of-experts, mixture-of-transformers, model-architecture, model-architecture-comparison, model-efficiency, model-specialization, model-training-pipeline, msa, multi-head-attention, multimodal-architecture, multimodal-models, nope, open-closed-model-gap, open-weight-models, open-weights, persona-drift, positional-encoding, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, relative-position-encoding, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, scene-graphs, self-attention, self-correction, sliding-window-attention, sparse-attention, sparse-models, staged-generation, swe-bench, text-to-image, text-to-image-generation, transformer-architecture, unified-architecture, unified-model-architecture, unsupervised-pretraining, weak-to-strong-supervision, world-models]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging architectures. Focuses on what architectural choices affect capability a

## GLM-5.1 Architecture (Z.ai, April 2026)

**Scale**: Mixture-of-experts transformer, 754 billion parameters total, 40 billion parameters active per token (~5.3% activation rate)

**Context/Output**: Up to 200,000 input tokens, up to 128,000 output tokens

**License**: MIT license (open-weights, commercial use allowed)

**Technical details**: Z.ai has not published a technical report specific to GLM-5.1. Appears to follow GLM-5's basic architecture, attention mechanism, and pretraining approach. Key architectural innovation is in the inference loop rather than model structure itself (see [[inference-time-compute]] and [[ai-engineering-agents]]).

**Optimization target**: Specifically optimized for agentic coding tasks, though methods not disclosed.