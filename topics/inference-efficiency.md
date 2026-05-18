---
tags: [agentic-tasks, api-pricing-economics, attention-mechanisms, autonomy, batch-size-latency-tradeoff, batch-size-optimization, chinchilla-scaling, claude-opus, edge-compute, edge-deployment, encoder-free-early-fusion, full-duplex-interaction, gpu-cluster-design, grouped-query-attention, inference-cost, inference-efficiency, latency-optimization, llm-architecture, local-inference, local-vs-cloud-tradeoffs, low-latency-inference, mixture-of-experts, model-distillation, model-parallelism, multi-head-attention, multimodal-fusion, onboard-ai, physical-ai, pipeline-parallelism, qwen, realtime-voice, reinforcement-learning, safety-critical-systems, sglang, sim-to-real, simulation, sparse-attention, statistical-safety, token-cost-optimization, tokenmaxxing, tpu-architecture, vehicle-operating-systems, voice-activity-detection]
---

# Inference Efficiency

Covers techniques for reducing the cost and latency of running AI models in production. Includes quantization (INT4, INT8, FP8), speculative decoding, continuous batching, KV cache optimization, and hardware-specific kernels (FlashAttention, Triton).

Key questions tracked: What is the current cost-per-token trajectory? Where does hardware vs. software optimization dominate? How does model size affect inference economics?

## Key Claims
<!-- agent-maintained -->

### KV Cache Optimization Techniques (April-May 2026)
- **KV sharing (cross-layer attention)**: Architecture technique where later transformer layers reuse key-value states from earlier layers
  - Reduces long-context memory footprint and compute requirements
  - Implemented in Gemma 4 E2B and E4B models (April 2026)
  - Based on research: Brandon et al., "Reducing Transformer Key-Value Cache Size with Cross-Layer Attention" (NeurIPS 2024)
- **Compressed attention**: Multiple architectures implementing compressed attention variants for KV cache reduction
  - ZAYA1-8B: Compressed convolutional attention
  - DeepSeek V4: mHC (multi-head compressed) plus compressed attention
  - See [[model-architecture]] for attention mechanism variants
- **Layer-wise attention budgeting**: Poolside

### Local vs. Cloud Inference Economics (May 2026)
- **Localmaxxing Pattern (Tunguz, Theory Ventures, May 2026)**: Individual user experiment running local models for routine work to optimize for latency over quality
  - **Business problem**: Reducing latency for high-frequency, low-complexity agent tasks
  - **Pattern**: Local inference on consumer hardware (MacBook Pro M5 with Qwen 3.6 35B-A3B-4bit quantized model)
  - **User**: VC/knowledge worker
  - **Workload analysis** (1,478 AI tasks over 5 weeks):
    - 50% of tasks suitable for local models
    - Suitable categories: Email & Inbound (11.5%), Scheduling (17.2%), Summarization (12.4%), Admin (0.7%) = 41.8%
    - Split categories: Market Research (13.0%), Engineering (9.9%) - simple tasks work locally, complex require cloud
    - Cloud-required: Other/unstructured (35.3%), complex synthesis, architectural decisions
  - **Performance comparison** (Local Qwen 3.6 35B vs. Cloud Claude Opus 4.5):
    - **Latency**: Local 2x faster for routine agent tasks
    - **Quality gap**: Cloud model ~20% higher on reasoning benchmarks
    - **Output characteristics**: Cloud produces better structure/polish; local produces terser output ("often half the tokens")
    - **Task completion**: Both completed test tasks correctly for routine work
  - **Key insight**: "For agent tasks where output feeds into another system, terseness is a feature"
  - **Trade-off calculus**: For 50% of workload, 2x latency improvement worth quality trade-off
  - **Economic drivers**:
    1. **Latency** (primary): "the only one that really matters"
    2. Privacy (secondary)
    3. Cost (secondary)
    4. Asset depreciation ("MacBook Pro depreciates whether you use it or not. Running local inference extracts compute value from a sinking asset before resale.")
  - **Lag dynamics**: "Local models lag frontier by 3-4 months, and for large-scale complex tasks, that gap matters. But for routine agent tasks, it rarely does."
  - **Trend prediction**: "As local models improve & close the gap with frontier, more users will shift workloads to their own hardware"
  - **Generalizability**: Pattern applies to any high-frequency knowledge work with mix of routine and complex tasks - especially roles with >10 agent interactions/day where latency compounds
  - See [[agentic-workflows-production]] for task categorization patterns