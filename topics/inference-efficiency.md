---
tags: [agentic-ai, agentic-inference, agentic-task-management, agentic-tasks, ai-budget-constraints, ai-coding-productivity, api-pricing-economics, attention-mechanisms, audio-latency, audio-video-alignment, autonomy, aws-inferentia, aws-infrastructure, aws-trainium, batch-size-latency-tradeoff, batch-size-optimization, benchmark-metrics, blackbox, capital-cost-conversion, cerebras, chinchilla-scaling, claude-opus, cloud-infrastructure, commodity-markets, concurrent-processing, consistency-models, custom-silicon, diffusion-transformers, edge-ai, edge-compute, edge-deployment, encoder-free-early-fusion, encoder-free-fusion, fastconformer, flipbook, flow-matching-decoder, full-duplex-interaction, gans, generative-ui, gpu-alternatives, gpu-cluster-design, gpu-optimization, graviton, grok-imagine, grouped-query-attention, hbm, heterogeneous-compute, hierarchical-mlp, hybrid-routing, index-as-model, inference-cost, inference-efficiency, inference-era, inference-speedups, inference-throughput, inference-workloads, intelligence-per-dollar, latency-optimization, latency-vs-throughput, llm-architecture, local-inference, local-vs-cloud-tradeoffs, logistics-as-service, low-latency-inference, low-precision-training, memory-bandwidth, memory-bandwidth-bound, microturn-processing, minimill-architecture, mixture-of-experts, model-distillation, model-parallelism, model-pricing, multi-head-attention, multimodal-fusion, nemotron, nitro, nvfp4, nvidia, onboard-ai, open-weights, pareto-frontier, physical-ai, pipeline-parallelism, prefill-decode, prefill-decode-disaggregation, primitives-strategy, qwen, real-time-inference, realtime-voice, recommendation-systems, recursive-self-improvement, reinforcement-learning, retrieval-architecture, retrieval-systems, rnn-t, safety-critical-systems, scm, sglang, sim-to-real, simulation, skill-distillation, sparse-attention, statistical-safety, step-distillation, streaming-asr, task-complexity-routing, temporal-compression, token-cost-optimization, token-efficiency, tokenmaxxing, tpu-architecture, unified-architecture, vaes, vehicle-operating-systems, video-age]
---

## Hybrid Routing Architectures

### Local-Cloud Task Routing (Tunguz, June 2026)
- **Classification-based routing**: Agent classifies tasks as easy/hard, routes simple tasks to local model, complex tasks to cloud
- **Observed distribution**: 78% local execution, 22% cloud execution in production agentic workflow (7-day observation period, daily peaks at 88% local)
- **Performance improvements from routing separation**:
  - Throughput: +25% improvement
  - Average task duration: 47s → 19s (60% reduction)
  - Queue age: 73s → 4s (94% reduction)
- **Mechanism**: Small, fast tasks no longer blocked behind large, slow tasks in unified queue
- **Implementation**: Task-based system (via Asana integration) with automated complexity classification

### Minimill Architecture Pattern
- **Analogy to steel minimills**: Distributed, capital-light processing units close to demand, using cloud only for specialized/complex work
- **Deployment model**: Every laptop, phone, edge device with sufficient memory becomes independent processing unit
- **Economic prediction**: "Tens of millions" of edge minimills will proliferate inside companies over next few years, reducing hyperscaler invoice exposure
- **Note**: Prediction is directional; no specific cost comparison data provided

See also: [[agentic-workflows-production]], [[build-vs-buy-enterprise-ai]], [[model-distillation]]