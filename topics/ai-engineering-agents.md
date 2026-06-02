---
tags: [agent-architecture, agentic-coding-tools, agentic-science, agentic-systems, agentic-workflows, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, alphafold, autonomous-agents, autonomous-fine-tuning, autonomous-research, benchmark-contamination, benchmark-vs-deployment, chain-of-thought, claude-code, codex-goals, creative-agents, diffusion-transformers, frontier-model-competition, goal-driven-agents, grok-imagine, iteration-speed, iterative-composition, llm-capability-eval, memory-systems, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, orchestration, planning-architectures, post-training, prompt-engineering, react, recursive-self-improvement, reflection-mechanisms, reflexion, reward-hacking, scientific-ai, self-reflection, specialized-tools, task-automation, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store, video-agents, video-generation, world-models]
---

# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchmark. This represents a ~47x improvement in solving real-world software engineering problems over ~2.5 years.
- **METR Time Horizons**: AI systems show rapid progress in completing increasingly complex tasks measured by human-equivalent time horizons. GPT-3.5 (2022) could handle tasks taking a person a few minutes; frontier models by 2026 can reliably complete multi-hour tasks (specific 50% reliability threshold not provided in excerpt, but trend indicates continuous expansion).

### Agent Evolution Pattern: From Output to Orchestration

#### Coding Model Evolution
- **Historical pattern**: Coding models evolved from focusing on "one-shot output performance and cost" to "multiturn reasoning and planning models"
- **Saturation point**: "At a certain point, coding models got so good that the only significant next step to improve performance was handling the orchestration of these models"
- **Agent capabilities**: Modern coding agents "can plan, edit, test, debug, and submit PRs"
- **Bottleneck shift**: Once base model capability reaches threshold, orchestration becomes primary constraint

#### Video Agent Emergence (2026)
- **Prediction (Ethan He, xAI)**: "In the near term, the next Sora won't be a better video model, but a video agent"
- **Parallel evolution**: Video generation following same trajectory as coding—from optimizing single outputs to building systems that orchestrate multiple generations
- **Grok Imagine Agent Mode (Apr 2026)**: First production video agent system with "plan → generate → edit → iterate" loop on infinite canvas
- **Creative agent capabilities**: Plan, generate, edit, critique, and iterate across entire creative tasks
- **Architectural insight**: Video agents may depend more on [[multimodal-models]] language models and agent architectures than on pure diffusion improvements

### Orchestration as Core Capability
- **Pattern recognition**: Across domains (coding, creative work), once base model quality reaches sufficiency, orchestration layer becomes the competitive frontier
- **System design**: Agents combining planning, execution, critique, and iteration rather than single-pass generation
- **Multi-turn reasoning**: Essential for complex tasks requiring revision and refinement