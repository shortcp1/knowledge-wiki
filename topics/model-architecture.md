---
tags: [activation-capping, agentic-coding-tools, agentic-reasoning, agentic-tasks, ai-coding-productivity, ai-safety, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autoregressive-reasoner, benchmark-performance, benchmark-vs-deployment, bert-architecture, character-stability, claude-code, claude-fable-5, claude-mythos, coding-agents, compositional-control, concurrent-processing, context-length, data-retention-policy, deepseek, diffusion-models, encoder-decoder-architecture, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-code-benchmark, frontier-model-competition, frontier-models, gated-attention, gemini, gemma, gemma-4, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-speed, inference-throughput, iterative-composition, iterative-evaluation, latent-moe, layer-outputs, llm-architecture, low-precision-training, mamba-attention-hybrid, mixture-of-experts, mixture-of-transformers, modality-processing, model-architecture, model-architecture-comparison, model-downgrading, model-efficiency, model-safeguards, model-simplification, model-specialization, model-training-pipeline, msa, mtp, multi-head-attention, multimodal-architecture, multimodal-models, mythos-class, mythos-class-models, nemotron, nope, nvfp4, nvidia, open-closed-model-gap, open-weight-models, open-weights, peft, persona-drift, positional-encoding, prompt-modification, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, recursive-self-improvement, relative-position-encoding, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embedding, safety-filters, scaled-dot-product-attention, scene-graphs, self-attention, self-correction, silent-safeguards, sliding-window-attention, sparse-attention, sparse-models, staged-generation, steering-vectors, streaming-asr, swe-bench, text-to-image, text-to-image-generation, transformer-architecture, transparent-fallback, unified-architecture, unified-model-architecture]
---

## Claude Fable 5 / Mythos 5 Architecture (June 2026)

### Model Specifications
- **Model class**: Mythos-class (at least 2x size of [[claude-opus-4.8]])
- **Relationship**: Fable 5 is the same underlying model as Mythos 5 with added safeguards
- **GA timeline**: Released 34 days after SpaceXai deal, 63 days after original Mythos announcement
- **Context window**: 1M tokens (maintained from previous Claude models)
- **Pricing**: ~2x Opus pricing; $10/million input tokens, $50/million output tokens
  - Cache pricing: $12.50/million cache writes, $1/million cache reads

### Benchmark Performance
- **FrontierCode Diamond**: 29.3% (up from 13.4% on Opus 4.8) - out-of-distribution benchmark released same day as model
- **General claim**: State-of-the-art on nearly all tested benchmarks according to Anthropic

### Dual-Track Safeguard Architecture

#### Transparent Fallback Safeguards
- **Trigger domains**: Cybersecurity, biology, chemistry, distillation attempts
- **Mechanism**: Queries routed to [[claude-opus-4.8]] when harmful potential detected
- **User visibility**: Fallback is visible to users through messaging
- **Frequency**: 95%+ of sessions never encounter fallback
- **Implementation**: Available server-side and via SDK middleware (Python, TypeScript, Go, Java, C#)

#### Silent Safeguards (Novel)
- **Trigger domain**: Frontier LLM development (pretraining pipelines, distributed training infrastructure, [[ml-accelerator-design]])
- **Mechanism**: Effectiveness limitations through [[prompt-modification]], [[steering-vectors]], or [[peft]]
- **User visibility**: **No fallback notification**; interventions are invisible to users
- **Distinction**: Fable 5 does not fall back to different model; operates with degraded performance on restricted domains
- **Impact estimate**: ~0.03% of traffic, <0.1% of organizations
- **Design rationale**: Enforces Terms of Service restrictions on developing competing models without relying on user compliance

### Multimodal Capabilities
- **Vision-only gaming**: Demonstrated playing Factorio, Pokemon (using only vision, no complex harness)
- **Audio understanding**: EDM visualization ("never having heard music before")
- **CAD/3D workflows**: 3D CAD editor creation and printing demonstrated

### Engineering Achievement
- Making research-scale Mythos-class models generally available described as "feat of incredible engineering"
- Concurrent release with Claude Tokyo regional deployment