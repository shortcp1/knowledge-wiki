---
tags: [4-bit-quantization, agentic-ai, agentic-tasks, code-generation-agents, coding-benchmarks, coding-models, context-window, context-window-expansion, deepseek, dense-attention, energy-efficiency, external-memory-management, frontend-coding, glm-5.2, hybrid-transformer-mamba, indexshare, inference-efficiency, inference-optimization, inference-speed, latent-moe, long-context, long-context-processing, ma-activity, mamba-2, meta-learning, mixture-of-experts, model-fusion, mtp, multi-teacher-distillation, multi-token-prediction, nemotron-3-super, nvfp4, nvidia, open-source-models, open-weights, quadratic-complexity, read-evaluate-print-loop, recursive-language-models, rlm, sliding-window-attention, sparse-attention, speculative-decoding, subquadratic, test-time-training, tokens-per-second, transformer-architecture, ttt-e2e, weight-compression, weight-update]
---

## IndexShare for Speculative Decoding

**Introduced**: GLM-5.2 (June 2026)  
**Developer**: Z.ai  
**Purpose**: Improved multi-token prediction (MTP) to boost acceptance rates in speculative decoding

### Technical Details
- Extension built on top of DeepSeek Sparse Attention
- Specifically optimized for ultra-long context windows (1M tokens)
- Enhances speculative decoding acceptance rates, improving overall inference throughput
- Works in conjunction with sparse attention mechanisms for efficiency gains

### Implementation Context
- Part of [[glm-5.2]] architecture enabling 1M context window performance
- Contributes to competitive inference speeds despite 744B parameter count
- Supports both "high" and "max" reasoning effort modes

**Note**: Technical disclosures are limited; no full paper released as of June 2026, only mention of "minor improvement" on DeepSeek Sparse Attention

## Sparse Attention for Efficiency Gains

### Computational Benefits Over Dense Attention
- **Sparse attention** selects subset of token pairs to multiply, avoiding quadratic scaling
- Enables longer context processing with fewer computations

## Multi-Token Prediction for Inference Speed

### Nemotron 3 Super Implementation
**Model**: [[nemotron-3-super]] (March 2026, Nvidia)  
**Performance**: ~442 output tokens per second (fastest open-weights in 120B class)

#### Technical Mechanism
- **MTP heads** integrated into hybrid mamba-2/transformer/MoE architecture
- Predict multiple output tokens per forward pass
- During inference: drafts tokens, verifies in single pass, keeps consistent tokens, discards inconsistent
- Functions as built-in [[speculative-decoding]] mechanism
- **Training benefit**: Encourages model to learn longer-range patterns

#### Efficiency Synergies
- Combined with mamba-2 layers (avoid quadratic attention complexity)
- Works with [[latent-moe]] compression (1/4 token representation size before routing)
- Enables 22 experts per token activation with ~5-6 expert equivalent processing cost

### Comparison to Other MTP Approaches
- [[glm-5.2]] uses IndexShare (multi-token prediction for speculative decoding with sparse attention)
- Nemotron 3 Super integrates MTP directly into architecture with mamba-2/attention hybrid

## Low-Precision Training for Inference Efficiency

### NVFP4 Native Training
**Implementation**: [[nemotron-3-super]]  
**Approach**: Pretrained in NVFP4 (4-bit floating-point, native to Nvidia Blackwell architecture)

#### Benefits
- Model learns to operate with reduced precision during training
- Avoids accuracy loss from post-training quantization
- Direct compatibility with hardware acceleration
- Related to [[hifloat4]] format approaches

**Contrast**: Traditional approach quantizes models after training, potentially degrading performance

## Mamba-2 for Subquadratic Scaling

### Computational Properties
**Used in**: [[nemotron-3-super]] (majority of layers)

#### Efficiency Characteristics
- Compresses earlier context into compact representation at each step
- **Avoids quadratic scaling** with input length (unlike standard attention)
- Enables processing of million-token contexts efficiently

#### Architectural Trade-offs
- **Weakness**: Struggles with precise retrieval from distant input parts
- **Solution**: Selective interleaving of attention layers for tasks requiring long-range precision
- Hybrid approach balances efficiency with capability