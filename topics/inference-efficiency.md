---
tags: [agentic-ai, agentic-inference, agentic-tasks, api-pricing-economics, attention-mechanisms, audio-latency, autonomy, aws-inferentia, aws-infrastructure, aws-trainium, batch-size-latency-tradeoff, batch-size-optimization, capital-cost-conversion, cerebras, chinchilla-scaling, claude-opus, cloud-infrastructure, commodity-markets, concurrent-processing, custom-silicon, edge-compute, edge-deployment, encoder-free-early-fusion, encoder-free-fusion, flow-matching-decoder, full-duplex-interaction, gpu-alternatives, gpu-cluster-design, gpu-optimization, graviton, grouped-query-attention, hbm, heterogeneous-compute, hierarchical-mlp, index-as-model, inference-cost, inference-efficiency, inference-era, inference-throughput, inference-workloads, latency-optimization, latency-vs-throughput, llm-architecture, local-inference, local-vs-cloud-tradeoffs, logistics-as-service, low-latency-inference, memory-bandwidth, memory-bandwidth-bound, microturn-processing, mixture-of-experts, model-distillation, model-parallelism, multi-head-attention, multimodal-fusion, nitro, onboard-ai, physical-ai, pipeline-parallelism, prefill-decode, prefill-decode-disaggregation, primitives-strategy, qwen, real-time-inference, realtime-voice, recommendation-systems, reinforcement-learning, retrieval-architecture, retrieval-systems, safety-critical-systems, sglang, sim-to-real, simulation, sparse-attention, statistical-safety, token-cost-optimization, tokenmaxxing, tpu-architecture, unified-architecture, vehicle-operating-systems, voice-activity-detection]
---

# Inference Efficiency

Covers techniques for reducing the cost and latency of running AI models in production. Includes quantization (INT4, INT8, FP8), speculative decoding, continuous batching, KV cache optimization, and hardware-specific kernels (FlashAttention, Triton).

Key questions tracked: What is the current cost-per-token trajectory? Where does hardware vs. software optimization dominate?

## Retrieval System Efficiency

### SilverTorch "Index as Model" Paradigm (Meta, May 2026)
- **Unified Model-Based Retrieval**: Meta replaced microservice-based recommendation retrieval with a single neural network architecture called SilverTorch
- **Performance claims**:
  - 23.7× higher throughput (requests per second) vs. traditional multi-service baseline on same model architecture
  - 20.9× better total cost of ownership (TCO) efficiency vs. CPU-based solution
  - Maintains sub-100ms latency requirement for retrieving from millions of items down to thousands
  - Tested at 80M-item scale
- **Architecture approach**: Expresses microservices as model modules within integrated neural network; item indices become tensors inside model
- **Integration benefit**: Single request flow handles search, filtering, reranking, and multi-task scoring without network round-trips between services
- **Deployment**: Production at scale across Meta family of apps for feed and video content retrieval
- **Reference**: "SilverTorch: A Unified Model-based System to Democratize Large-Scale Recommendation on GPUs" (SIGIR 2026)

### Microservice vs. Unified Architecture Trade-offs
- **Traditional microservice bottlenecks** (per Meta analysis):
  - Network round-trip time and serialization overhead between services
  - Version inconsistency when user-tower model, item index, and filtering rules update independently
  - No joint optimization possible across filtering, search, and scoring
  - Siloed development (PyTorch ML vs. C++ infrastructure)
- **Unified model advantages**: Eliminates inter-service data movement costs; enables joint optimization; single version consistency
- **Note**: This represents a shift from CPU-era microservice design to GPU-native unified inference for retrieval workloads

See also: [[model-architecture]] for neural network design choices