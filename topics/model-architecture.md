---
tags: [anthropic, arcee-ai, ascend-npu, attention-mechanisms, automated-research, context-length, deepseek, encoder-decoder-architecture, export-controls, gated-attention, gemma, glm, grouped-query-attention, hifloat4, inference-efficiency, llm-architecture, low-precision-training, mixture-of-experts, model-architecture, model-architecture-comparison, model-efficiency, model-training-pipeline, multi-head-attention, nope, open-weight-models, positional-encoding, qk-norm, reasoning-models, relative-position-encoding, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, self-attention, sliding-window-attention, sparse-attention, transformer-architecture, weak-to-strong-supervision]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging architectures. Focuses on what architectural choices affect capability and efficiency.

Key questions tracked: Is MoE the dominant path to scale? Where are SSMs competitive with transformers? What architectural changes are driving the next generation of frontier models?

## Key Claims

### Vanilla Transformer Architecture (2017)
- **Encoder-decoder architecture**: Original Transformer uses encoder-decoder structure, as commonly used in NMT models (Vaswani et al., 2017)
- **Simplified variants**: Later simplified Transformers showed strong performance:
  - **Encoder-only**: BERT architecture
  - **Decoder-only**: GPT architecture
- **Core mechanism**: Scaled dot-product attention as fundamental operation

### Attention Mechanisms

#### Scaled Dot-Product Attention (2017)
- **Formula**: $\text{attn}(\mathbf{Q}, \mathbf{K}, \mathbf{V}) = \text{softmax}(\frac{\mathbf{Q} {\mathbf{K}}^\top}{\sqrt{d_k}})\mathbf{V}$
- **Scalar attention score**: Between query $\mathbf{q}_i$ and key $\mathbf{k}_j$: $a_{ij} = \text{softmax}(\frac{\mathbf{q}_i {\mathbf{k}_j}^\top}{\sqrt{d_k}})$
- **Output**: Weighted sum of value vectors, where weights determined by dot-product of query with corresponding key
- **Scaling factor**: Division by $\sqrt{d_k}$ where $d_k$ is key dimension

#### Self-Attention Properties
- **Definition**: Mechanism where model makes predictions for one part of data sample using other parts of same sample
- **Permutation invariance**: Self-attention is an operation on sets (order-independent without positional encoding)
- **Conceptual similarity**: Related to non-local means in signal processing

#### Multi-Head Self-Attention
- **Weight matrices per head**: $\mathbf{W}^k_i, \mathbf{W}^q_i \in \mathbb{R}^{d \times d_k/h}$; $\mathbf{W}^v_i \in \mathbb{R}^{d \times d_v/h}$ where $h$ is number of heads
- **Output projection**: $\mathbf{W}^o \in \mathbb{R}^{d_v \times d}$
- **Standard dimensions**: Often $d_k = d_v = d$ (model dimension)

### Positional Encoding Variants

#### Sinusoidal Positional Encoding (2017)
- **Type**: Fixed, non-learned positional encoding in original Transformer
- **Encoding matrix**: $\mathbf{P} \in \mathbb{R}^{L \times d}$ where $\mathbf{p}_i$ is positional encoding for input $\mathbf{x}_i$

#### Learned Positional Encoding
- **Type**: Trainable positional embeddings (alternative to sinusoidal)

#### Relative Position Encoding
- **Type**: Encodes relative rather than absolute positions
- **Cross-reference**: See [[attention-mechanisms]] for implementation details

#### Rotary Position Embedding (RoPE)
- **Type**: Rotation-based positional encoding
- **Cross-reference**: See [[attention-mechanisms]] for technical details

### DeepSeek V3 Architecture (December 2024)
- **Base model release**: DeepSeek V3 released December 2024 as base model
- **Architecture foundation**: Used as base for DeepSeek R1 reasoning model (identical architecture with additional post-training)
- **Design pattern**: Base model approach (as opposed to hybrid reasoning model)

### DeepSeek V3.2 Architecture (December 2025)
- **Release date**: January 1, 2026 (final update); initial release December 2025
- **Performance claim**: Benchmarks show performance on par with GPT-5 and Gemini 3.0 Pro level (per DeepSeek V3.2 report)
- **Status**: Available as open-weight model
- **Sparse attention variant**: Uses "non-standard sparse attention variant that requires custom code" (specifics not detailed in excerpt)
- **Experimental release**: DeepSeek V3.2-Exp released prior to V3.2 to prepare ecosystem and inference infrastructure for custom sparse attention implementation

### DeepSeek V3.1 (2025)
- **Release status**: Smaller