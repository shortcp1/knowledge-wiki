---
tags: [agent-architecture, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, alphafold, anthropic, autonomous-agents, autonomous-fine-tuning, autonomous-research, backend-development, benchmark-contamination, benchmark-vs-deployment, chain-of-thought, claude-code, claude-mythos, claude-opus-4, codex-goals, coding-agents, creative-agents, diffusion-transformers, frontend-development, frontier-model-competition, goal-driven-agents, grok-imagine, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, llm-capability-eval, long-running-tasks, low-precision-training, memory-systems, mixture-of-experts, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, open-weights, orchestration, planning-architectures, post-training, productivity-metrics, prompt-engineering, react, recursive-self-improvement, reflection-mechanisms, reflexion, research-workflows, reward-hacking, rsi, scientific-ai, self-reflection, software-development-acceleration, specialized-tools, strategic-iteration, streaming-asr, swe-bench, task-automation, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store, video-agents, video-generation, world-models, z-ai-glm]
---

# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchm

### Recursive Self-Improvement Evidence (Anthropic, June 2026)

**Operational Metrics**: Anthropic reports unprecedented AI-driven productivity:
- **80%+ of merged code** at Anthropic is now authored by Claude
- **8x code output per engineer** per quarter compared to pre-AI baseline
- **Internal engineering tasks**: Claude success rate increased from ~26% to 76% in six months (open-ended engineering tasks)

**Training Script Optimization Benchmark**: Anthropic's recurring internal test asks models to speed up a small model training script:
- **Claude Opus 4**: ~3x average speedup
- **Claude Mythos Preview**: ~52x speedup (significantly higher than previous models)

**Research Assistance**: In sessions where researchers had taken a wrong turn, Claude Mythos gave better "what to do next" research suggestions than humans **64% of the time**.

**RSI Framing**: Anthropic explicitly stated current systems show "early signs of recursive self-improvement"—not yet full autonomy in research direction, but clear evidence that AI is accelerating AI development. Key limitation: automating problem selection remains unresolved, but automating large portions of implementation and iteration is already operational.

**Governance Position**: Anthropic stated "it would be good for the world to have the option to slow or temporarily pause frontier AI development," framing verification and coordination mechanisms as increasingly urgent if RSI-like dynamics continue.

**Note**: This represents internal, non-public benchmarks and operational data rather than standardized external evaluations. Success metrics are on Anthropic-specific engineering and research tasks.

### NVIDIA Nemotron 3 Ultra for Agents

**Agentic Optimization (June 2026)**: 550B MoE model (55B active) with 1M context, designed explicitly for long-running agent workloads. NVIDIA claims:
- Up to 5x faster for agentic tasks
- 30% lower cost for agentic workloads

Demonstrated Pareto-optimal performance on Terminal-Bench-style evaluations under turn limits (latency vs. task completion).

See also: [[model-architecture]], [[inference-efficiency]]