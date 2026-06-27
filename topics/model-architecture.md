---
tags: [4-bit-quantization, activation-capping, agentic-ai, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-tasks, ai-coding-productivity, ai-lab-government-relations, ai-safety, aliasing-errors, anthropic, apple-foundation-models, apple-silicon, arcee-ai, architecture-invariant-exponents, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autonomous-coding, autoregressive-reasoner, benchmark-methodology, benchmark-performance, benchmark-vs-deployment, bert-architecture, block-generation, chaotic-systems, character-stability, chinchilla-scaling, claude-code, claude-fable-5, claude-mythos, code-generation-agents, coding-agents, coding-benchmarks, coding-models, common-crawl, composer, compositional-control, compute-allocation, concurrent-processing, context-caching, context-length, context-window, context-window-expansion, cost-efficiency, culturax, cursor, cybersecurity-capabilities, data-retention-policy, data-scaling, deepseek, dense-attention, diffusion-generation, diffusion-models, diffusion-text-generation, diffusiongemma, distillation, encoder-decoder-architecture, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, energy-efficiency, evaluation-transparency, expert-routing, export-controls, external-context-management, external-memory-management, flash-memory-storage, flow-matching-decoder, fluid-dynamics-simulation, frontend-coding, frontier-code-benchmark, frontier-model-competition, frontier-models, gated-attention, gemini, gemma, gemma-4, generalization-error, glm, glm-5.2, google-apple-partnership, gpu-optimization, group-relative-policy-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, hybrid-transformer-mamba, index-as-model, indexcache, indexshare, inductive-bias, inference-efficiency, inference-optimization, inference-speed, inference-throughput, instruction-following-pruning, iterative-composition, iterative-evaluation, kaplan-scaling-laws, kimi, language-specific-bias, latent-moe, layer-outputs, llm-architecture, long-context, long-context-optimization, long-context-processing, low-precision-train, mixture-of-experts, mixture-of-experts-alternatives, model-architecture, model-distillation, multimodal-models, on-device-inference, on-device-models]
---

## Instruction-Following Pruning

**Introduced**: AFM 3 Core Advanced (Apple Foundation Models, 2026)
**Developer**: Apple (in partnership with Google)
**Purpose**: Alternative to mixture-of-experts (MoE) architecture optimized for on-device inference with reduced memory footprint

### Technical Details
- **Architecture modification**: Uses a separate transformer to select which experts to activate, rather than routing layers within the model
- **Key optimization**: Same experts are used across multiple tokens (not switched per-token like traditional MoE)
- **Model size**: 20 billion parameters total, 1-4 billion parameters active during inference
- **Memory advantage**: Enables storing model in flash memory rather than requiring all experts in active memory (RAM/VRAM)
- **Performance claim**: Faster inference than typical mixture-of-experts models of equivalent size
- **Flash memory viability**: Unlike traditional MoE which requires loading all experts into RAM, instruction-following pruning makes token-by-token loading from flash practical

### Trade-offs vs Traditional MoE
- **Traditional MoE**: Routes per token, requires entire model in active memory
- **Instruction-Following Pruning**: Routes per multiple tokens, allows flash memory storage
- **Result**: Enables larger, more capable models on memory-constrained devices

### Integration Context
- Part of Apple Foundation Models 3 (AFM 3) family
- Models are distillation-based from Google [[gemini]] models (confirmed by Apple VP of AI Amar Subramanya)
- Optimized for Apple silicon
- Supports multimodal capabilities: text, images, speech input; text, speech output
- 25 languages supported
- Available on Macs and iPhone 17 Pro/Max/Air (fall 2026)

### Training Pipeline
- Pretraining on mixture of public data, licensed data, study data, and generated data
- No user data or user interactions included in training
- Supervised fine-tuning
- Reinforcement learning

**Note**: Benchmark results not yet published as of June 2026. Apple claims improvements over AFM 2 generation in proprietary human preference measurements.

See also: [[inference-efficiency]], [[gpu-architecture-training-infra]], [[on-device-ai]]