---
tags: [agent-architecture, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-workflows, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, alphafold, autonomous-agents, autonomous-fine-tuning, autonomous-research, backend-development, benchmark-contamination, benchmark-vs-deployment, chain-of-thought, claude-code, codex-goals, coding-agents, creative-agents, diffusion-transformers, frontend-development, frontier-model-competition, goal-driven-agents, grok-imagine, infrastructure-engineering, iteration-speed, iterative-composition, iterative-evaluation, llm-capability-eval, long-running-tasks, memory-systems, mixture-of-experts, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, open-weights, orchestration, planning-architectures, post-training, prompt-engineering, react, recursive-self-improvement, reflection-mechanisms, reflexion, research-workflows, reward-hacking, scientific-ai, self-reflection, software-development-acceleration, specialized-tools, strategic-iteration, swe-bench, task-automation, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store, video-agents, video-generation, world-models, z-ai-glm]
---

# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchmark. This represents a ~47x improvement in solving real-world software engineering problems over ~2.5 years.
- **METR Time Horizons**: AI systems show rapid progress in completing tasks over extended time horizons.

### Long-Running Agentic Tasks (Apr 2026)
**Source**: The Batch Issue 350, Apr 24, 2026

**Model**: GLM-5.1 by Z.ai (open-weights)

**Business Problem**: Enabling AI agents to work autonomously on single complex tasks for extended periods without giving up early when initial approaches fail.

**AI Pattern**: Agentic workflow with strategic iteration and self-evaluation:
- **Try-evaluate-revise loop**: Agent attempts an approach, evaluates the result, and revises strategy if inadequate
- **Extended persistence**: Can repeat iteration loop hundreds of times rather than giving up after early failures
- **Task duration**: Designed to work autonomously on single tasks for up to 8 hours
- **Context window**: 200,000 token input, 128,000 token output

**Application Areas**: 
- Coding tasks
- General agentic tasks requiring sustained problem-solving

**Success Factors**:
- **Strategic iteration capability**: Ability to evaluate own results and change approach
- **Extended time horizon**: 8-hour autonomous operation window (vs. typical shorter agent sessions)
- **Large context**: 200K input tokens allows maintaining full task context across iterations
- **Persistence**: Hundreds of iteration loops possible before giving up

**Model Type**: Open-weights (community can inspect, modify, and deploy)

**Generalizability**: 
- Long-running autonomous agents applicable to any complex problem-solving domain requiring multiple attempts and strategy adjustments
- Particularly valuable for: research tasks, complex debugging, system design, multi-step analysis
- Cross-industry applications: software development, data analysis, research, content creation, business process automation
- The try-evaluate-revise pattern mirrors human expert problem-solving approaches

**Industry Significance**: Represents shift from single-shot or short-session agents to persistent, self-correcting autonomous systems capable of working through complex problems over multiple hours.

---

[Previous content continues...]