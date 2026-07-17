---
tags: [2-8t-parameters, 4-bit-quantization, activation-capping, active-parameters, agentic-ai, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-systems, agentic-tasks, ai-coding-productivity, ai-lab-government-relations, ai-safety, ai-safety-evaluations, aliasing-errors, anthropic, anthropic-research, apache-2-license, apple-foundation-models, apple-silicon, arcee-ai, architecture-invariant-exponents, ascend-npu, assistant-alignment, attention-mechanisms, attention-residuals, audio-latency, automated-research, autonomous-agents, autonomous-coding, autoregressive-reasoner, benchmark-cost-metrics, benchmark-methodology, benchmark-performance, benchmark-vs-deployment, bert-architecture, block-generation, capability-trajectory, capture-the-flag, chaotic-systems, character-stability, chinchilla-scaling, claude-3-7-sonnet, claude-code, claude-fable-5, claude-mythos, claude-opus-4-6, claude-sonnet-5, code-generation-agents, coding-agents, coding-benchmarks, coding-models, common-crawl, composer, compositional-control, compound-ai-systems, compute-allocation, concurrent-processing, context-caching, context-length, context-management, context-orchestration, context-window, context-window-expansion, continual-learning, controllable-reasoning-effort, conversational-personality, cost-efficiency, culturax, cursor, customer-retention, cybersecurity-capabilities, data-retention-policy, data-scaling, deepseek, delta-attention, dense-attention, diffusion-generation, diffusion-models, diffusion-text-generation, diffusiongemma, distillation, dual-use-ai, encoder-decoder-architecture, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, energy-efficiency, evaluation-methodology, evaluation-transparency, expert-routing, export-controls, extended-thinking, external-context-management, external-memory-management, flash-memory-storage, flow-matching-decoder, fluid-dynamics-simulation, foundation-models, frontend-code-arena, frontend-code-generation, frontend-coding, frontier-code-benchmark, frontier-model-competition, frontier-models, inkling, inkling-small, mixture-of-experts, model-architecture, multimodal-reasoning, open-weights, thinking-machines, thinky]
---

## Inkling Model Family (Thinking Machines Lab, July 2026)

**Architecture**: Mixture-of-Experts transformer
- **Inkling**: 975B total parameters, 41B active per token
- **Inkling-Small**: 276B total parameters, 12B active per token
- **License**: Apache 2.0
- **Context window**: Up to 1M tokens (open weights); 256K via Tinker API (with pricing tiers at 64K and 256K)
- **Modalities**: Native reasoning over text, images, and audio inputs; text output

**Training Data**: 45 trillion tokens across text, images, audio, and video
- Pretraining began winter 2025-2026
- Trained from scratch by TML
- Mid-January 2026: small team added coding, reasoning, and agentic training layers

**Key Design Philosophy**:
- Positioned as a "foundation model" and "customizable base" rather than benchmark-maximized flagship
- Focus on "solid performance across broad categories" for practical use and customization
- Controllable reasoning effort via numerical effort levels
- Emphasized concise reasoning and strong tool calling over raw benchmark performance

**Ecosystem Support** (day-0):
- vLLM, SGLang, Modal, Baseten, Databricks, Hugging Face
- Immediate fine-tuning support on Tinker platform
- Quantization and community tooling

**Market Position** (per independent commentators):
- Tagged as strongest U.S.-based open-weight release as of July 2026
- Still behind top Chinese open-weight models and best closed models on some benchmarks
- Represents TML's "first model" and "first general model" release

See also: [[multimodal-models]], [[inference-efficiency]]