---
tags: [anthropic, arcee-ai, ascend-npu, attention-mechanisms, audio-latency, automated-research, concurrent-processing, context-length, deepseek, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, gated-attention, gemma, glm, grouped-query-attention, hierarchical-mlp, hifloat4, inference-efficiency, llm-architecture, low-precision-training, mixture-of-experts, model-architecture, model-architecture-comparison, model-efficiency, model-training-pipeline, multi-head-attention, nope, open-weight-models, positional-encoding, qk-norm, real-time-inference, reasoning-models, relative-position-encoding, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, self-attention, sliding-window-attention, sparse-attention, transformer-architecture, weak-to-strong-supervision]
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
- **Scalar attention score**: Between query $\mathbf{q}_i$ and key $\mathbf{k}_j$: $a_{ij} = \text{softmax}(\frac{\mathbf{q}_i \cdot \mathbf{k}_j}{\sqrt{d_k}})$

### Encoder-Free Early Fusion (Thinking Machines, May 2026)
- **Design principle**: Skip large pretrained encoders (e.g., OpenAI Whisper for audio, vision transformers for images) and instead train all components together from scratch
- **TML-Interaction-Small implementation**:
  - **Audio**: Direct discretized audio tokens (no large pretrained encoder)
  - **Vision**: Image patch embeddings (40×40 pixels) via hierarchical multilayer perceptron
  - **Text**: Direct text embeddings
  - **Training**: Transformer, hierarchical MLP, and flow-matching decoder trained end-to-end
- **Output**: Flow-matching decoder generates both audio and text
- **Rationale**: Enables tighter integration for real-time multimodal interaction; eliminates encoder bottlenecks
- **Related**: Similar philosophy to Meta's Chameleon for multimodal fusion
- See [[multimodal-models]] for full system architecture and [[inference-efficiency]] for latency implications