---
tags: [agentic-coding-tools, anthropic, arcee-ai, ascend-npu, attention-mechanisms, audio-latency, automated-research, benchmark-vs-deployment, bert-architecture, claude-code, compositional-control, concurrent-processing, context-length, deepseek, diffusion-models, encoder-decoder-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, frontier-model-competition, gated-attention, gemini, gemma, glm, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, inductive-bias, inference-efficiency, inference-throughput, iterative-composition, llm-architecture, low-precision-training, mixture-of-experts, model-architecture, model-architecture-comparison, model-efficiency, model-specialization, model-training-pipeline, msa, multi-head-attention, multimodal-models, nope, open-closed-model-gap, open-weight-models, positional-encoding, protein-structure-prediction, qk-norm, real-time-inference, reasoning-models, recommendation-systems, relative-position-encoding, retrieval-architecture, retrieval-systems, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, scene-graphs, self-attention, self-correction, sliding-window-attention, sparse-attention, staged-generation, text-to-image, text-to-image-generation, transformer-architecture, unified-architecture, unified-model-architecture, unsupervised-pretraining, weak-to-strong-supervision, world-models]
---

# Model Architecture

Tracks the structural design of large language models and their variants. Covers transformer variants, mixture-of-experts (MoE), state space models (Mamba, SSMs), multi-head vs. grouped-query attention, and emerging architectures. Focuses on what architectural choices affect capability and efficiency.

Key questions tracked: Is MoE the dominant path to scale? Where are SSMs competitive with transformers? What architectural changes are driving the next generation of frontier models?

## Key Claims

### Vanilla Transformer Architecture (2017)
- **Encoder-decoder

## Unified Model Architectures for Retrieval

### SilverTorch "Index as Model" (Meta, May 2026)
- **Paradigm**: Replac

## Staged Generation Architectures (Image Generation)

### Meta Staged Image Composition (May 2026)
- **Paradigm shift**: Challenges the standard diffusion/flow-matching approach of composing whole images at once by breaking generation into discrete stages
- **Base model**: BAGEL-7B, a pretrained multimodal model (takes images + text, produces images + text)
- **Four-stage iterative loop**:
  1. **Plan**: Generate instruction for next compositional change + description of expected result
  2. **Sketch**: Generate updated image via [[flow-matching-decoder]] steps
  3. **Inspect**: Verify consistency between instruction, description, and original prompt
  4. **Refine**: Issue corrective commands and regenerate if inconsistencies detected
- **Key advantage**: Better control over spatial relationships (above/below/in-front/behind) and object attributes (counts of body parts) compared to single-pass generation
- **Training approach**: Three separate fine-tuning stages
  - Plan/Sketch: 32,000 examples with 3-5 intermediate images per prompt, using GPT-4o to create scene graphs and FLUX.1 Kontext for image generation
  - Inspect: ~15,300 examples (7,000 consistent, 8,300 inconsistent) using GPT-4o critiques
  - Refine: Dataset of images with reflections on improvements and improved versions
- **Technical note**: Model learns both (i) next-token generation for text and (ii) image generation via pixel value adjustments over flow-matching steps
- **Architectural implication**: Suggests value of explicit planning and error-checking loops in generative architectures, similar to reasoning models like [[reasoning-models]] but for visual composition

See also: [[inference-efficiency]] for iterative generation costs