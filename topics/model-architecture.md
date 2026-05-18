---
tags: [anthropic, arcee-ai, ascend-npu, attention-mechanisms, automated-research, export-controls, gated-attention, gemma, glm, grouped-query-attention, hifloat4, inference-efficiency, llm-architecture, low-precision-training, mixture-of-experts, model-architecture, model-architecture-comparison, multi-head-attention, nope, open-weight-models, qk-norm, sliding-window-attention, sparse-attention, weak-to-strong-supervision]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging architectures. Focuses on what architectural choices affect capability and efficiency.

Key questions tracked: Is MoE the dominant path to scale? Where are SSMs competitive with transformers? What architectural changes are driving the next generation of frontier models?

## Key Claims

### DeepSeek V4 Architecture (May 2026)
- **V4 Pro**: 1.6T total parameters with 49B active parameters (MoE architecture)
- **V4 Flash**: 284B total parameters with 13B active parameters (MoE architecture)
- **Performance observation**: Flash variant reported as "real star of the show" with relatively strong performance despite smaller size, while Pro "seems to underdeliver relative to its size" (community assessment, not formal benchmark)
- **Long-context optimizations**: Tech report details architectural changes for "better and cheaper long-context performance" (specifics not provided in excerpt)
- **mHC (multi-head compressed attention)**: DeepSeek V4 implements mHC plus compressed attention for KV cache reduction (May 2026)
- **Design motivation**: Architecture focused on reducing KV cache size, memory traffic, and attention cost for reasoning models and agent workflows that maintain many tokens over long contexts
- **Release status**: As of March 22, 2026, DeepSeek V4 had not yet been released (Raschka observation)

### MoE Model Size Trends (May 2026)
- **Xiaomi MiMo-V2.5-Pro**: Unspecified MoE architecture, competitive with other flagship models
- **Google Gemma 4*

### Arcee AI Trinity Large (January 2026)
- **Model family**: Three variants released Jan 27, 2026
  - Trinity Large: 400B total parameters, 13B active (MoE)
  - Trinity Mini: 26B total, 3B active
  - Trinity Nano: 6B total, 1B active
- **Sliding window attention (SWA)**: Alternating local:global attention layers with 3:1 ratio (differs from Gemma 3/Xiaomi's 5:1)
  - Window size: 4096 tokens (similar to Olmo 3)
  - Reduces attention cost from O(n²) to O(n·t) for sequence length n and window size t
  - Global layers support up to 256K token context
- **QK-Norm**: Applies RMSNorm to keys and queries for training stability
- **NoPE (No Positional Embeddings)**: Used in global attention layers (similar to SmolLM3)
- **Gated attention**: Modified attention mechanism with elementwise gating to scaled dot-product before output projection
  - Similar to Qwen3-Next approach (not full Gated DeltaNet)
  - Purpose: Reduces attention sinks, improves long-sequence generalization, aids training stability
- **RMSNorm placement**: Four RMSNorm layers per block (Gemma 3-like placement)
  - Second RMSNorm in each block is depth-scaled: initialized to ~1/sqrt(L) where L = total layers
  - Residual updates start small early in training, grow as model learns appropriate scale
- **Base model performance**: Trinity Large and GLM-4.5 (355B) base models show "practically identical" performance (technical report comparison)
- **Release format**: Open-weight with technical report on GitHub (Feb 18 also on arXiv)

### Architectural Pattern Convergence (Jan-Feb 2026)
- **Sliding window attention ratios**:
  - 3:1 local:global: Arcee Trinity, Olmo 3
  - 5:1 local:global: Gemma 3, Xiaomi MiMo
- **QK-Norm adoption**: Increasingly common for training stability
- **Gated attention mechanisms**: Appearing in multiple architectures (Qwen3-Next, Trinity) as alternative to full Gated DeltaNet