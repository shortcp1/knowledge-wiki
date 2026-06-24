---
tags: [4-bit-quantization, agentic-tasks, code-generation-agents, coding-benchmarks, coding-models, context-window, context-window-expansion, deepseek, dense-attention, energy-efficiency, external-memory-management, frontend-coding, glm-5.2, hybrid-transformer-mamba, indexshare, inference-efficiency, inference-optimization, inference-speed, latent-moe, long-context, long-context-processing, ma-activity, meta-learning, mixture-of-experts, model-fusion, mtp, multi-teacher-distillation, multi-token-prediction, nemotron-3-ultra, nvfp4, nvidia, open-source-models, open-weights, quadratic-complexity, read-evaluate-print-loop, recursive-language-models, rlm, sliding-window-attention, sparse-attention, speculative-decoding, subquadratic, test-time-training, tokens-per-second, transformer-architecture, ttt-e2e, weight-compression, weight-update]
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
- **DeepSeek Sparse Attention**: Foundation for IndexShare extension

## Recursive Language Models (RLMs)

**Introduced**: March 2026  
**Developers**: MIT (Alex L. Zhang, Tim Kraska, Omar Khattab)  
**Purpose**: Process inputs beyond context window limits by treating context as external variable

### Core Architecture
- Offloads prompts to external programming environment (Python REPL)
- Root model generates code to manipulate context programmatically
- Spawns submodel instances to handle subtasks iteratively
- Context stored as persistent variables rather than in-context tokens

### Technical Mechanism
1. Task data loaded into Python interpreter as variable
2. Root model inspects, chunks, and decomposes tasks via code generation
3. Submodels process individual chunks according to root model instructions
4. Intermediate results stored as variables and aggregated by root model

### Implementations Tested
- **RLM-Qwen3-8B** (32,768-token base context window)
- **RLM-GPT-5** with medium reasoning (400,000-token base context window)
- **RLM-Qwen3-Coder-480B** (256,000-token base context window)

### Performance Characteristics
- **BrowseComp+** (multi-document Q&A): RLM-GPT-5 achieved 91.3% accuracy vs. GPT-5 unable to answer due to context limits; outperformed summary agent at 70.5%
- **OOLONG-PAIRS** (32K tokens): RLM-GPT-5 achieved 58% accuracy vs. GPT-5 near 0%; maintained ~50% accuracy even at 1M tokens
- Successfully handles up to 11 million tokens total across multiple documents
- Significantly outperforms retrieval-augmented and summarization approaches

### Advantages Over Alternative Approaches
- **vs. Retrieval methods**: Avoids losing critical details through selective retrieval
- **vs. Summarization**: Preserves information that may be compressed away
- **vs. Direct long-context processing**: Reduces hallucination and detail loss in ultra-long contexts
- Enables decomposition of complex tasks before holistic processing

### Relationship to Other Techniques
- See [[agentic-workflows-production]] for agentic framework architecture
- Complements but differs from sparse attention approaches (algorithmic vs. architectural solution)
- Alternative to context window expansion strategies in [[model-architecture]]