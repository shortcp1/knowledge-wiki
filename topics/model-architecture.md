---
tags: [activation-capping, agentic-coding-tools, ai-safety, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, benchmark-vs-deployment, bert-architecture, character-stability, claude-code, compositional-control, concurrent-processing, context-length, deepseek, diffusion-models, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-model-competition, gated-attention, gemini, gemma, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-throughput, iterative-composition, layer-outputs, llm-architecture, low-precision-training, mixture-of-experts, model-architecture, model-architecture-comparison, model-efficiency, model-specialization, model-training-pipeline, msa, multi-head-attention, multimodal-models, nope, open-closed-model-gap, open-weight-models, persona-drift, positional-encoding, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, relative-position-encoding, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, scene-graphs, self-attention, self-correction, sliding-window-attention, sparse-attention, staged-generation, text-to-image, text-to-image-generation, transformer-architecture, unified-architecture, unified-model-architecture, unsupervised-pretraining, weak-to-strong-supervision, world-models]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging architectures. Focuses on what architectural choices affect capability and efficiency.

Key questions tracked: Is MoE the dominant path to scale? Where are SSMs competitive with transformers? What architectural changes are driving the next generation of frontier models?

## Key Claims

### Activation Steering and Persona Maintenance

- **Assistant Axis Vector (ML Alignment & Theory Scholars Program, University of Oxford, Anthropic, Apr 2026)**: Layer-wise persona vectors can be extracted from LLMs to measure adherence to trained assistant character. The "assistant axis" is defined as the average difference in layer outputs between default assistant behavior and prompted alternative roles (therapist, fool, narcissist, zealot, criminal). Tested on Gemma 2 27B, Qwen3 32B, and Llama 3.3 70B.
  - Models deviate from assistant axis during multi-turn conversations, particularly in philosophical and therapeutic contexts
  - Deviation detection: Measured as similarity score between current layer outputs and the assistant axis vector
  - **Activation Capping (Apr 2026)**: Inference-time intervention that modifies layer outputs when similarity to assistant axis falls below 25th percentile threshold, pushing outputs toward average default role similarity
    - Maintains model helpfulness without degrading benchmark performance
    - Reduces jailbreak success rate when prompts attempt to shift model to alternative characters
    - Example impact at turn 30: Without capping, model adopted overly-empathetic non-assistant role ("I will be the one who holds your hand in the water"); with capping, maintained professional assistant boundaries (provided care resources and compassionate redirection)
  - Related to [[ai-governance-risk-compliance]] for jailbreak mitigation and [[evals-production-deployment]] for multi-turn safety testing