---
tags: [activation-capping, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-tasks, ai-coding-productivity, ai-safety, aliasing-errors, anthropic, arcee-ai, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autoregressive-reasoner, benchmark-performance, benchmark-vs-deployment, bert-architecture, block-generation, chaotic-systems, character-stability, claude-code, claude-fable-5, claude-mythos, coding-agents, coding-benchmarks, coding-models, common-crawl, composer, compositional-control, concurrent-processing, context-caching, context-length, culturax, cursor, data-retention-policy, deepseek, diffusion-generation, diffusion-models, diffusion-text-generation, diffusiongemma, encoder-decoder-architecture, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, export-controls, flow-matching-decoder, fluid-dynamics-simulation, frontend-coding, frontier-code-benchmark, frontier-model-competition, frontier-models, gated-attention, gemini, gemma, gemma-4, glm, glm-5.2, gpu-optimization, grouped-query-attention, hierarchical-mlp, hifloat4, index-as-model, indexshare, inductive-bias, inference-efficiency, inference-optimization, inference-speed, inference-throughput, iterative-composition, iterative-evaluation, kimi, language-specific-bias, latent-moe, layer-outputs, llm-architecture, long-context, long-context-optimization, low-precision-training, ma-activity, mamba-attention-hybrid, meta-superintelligence-labs, mixture-of-experts, mixture-of-transformers, modality-processing, model-architecture, model-architecture-comparison, model-downgrading, model-efficiency, model-fusion, model-safeguards, model-simplification, model-specialization, model-training-pipeline, moonshot, msa, mtp, multi-agent-orchestration, multi-head-attention, multimodal-architecture, multimodal-models, multimodal-reasoning, muse-spark, mythos-class, mythos-class-models, native-multimodal, non-autoregressive-generation, open-source-models, open-weights, physics-simulation, scientific, sparse-attention, speculative-decoding, z-ai]
---

## GLM-5.2 Architecture

**Release Date**: June 2026  
**Developer**: Z.ai  
**License**: MIT (open weights)  
**Parameters**: 744B total, 40B active per token (MoE)  
**Context Window**: 1M tokens

### Core Architecture
- **Base Design**: Built on DeepSeek Sparse Attention with IndexShare extension for improved efficiency at ultra-long contexts
- **Mixture-of-Experts**: 744B parameter MoE with 40B active parameters per token
- **Reasoning Modes**: Two inference modes available - "high" and "max" reasoning effort

### Technical Innovations

**IndexShare for Speculative Decoding**
- Extension to multi-token prediction (MTP) that improves acceptance rates in speculative decoding
- Designed to boost [[inference-efficiency]] at long context lengths
- Works in conjunction with sparse attention mechanisms

**Sparse Attention Improvements**
- Minor but meaningful improvements on DeepSeek Sparse Attention
- Optimized for 1M token context windows
- Contributes to long-horizon agentic task performance

### Performance Characteristics

**Coding Performance** (as of June 2026)
- FrontierSWE: #3 overall (behind Fable 5 and Opus 4.8, ahead of GPT-5.5)
- Frontend coding: #2 overall on Code Arena: Frontend (+29 points over Claude Opus 4.7 Thinking), behind only Fable 5
  - #2 in React specifically
  - #4 in HTML
- Long-horizon coding: 74.4 (ahead of GPT-5.5's 72.6)
- SWE-bench Pro: 62.1 (ahead of GPT-5.5)
- Terminal-Bench 2.1: 81.0 (vs 62.0 for GLM-5.1) - first open-weight model to cross 80%

**Notable**: Achieves top-tier frontend coding performance despite being only 744B parameters vs rumored 1.5T+ for Opus 4.8 and similar sizes for [[cursor]]'s Composer model. Described as first open model competitive with Opus/GPT-class workflows for coding by early testers.

**Design/Agent Performance**
- Design Arena: #1, Elo 1360 (+27 Elo, +4 positions)
- Agent Arena: GLM-5.2 (Max) #10 overall, #1 open model by wide margin
- Agent tasks show steerability tradeoff between high/max modes

**General Performance**
- Text Arena: #25 overall (similar to GLM-5.1)
- AIME 2026: 99.2 (ahead of Opus 4.8 and GPT-5.5)
- Shows gains in Expert Arena, Multi-Turn, and occupational domains (Medicine & Healthcare)

### Infrastructure & Training
- Release includes agentic RL innovations (details light)
- Infrastructure optimizations specifically for 1M context handling
- API pricing maintained at GLM-5.1 levels: $1.4/$4.4 per input/output MTokens

### Ecosystem Support
Day-0 support across: Transformers, vLLM, SGLang, Cloudflare Workers AI, OpenRouter, Ollama Cloud, Baseten, DeepInfra, Fireworks, Notion

See also: [[inference-efficiency]], [[ai-engineering-agents]], [[speculative-decoding]]