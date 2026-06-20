---
tags: [activation-capping, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-tasks, ai-coding-productivity, ai-safety, aliasing-errors, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autoregressive-reasoner, benchmark-methodology, benchmark-performance, benchmark-vs-deployment, bert-architecture, block-generation, chaotic-systems, character-stability, claude-code, claude-fable-5, claude-mythos, coding-agents, coding-benchmarks, coding-models, common-crawl, composer, compositional-control, concurrent-processing, context-caching, context-length, context-window, culturax, cursor, data-retention-policy, deepseek, dense-attention, diffusion-generation, diffusion-models, diffusion-text-generation, diffusiongemma, encoder-decoder-architecture, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, energy-efficiency, evaluation-transparency, export-controls, flow-matching-decoder, fluid-dynamics-simulation, frontend-coding, frontier-code-benchmark, frontier-model-competition, frontier-models, gated-attention, gemini, gemma, gemma-4, glm, glm-5.2, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, indexshare, inductive-bias, inference-efficiency, inference-optimization, inference-speed, inference-throughput, iterative-composition, iterative-evaluation, kimi, language-specific-bias, latent-moe, layer-outputs, llm-architecture, long-context, long-context-optimization, low-precision-training, ma-activity, mamba-attention-hybrid, meta-superintelligence-labs, mixture-of-experts, mixture-of-transformers, modality-processing, model-architecture, model-architecture-comparison, model-downgrading, model-efficiency, model-evaluation, model-fallback, model-fusion, model-routing, model-safeguards, model-simplification, model-specialization, model-training-pipeline, moonshot, msa, mtp, multi-agent-orchestration, multi-head-attention, multimodal-architecture, multimodal-models, multimodal-reasoning, muse, quadratic-complexity, sparse-attention, subquadratic, transformer-architecture]
---

## Dense Attention (Transformer Core Mechanism)

**Standard Operation**: The foundational mechanism in most LLMs since the 2017 "Attention Is All You Need" paper (Google)

### How Dense Attention Works
- Encodes each word/token with a number
- Multiplies each token's number with **every other token's number** in the input text
- Computational complexity: **quadratic** (doubles input length → roughly quadruples computations)
- Example: 10,000 words triggers ~50 million multiplications

### Computational Cost Implications
- Primary reason LLMs are power-intensive
- Creates bottleneck for context window scaling
- Each additional token must be multiplied by all previous tokens

### Architecture Variants
Most current LLMs chain multiple transformers using dense attention as the core operation.

See also: [[sparse-attention]], [[inference-efficiency]], [[attention-mechanisms]]

## Sparse Attention Alternative

**Key Innovation**: Selects only **some** token numbers to multiply, rather than all pairs

### Computational Benefits
- Reduces number of computations from quadratic scaling
- Enables longer context windows with less computation
- Lower energy consumption

### Known Implementations
- **DeepSeek Sparse Attention**: Used as foundation for [[indexshare]] in [[glm-5.2]]
- **SubQ (Subquadratic)**: Announced June 2026, replaces dense attention entirely

### SubQ Architecture

**Developer**: Subquadratic (Miami-based startup)  
**Announced**: May 2026 (stealth exit)  
**Status**: Not widely available as of June 2026

**Claims** (verified by third-party evaluation from Appen, June 2026):
- Faster inference than existing top models
- Lower cost per operation
- Significantly reduced energy consumption
- Processes up to **12x more text** than most other models at once
- Performance comparable to Google DeepMind, OpenAI, and Anthropic models on coding tasks

**Architecture Approach**: Abandons transformer dense attention mechanism entirely in favor of sparse attention

**Confidence Level**: Medium-High. Independent third-party benchmarks (Appen) validate performance claims, but model not yet publicly testable. Jeanine Sinanan-Singh (Appen's Director of Generative AI Research) confirmed validation of architecture.

**Company Vision**: "We don't think anybody will be building on transformers in a few years" - Justin Dangel, CEO

**Note**: Initial announcement met with skepticism due to limited evidence. Later third-party benchmarks addressed concerns. Model specializes in data-heavy tasks (analyzing hundreds of documents, entire code bases).

See also: [[inference-efficiency]], [[long-context]]