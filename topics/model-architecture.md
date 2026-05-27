---
tags: [compute-costs, transformer-architecture, training-cost, inference-cost, flops-calculation, model-parameters, token-length, model-architecture]
---

=== model-architecture ===
---
tags: [agentic-coding-tools, anthropic, arcee-ai, ascend-npu, attention-mechanisms, audio-latency, automated-research, benchmark-vs-deployment, claude-code, concurrent-processing, context-length, deepseek, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-model-competition, gated-attention, gemini, gemma, glm, grouped-query-attention, hierarchical-mlp, hifloat4, inference-efficiency, llm-architecture, low-precision-training, mixture-of-experts, model-architecture, model-architecture-comparison, model-efficiency, model-specialization, model-training-pipeline, multi-head-attention, nope, open-closed-model-gap, open-weight-models, positional-encoding, qk-norm, real-time-inference, reasoning-models, relative-position-encoding, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, self-attention, sliding-window-attention, sparse-attention, transformer-architecture, weak-to-strong-supervision]
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

### Transformer Computational Costs
- **Training cost rule of thumb**: ~6*p FLOPs per token for model with p parameters
  - Includes forward pass (2p) and backward pass (4p additional operations)
  - Total training cost = 6*p * number of training tokens
  - **Source**: a16z framework, April 2023
- **Inference cost**: ~2*n*p FLOPs for n tokens (see [[inference-efficiency]])
- **GPT-3 training example**: 175B parameters requires ~3.14*10^23 FLOPs total
- **Memory requirements for training**: >1 TB for 175B parameter model at 32-bit precision
  - Exceeds single GPU capacity, requires model splitting across cards
  - **Optimization**: Moving to 16-bit (common as of 2023) and 8-bit (anticipated)

### Model Scale Examples (as of April 2023)
- **GPT-3**: ~175B parameters
- **Meta LLaMA**: Even higher compute requirements than GPT-3
- **Note**: Training these models among most computationally intensive tasks

### Attention Mechanisms

#### Scaled D