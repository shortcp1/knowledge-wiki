---
tags: [activation-capping, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-tasks, ai-coding-productivity, ai-safety, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autoregressive-reasoner, benchmark-performance, benchmark-vs-deployment, bert-architecture, character-stability, claude-code, claude-fable-5, claude-mythos, coding-agents, common-crawl, composer, compositional-control, concurrent-processing, context-caching, context-length, culturax, cursor, data-retention-policy, deepseek, diffusion-models, encoder-decoder-architecture, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-code-benchmark, frontier-model-competition, frontier-models, gated-attention, gemini, gemma, gemma-4, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-speed, inference-throughput, iterative-composition, iterative-evaluation, kimi, language-specific-bias, latent-moe, layer-outputs, llm-architecture, low-precision-training, mamba-attention-hybrid, mixture-of-experts, mixture-of-transformers, modality-processing, model-architecture, model-architecture-comparison, model-downgrading, model-efficiency, model-safeguards, model-simplification, model-specialization, model-training-pipeline, moonshot, msa, mtp, multi-head-attention, multimodal-architecture, multimodal-models, mythos-class, mythos-class-models, nemotron, nope, nvfp4, nvidia, open-closed-model-gap, open-weight-models, open-weights, open-weights-fine-tuning, peft, persona-drift, positional-encoding, prompt-modification, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, recursive-self-improvement, reinforcement-learning-from-feedback, reinforcement-learning-from-harness, relative-position-encoding, responsible-ai, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embeddin, specialized-model-training, state-media-bias, synthetic-data-generation, synthetic-task-generation, text-feedback-rl, tool-aligned-training, tool-calling, training-data-composition]
---

=== model-architecture ===

== Agent-Specialized Model Training ==

=== Cursor Composer 2.5 Training Approach ===
**Base model**: [[moonshot]] Kimi K2.5 (open weights)
**Architecture**: Mixture-of-experts transformer, 1.04 trillion parameters, 32 billion active per token

**Training pipeline for agent specialization**:
1. **Continued pretraining**: Large code dataset applied to base model weights
2. **Reinforcement learning with matched harness**: 
   - Simulated agentic harness matching deployment environment ([[cursor-cli]])
   - Rewards for: task success, output brevity, output elegance
   - **Text feedback mechanism**: Corrective text loaded into context window during RL (e.g., suggesting better tool calls), using correct output as teaching signal
   - **Synthetic task scaling**: 25x more synthetic tasks than previous version, emphasizing harder scenarios

**Key principle**: **Co-design of model and harness** - training environment matches deployment tools, reducing distribution shift between training and inference.

This represents a specialized approach where the model is explicitly trained for the specific agent harness it will operate within, rather than general-purpose capabilities. See [[ai-engineering-agents]] for performance characteristics.

**Undisclosed**: Source model for synthetic task generation, specific composition of additional pretraining data.