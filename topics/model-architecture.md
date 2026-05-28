---
tags: [agentic-coding-tools, anthropic, arcee-ai, ascend-npu, attention-mechanisms, audio-latency, automated-research, benchmark-vs-deployment, bert-architecture, claude-code, concurrent-processing, context-length, deepseek, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-model-competition, gated-attention, gemini, gemma, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-throughput, llm-architecture, low-precision-training, mixture-of-experts, model-architecture, model-architecture-comparison, model-efficiency, model-specialization, model-training-pipeline, msa, multi-head-attention, nope, open-closed-model-gap, open-weight-models, positional-encoding, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, relative-position-encoding, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, self-attention, sliding-window-attention, sparse-attention, transformer-architecture, unified-architecture, unified-model-architecture, unsupervised-pretraining, weak-to-strong-supervision, world-models]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging architectures. Focuses on what architectural choices affect capability and efficiency.

Key questions tracked: Is MoE the dominant path to scale? Where are SSMs competitive with transformers? What architectural changes are driving the next generation of frontier models?

## Key Claims

### Vanilla Transformer Architecture (2017)
- **Encoder-decoder

## Unified Model Architectures for Retrieval

### SilverTorch "Index as Model" (Meta, May 2026)
- **Paradigm**: Replace microservice-based retrieval with single integrated neural network
- **Architecture components expressed as model modules**:
  - User-tower (user embedding computation)
  - Item index (becomes tensor inside model rather than external service)
  - Similarity search
  - Eligibility filtering (language, geography, etc.)
  - Neural reranking
  - Multi-task scoring (multiple engagement actions)
- **Design rationale**: Eliminates version inconsistency between components (user model v2 querying item index v1), enables joint optimization across retrieval stages
- **Scale**: Deployed for 80M+ item retrieval at sub-100ms latency
- **Context**: Represents shift from CPU-era microservice design to GPU-native unified architecture for recommendation systems

See also: [[inference-efficiency]] for performance characteristics