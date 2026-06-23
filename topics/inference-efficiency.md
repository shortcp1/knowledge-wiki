---
tags: [4-bit-quantization, agentic-tasks, coding-benchmarks, coding-models, context-window, deepseek, dense-attention, energy-efficiency, frontend-coding, glm-5.2, hybrid-transformer-mamba, indexshare, inference-efficiency, inference-optimization, inference-speed, latent-moe, long-context, ma-activity, meta-learning, mixture-of-experts, model-fusion, mtp, multi-teacher-distillation, multi-token-prediction, nemotron-3-ultra, nvfp4, nvidia, open-source-models, open-weights, quadratic-complexity, sliding-window-attention, sparse-attention, speculative-decoding, subquadratic, test-time-training, tokens-per-second, transformer-architecture, ttt-e2e, weight-compression, weight-update]
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
- Significantly reduces energy consumption
- See [[model-architecture]] for technical comparison with dense attention

### Known Implementations
- **DeepSeek Sparse Attention**: Foundation for IndexShare optimization
- **SubQ (Subquadratic)**: Claims 12x context lengt

## Test-Time Training End-to-End (TTT-E2E)

**Introduced**: April 2026  
**Developers**: Astera Institute (nonprofit), Nvidia, Stanford, UC Berkeley, UC San Diego  
**Architecture**: 3B parameter transformer with sliding-window attention

### Problem Addressed
- Traditional transformers attend to entire context, causing each output token to require more processing than the last
- Results in increasing inference time and cost as context grows
- Accuracy typically degrades with longer contexts

### Technical Approach
**Core Innovation**: Compresses context into model weights through inference-time training rather than attending to full context

**Architecture Decisions**:
- Sliding-window attention restricted to fixed 8,000 token window
- Only updates fully connected layers in last quarter of network during inference
- Maintains constant time per output token regardless of context length

### Training Methodology
**Dual-Loop Meta-Learning Structure**:

**Inner Loop** (simulates inference-time learning):
1. Splits training sequence into 1,000-token chunks
2. Uses sliding-window attention to predict each token
3. Computes next-token prediction loss
4. Calculates weight updates for fully connected layers in final quarter of network
5. Produces sequence of weight updates (one per 1,000 tokens)

**Outer Loop** (meta-optimization):
1. Computes average next-token prediction loss after simulated weight updates
2. Backpropagates through sequence of simulated weight updates (gradient-of-gradients)
3. Updates entire model's weights

**Training Data**:
- Pretraining: 164B tokens in 8,000-token sequences from filtered web scrape
- Fine-tuning: Up to 128,000-token sequences from Books subset of The Pile

### Inference Process
1. Splits input context into chunks
2. Calculates next-token prediction loss on chunks
3. Updates only fully connected layers in last quarter of network
4. Generates new tokens with constant processing time per token

**Note**: Inference uses only inner loop, avoiding gradient-of-gradients computation required in training

### Performance Characteristics

**Accuracy**:
- Slightly exceeds vanilla transformer over long contexts (average 0.015 lower loss)
- Maintains stable accuracy from 8,000 to 128,000 token contexts
- Outperforms Mamba 2 and Gated DeltaNet (0.03 loss advantage)
- **Exception**: Matched but did not exceed other models on Needle-in-a-Haystack (NIAH) task for exact string retrieval

**Speed**:
- Constant inference time regardless of context length
- Matches inference speed of efficient architectures (Mamba 2, Gated DeltaNet)
- Comparable to models specifically designed for efficiency

**Training Trade-off**:
- Slower and more complex training due to gradient-of-gradients computation in outer loop
- Increased training time cost for inference speed benefits

### Architectural Comparisons
Tested against:
- Vanilla transformer with conventional attention
- [[mamba-transformer-hybrid]] (Mamba 2) - recurrent neural network-style
- Gated DeltaNet - custom linear attention

### Context Window Performance
- Evaluated on contexts from 8,000 to 128,000 tokens
- Unlike traditional transformers, maintains constant per-token generation time across all context lengths
- Contrast with sparse attention approaches that reduce but don't eliminate quadratic scaling

**Confidence**: High - published research with specific benchmark comparisons and architectural details