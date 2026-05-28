---
tags: [agent-architecture, agentic-coding-tools, agentic-science, agentic-systems, agentic-workflows, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, alphafold, autonomous-agents, autonomous-fine-tuning, autonomous-research, benchmark-contamination, benchmark-vs-deployment, chain-of-thought, claude-code, codex-goals, frontier-model-competition, goal-driven-agents, llm-capability-eval, memory-systems, model-specialization, open-closed-model-gap, planning-architectures, post-training, prompt-engineering, react, recursive-self-improvement, reflection-mechanisms, reflexion, reward-hacking, scientific-ai, self-reflection, specialized-tools, task-automation, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store]
---

# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchmark. This represents a ~47x improvement in solving real-world software engineering problems over ~2.5 years.
- **METR Time Horizons**: AI systems show rapid progress in completing increasingly complex tasks measured by human-equivalent time horizons. GPT-3.5 (2022) could handle tasks taking a person a few minutes; frontier models by 2026 can reliably complete multi-hour tasks (specific 50% reliability threshold not provided in excerpt, but trend indicates continuous expansion of task complexity).
- **Industry Adoption Pattern (2026)**: "Vast majority" of people at frontier labs and

### Goal-Driven Agent Patterns

#### Codex /goal Feature (May 2026)
- **Autonomy shift**: /goal command transforms AI from "turn-based assistant" requiring constant prompting into autonomous agent capable of multi-hour execution without human intervention
- **Production evidence**: Real-world use cases demonstrate 4-5+ hour autonomous runs:
  - Code maintenance: Eliminated hundreds of Sentry errors over 5h45m autonomous execution
  - Email processing: Cleaned 3,900 emails down to 68 in under 4 hours
  - Project management: Organized hundreds of Linear tasks autonomously
- **Key architectural difference**: Goals implement persistent loops with verification/retry logic, vs. standard prompts that require turn-by-turn guidance
- **Cross-domain applicability**: Works for both technical (codebase maintenance, API error resolution) and non-technical tasks (email triage, project organization)

#### Effective Goal Design Framework (6 components)
OpenAI documentation and practitioner experience (Vo, 2026) identify critical elements:
1. **Measurable outcomes** (not outputs): Goals should specify desired end state, not process steps
2. **Verification methods**: How the agent confirms task completion or progress
3. **Constraints**: Boundaries and limitations to prevent scope creep or unsafe actions
4. **[Components 4-6 not specified in source but referenced as part of framework]**

#### Goal Lifecycle Management
- **Operations supported**: View active goals, pause execution, resume from checkpoint, clear/cancel goals
- **Implications**: Suggests goals maintain persistent state and support interruption/resumption patterns

#### When NOT to Use Goals (May 2026)
- Specific anti-patterns mentioned but not detailed in source
- Suggests task characteristics that make goal-based autonomy inappropriate vs. interactive prompting
- Related to [[agentic-workflows-production]] considerations for safe deployment

**Related patterns**: See [[prompt-architecture]] for differences between goal-based and turn-based prompting strategies; [[agentic-workflows-production]] for production deployment considerations