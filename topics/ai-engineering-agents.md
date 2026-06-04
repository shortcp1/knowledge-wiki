---
tags: [agent-architecture, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-workflows, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, alphafold, autonomous-agents, autonomous-fine-tuning, autonomous-research, benchmark-contamination, benchmark-vs-deployment, chain-of-thought, claude-code, codex-goals, coding-agents, creative-agents, diffusion-transformers, frontier-model-competition, goal-driven-agents, grok-imagine, iteration-speed, iterative-composition, iterative-evaluation, llm-capability-eval, memory-systems, mixture-of-experts, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, open-weights, orchestration, planning-architectures, post-training, prompt-engineering, react, recursive-self-improvement, reflection-mechanisms, reflexion, reward-hacking, scientific-ai, self-reflection, specialized-tools, swe-bench, task-automation, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store, video-agents, video-generation, world-models]
---

# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchmark. This represents a ~47x improvement in solving real-world software engineering problems over ~2.5 years.
- **METR Time Horizons**: AI systems show rapid progress in completing increasingly complex tasks measured by human-equivalent time horizons. GPT-3.5 (2022) could handle

### Long-Running Agentic Tasks (GLM-5.1, April 2026)

**Extended autonomy**: Z.ai's GLM-5.1 is designed to work autonomously on single tasks for up to 8 hours, representing a significant extension of task horizon compared to prior models.

**Iterative approach**: Unlike models that produce final output within a fixed token budget, GLM-5.1 cycles through:
1. Planning
2. Execution
3. Evaluation of intermediate results
4. Evaluation of its approach
5. Strategy revision if current approach is inadequate

This loop may repeat hundreds of times, sometimes using thousands of tool calls across multiple hours in Z.ai's tests.

**Self-correction mechanism**: Model can detect when current approach is inadequate and shift strategies mid-task, rather than giving up early or continuing with ineffective methods.

**Performance on agentic coding**:
- SWE-Bench Pro (Z.ai tests, April 2026): 58.4% (GLM-5.1) vs 57.7% (GPT-5.4), 57.3% (Claude Opus 4.6), 54.2% (Gemini 3.1 Pro)
- Arena Code leaderboard: 1,530 Elo (3rd place, behind Claude Opus 4.6 variants)
- CyberGym: 68.7 (highest among models tested by Z.ai, prior to Claude Mythos at 83.1)
- KernelBench Level 3 (GPU acceleration): 3.6x speedup (behind Claude Opus 4.6 at 4.2x)

**Reasoning limitations**: Despite strong coding performance, GLM-5.1 trailed proprietary models on reasoning/math:
- GPQA Diamond: 86.2% (vs Gemini 3.1 Pro 94.3%)
- AIME 2026: 95.3% (vs GPT-5.4 98.7%)

**Open-weights leadership**: Highest-scoring open-weights model on Artificial Analysis Intelligence Index (51), though behind closed models (Gemini 3.1 Pro Preview and GPT-5.4 at 57, Claude Opus 4.6 at 53).

**Economics**: API pricing $1.40/$0.26/$4.40 per million input/cached/output tokens (~40% higher than GLM-5 predecessor). Coding subscriptions $48.60-$432/quarter (roughly double predecessor). Still less expensive than comparable proprietary models but gap narrowing.

See also: [[inference-time-compute]] for theoretical foundations of extended reasoning, [[model-architecture]] for GLM-5.1 technical specs.