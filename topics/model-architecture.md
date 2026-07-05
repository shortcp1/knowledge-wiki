---
tags: [agentic-tasks, claude-code, coding-agents, creative-generation, cursor-ide, glm-5-2, hallucination-control, hallucination-tolerance, inference-cost, llm-diversity, llm-homogeneity, model-architecture, model-convergence, model-regression, model-specialization, open-ended-generation, open-weight-models, output-predictability, reinforcement-learning, response-diversity, self-hosting, tool-calling, tool-calling-bias, tool-schema, tool-use-training, training-data-convergence, training-methodology, vendor-lock-in]
---

---
tags: [4-bit-quantization, activation-capping, agentic-ai, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-tasks, ai-coding-productivity, ai-lab-government-relations, ai-safety, aliasing-errors, anthropic, apple-foundation-models, apple-silicon, arcee-ai, architecture-invariant-exponents, ascend-npu, assistant-alignment, attention-mechanisms, audio-latency, automated-research, autonomous-coding, autoregressive-reasoner, benchmark-methodology, benchmark-performance, benchmark-vs-deployment, bert-architecture, block-generation, chaotic-systems, character-stability, chinchilla-scaling, claude-code, claude-fable-5, claude-mythos, code-generation-agents, coding-agents, coding-benchmarks, coding-models, common-crawl, composer, compositional-control, compute-allocation, concurrent-processing, context-caching, context-length, context-window, context-window-expansion, cost-efficiency, culturax, cursor, cybersecurity-capabilities, data-retention-policy, data-scaling, deepseek, dense-attention, diffusion-generation, diffusion-models, diffusion-text-generation, diffusiongemma, distillation, encoder-decoder-architecture, encoder-free-architecture, encoder-free-early-fusion, encoder-free-fusion, energy-efficiency, evaluation-transparency, expert-routing, export-controls, external-context-management, external-memory-management, flash-memory-storage, flow-matching-decoder, fluid-dynamics-simulation, frontend-coding, frontier-code-benchmark, frontier-model-competition, frontier-models, gated-attention, gemini, gemma, gemma-4, generalization-error, glm, glm-5.2, google-

## Reinforcement Learning Tool Use Training Effects (July 2026)

**Source**: Armin Ronacher, reported by Simon Willison

### Training-Induced Specialization Bias
**Phenomenon**: Models trained via RL to optimize vendor-specific tool performance show **degraded generalization** to third-party tool schemas.

**Observed Evidence** (Claude Opus 4.8, Sonnet 5):
- Recent Anthropic models trained to excel with Claude Code's search-and-replace edit tools
- Same models exhibit **worse performance** on third-party tool schemas (Pi's edit tools) compared to older model versions
- Failure mode: Invented/hallucinated fields in structured tool calls that violate third-party schemas
- **Performance regression**: Newer, more capable models perform worse on non-native tools

### Vendor Tool Ecosystem Lock-in Through Training
**Pattern Across Vendors**:
- **Anthropic**: RL training optimizes for Claude Code's search-and-replace mechanism
- **OpenAI**: Explicit training for Codex's apply_patch mechanism (publicly discussed)
- **Implication**: Model capabilities increasingly tied to vendor-specific tool implementations

**Generalization Trade-off**:
- Hypothesis: RL optimization for specific tool schemas reduces model's ability to adapt to novel/third-party tool formats
- Models may overfit to training-time tool patterns
- Conflicts with goal of general-purpose tool use capability

### Cross-References
- Related to [[ai-engineering-agents]] cross-harness compatibility issues
- Vendor lock-in implications for [[agentic-workflows-production]] multi-model orchestration