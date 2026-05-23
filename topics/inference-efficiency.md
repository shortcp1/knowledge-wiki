---
tags: [agentic-ai, agentic-inference, agentic-tasks, api-pricing-economics, attention-mechanisms, audio-latency, autonomy, aws-inferentia, aws-infrastructure, aws-trainium, batch-size-latency-tradeoff, batch-size-optimization, capital-cost-conversion, cerebras, chinchilla-scaling, claude-opus, cloud-infrastructure, commodity-markets, concurrent-processing, custom-silicon, edge-compute, edge-deployment, encoder-free-early-fusion, encoder-free-fusion, flow-matching-decoder, full-duplex-interaction, gpu-alternatives, gpu-cluster-design, graviton, grouped-query-attention, hbm, heterogeneous-compute, hierarchical-mlp, inference-cost, inference-efficiency, inference-era, inference-workloads, latency-optimization, latency-vs-throughput, llm-architecture, local-inference, local-vs-cloud-tradeoffs, logistics-as-service, low-latency-inference, memory-bandwidth, memory-bandwidth-bound, microturn-processing, mixture-of-experts, model-distillation, model-parallelism, multi-head-attention, multimodal-fusion, nitro, onboard-ai, physical-ai, pipeline-parallelism, prefill-decode, prefill-decode-disaggregation, primitives-strategy, qwen, real-time-inference, realtime-voice, reinforcement-learning, safety-critical-systems, sglang, sim-to-real, simulation, sparse-attention, statistical-safety, token-cost-optimization, tokenmaxxing, tpu-architecture, vehicle-operating-systems, voice-activity-detection]
---

# Inference Efficiency

Covers techniques for reducing the cost and latency of running AI models in production. Includes quantization (INT4, INT8, FP8), speculative decoding, continuous batching, KV cache optimization, and hardware-specific kernels (FlashAttention, Triton).

Key questions tracked: What is the current cost-per-token trajectory? Where does hardware vs. software optimization dominate? How does model size affect inference economics?

## Key Claims
<!-- agent-maintained -->

### KV Cache Optimization Techniques (April-May 2026)
- **KV sharing (cross-layer attention)**: Architecture technique where later transformer layers reuse key-value states from earlier layers
  - Reduces long-context memory footprint

### Real-Time Multimodal Latency (Thinking Machines, May 2026)
- **Microturn processing**: TML-Interaction-Small processes conversations in 200ms chunks ("micro-turns") rather than waiting for full turns
  - Interleaves input processing and output generation continuously
  - Eliminates perceived boundary between end of input and start of output
- **Encoder-free early fusion**: Skipping large pretrained encoders (Whisper for audio, ViT for images) and training components end-to-end enables <200ms multimodal processing
  - Direct audio tokenization instead of Whisper preprocessing
  - Hierarchical MLP for 40×40 pixel image patches instead of vision transformer
  - Flow-matching decoder for audio/text output
- **Measured latency**: 0.40s response time on FD-bench V1 conversational turn test
  - vs Gemini-3.1-flash-live-preview minimal reasoning: 0.57s
  - vs GPT-Realtime-2 minimal reasoning: 1.18s
- **Asynchronous background reasoning**: Separates fast interaction model from slower reasoning/tool-use model running in parallel
  - Background model shares context but doesn't block interaction
  - Outputs woven into conversation when appropriate
- **Interactivity vs intelligence tradeoff**: System optimized for low latency leads on interactivity benchmarks but slightly trails on pure reasoning (96.5% vs 96.6% BigBench Audio accuracy)
- See [[multimodal-models]] for full architecture and [[model-architecture]] for encoder-free early fusion details