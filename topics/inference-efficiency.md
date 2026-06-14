---
tags: [agent-architecture, agent-ecosystems, agent-kv-cache-demands, agent-memory-requirements, agent-paradigm, agentic-ai, agentic-computing, agentic-inference, agentic-task-management, agentic-tasks, ai-budget-constraints, ai-coding-productivity, api-pricing-economics, app-intents, attention-mechanisms, audio-latency, audio-video-alignment, autonomy, aws-inferentia, aws-infrastructure, aws-trainium, batch-size-latency-tradeoff, batch-size-optimization, benchmark-metrics, blackbox, capital-cost-conversion, cerebras, chinchilla-scaling, claude-opus, cloud-infrastructure, commodity-markets, concurrent-processing, consistency-models, consumer-ai, contextual-ai, custom-silicon, device-ecosystem, device-interaction-paradigms, device-paradigm, diffusion-transformers, edge-ai, edge-compute, edge-deployment, encoder-free-early-fusion, encoder-free-fusion, fastconformer, flipbook, flow-matching-decoder, full-duplex-interaction, gans, generative-ui, graviton, grok-imagine, grouped-query-attention, hbm, heterogeneous-compute, hierarchical-mlp, hybrid-routing, index-as-model, inference-cost, inference-efficiency, inference-era, inference-speedups, inference-throughput, inference-workloads, intelligence-per-dollar, interaction-paradigm, kv-cache-memory-demands, latency-optimization, latency-vs-throughput, llm-architecture, local-inference, local-vs-cloud-tradeoffs, logistics-as-service, low-latency-inference, low-precision-training, memory-bandwidth, memory-bandwidth-bound, microturn-processing, minimill-architecture, mixture-of-experts, model-distillation, model-parallelism, model-pricing, multi-head-attention, multimodal-fusion, nemotron, nitro, nvfp4, nvidia, on-device-inference, onboard-ai, open-weights, pareto-frontier, physical-ai, pipeline-parallelism, portal-devices, prefill-decode, prefill-decode-disaggregation, primitives-strategy, project-solara, qwen, real-time-inference, realtime-voice, recommendation-systems, recursive-self-improvement, reinforcement-learning, retrieval-architecture, retrieval-sys, server-side-inference, thin-client-architecture]
---

# Inference Efficiency

## Server-Side Dominance for Agentic Workloads (Thompson, February 2026)

### Memory Demands Drive Centralization
**Technical Driver**: Increasingly high memory demands for agents, particularly KV cache requirements, favor server-side inference over edge deployment.

**Agentic Rationale**: Agent workloads require extended context and state management that exceeds practical on-device memory constraints. See [[agentic-workflows-production]] for enterprise deployment patterns.

### Thin Client Economics
**Core Thesis**: For agent-based computing, local compute becomes unnecessary:
- Traditional chatbot: No local compute needed for inference
- Agent workflows: No local compute needed for task execution—AI on server does it all
- User device only needs minimal compute for brief interaction moments

**Architectural Implication**: The separation of interaction (device-side) from computation (server-side) enables portal device paradigms. See [[ai-native-product-design]] for interaction design implications.