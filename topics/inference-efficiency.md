---
tags: [agentic-ai, agentic-inference, agentic-tasks, ai-budget-constraints, api-pricing-economics, attention-mechanisms, audio-latency, audio-video-alignment, autonomy, aws-inferentia, aws-infrastructure, aws-trainium, batch-size-latency-tradeoff, batch-size-optimization, benchmark-metrics, capital-cost-conversion, cerebras, chinchilla-scaling, claude-opus, cloud-infrastructure, commodity-markets, concurrent-processing, consistency-models, custom-silicon, diffusion-transformers, edge-compute, edge-deployment, encoder-free-early-fusion, encoder-free-fusion, flipbook, flow-matching-decoder, full-duplex-interaction, gans, generative-ui, gpu-alternatives, gpu-cluster-design, gpu-optimization, graviton, grok-imagine, grouped-query-attention, hbm, heterogeneous-compute, hierarchical-mlp, index-as-model, inference-cost, inference-efficiency, inference-era, inference-speedups, inference-throughput, inference-workloads, intelligence-per-dollar, latency-optimization, latency-vs-throughput, llm-architecture, local-inference, local-vs-cloud-tradeoffs, logistics-as-service, low-latency-inference, memory-bandwidth, memory-bandwidth-bound, microturn-processing, mixture-of-experts, model-distillation, model-parallelism, model-pricing, multi-head-attention, multimodal-fusion, nitro, onboard-ai, physical-ai, pipeline-parallelism, prefill-decode, prefill-decode-disaggregation, primitives-strategy, qwen, real-time-inference, realtime-voice, recommendation-systems, reinforcement-learning, retrieval-architecture, retrieval-systems, safety-critical-systems, scm, sglang, sim-to-real, simulation, sparse-attention, statistical-safety, step-distillation, temporal-compression, token-cost-optimization, token-efficiency, tokenmaxxing, tpu-architecture, unified-architecture, vaes, vehicle-operating-systems, video-agents, video-inference, voice-activity-detection, world-models]
---

# Inference Efficiency

Covers techniques for reducing the cost and latency of running AI models in production. Includes quantization (INT4, INT8, FP8), speculative decoding, continuous batching, KV cache optimization, and token efficiency optimization.

## Intelligence Per Dollar Metric

**Dual-Dimension Benchmarking (June 2026)**: The industry is shifting from pure performance benchmarks to measuring both performance and cost efficiency simultaneously.

- **Average Token Usage**: Microsoft's MAI-Code-1-Flash model release card (June 2026) introduced "average token usage" as a standard metric alongside performance scores
  - Example: Microsoft model achieved 71.6 on SWE-Bench Verified using ~33% of tokens compared to Claude Haiku 4.5
  - Signals end of "tokenmaxxing" era where models gamed benchmarks with excessive token usage

- **Intelligence Index Cost Comparison**: Artificial Analysis benchmarks show significant cost variance for equivalent performance:
  - GPT 5.5 and Claude Opus 4.8 both score ~60 on Intelligence Index
  - Running same benchmark costs $3,357 on GPT 5.5 vs $4,685 on Opus 4.8 (40% price premium for equivalent intelligence)

## Enterprise Cost Reality (2026)

**Budget Constraints at Scale**: Even large enterprises face AI token budget exhaustion:
- Uber capped employee AI spending after exhausting budget in 4 months (2026)
- Salesforce spent $300M on Anthropic tokens, leading to engineering hiring freeze (2026)
- Microsoft cancelled Claude Code licenses across Experiences and Devices division after engineering usage outran budgets (2026)

**Implication**: "State-of-the-art intelligence for every conceivable use case" is economically unsustainable even for most valuable companies.

See also: [[ai-pricing-packaging-saas]], [[build-vs-buy-enterprise-ai]], [[token-cost-optimization]]