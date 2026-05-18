# Inference Efficiency

Covers techniques for reducing the cost and latency of running AI models in production. Includes quantization (INT4, INT8, FP8), speculative decoding, continuous batching, KV cache optimization, and hardware-specific kernels (FlashAttention, Triton).

Key questions tracked: What is the current cost-per-token trajectory? Where does hardware vs. software optimization dominate? How does model size affect inference economics?

## Key Claims
<!-- agent-maintained -->

### Real-Time Voice AI Infrastructure (OpenAI, 2026)
- **WebRTC stack rebuild**: OpenAI rebuilt its WebRTC infrastructure to deliver low-latency voice AI at global scale
- **Key capability**: Enables seamless conversational turn-taking in real-time voice interactions
- **Deployment context**: Production-scale serving for real-time voice models
- *Note*: Article focuses on infrastructure/networking layer rather than model optimization; specific latency figures not provided

## Cross-References
- [[gpu-architecture-training-infra]]
- [[model-architecture]]
- [[evals-production-deployment]]
- [[ai-in-product-and-engineering]]