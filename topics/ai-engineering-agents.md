---
tags: [agent-architecture, agent-harness, agent-harness-design, agentic-behavior, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, anthropic, antigravity-cli, autonomous-agents, autonomous-debugging, autonomous-fine-tuning, autonomous-research, backend-development, benchmark-contamination, benchmark-vs-deployment, browser-automation, chain-of-thought, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, code-quality-evaluation, codex-cli, codex-goals, coding-agents, cors-debugging, creative-agents, data-retention-privacy, datasette-agent, desktop-agent-harness, desktop-agents, diffusion-transformers, false-positives, frontend-code, frontier-model-competition, frontiercode, function-calling, goal-driven-agents, grok-imagine, html-injection, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, javascript-injection, keyboard-simulation, llm-capability-eval, llm-driven-loops, local-server-debugging, long-running-tasks, low-precision-training, mac-automation, maintainability, memory-systems, mixture-of-experts, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, open-source-agents, open-weights, opencode, opencoworker, orchestration, planning-architectures, post-training, proactive-agents, productivity-metrics, prompt-engineering, pyobjc, react, recursive-self-improvement, reflection-mechanisms, reflexion, research-workflows, reward-hacking, rsi, scientific-ai, scratch-html-testing, screencapture-cli, screenshot-automation, self-reflection, software-development-acceleration, specialized-tools, strategic-iteration, streaming-asr, swe-bench, task-automation, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store, video-agents, video-generation, window-management, world-models, z-ai-glm]
---

# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the

## Agent Harness Architecture

### Definition & Purpose
**Agent Harness:** The software that wraps around an LLM to implement a desired agentic system. It enables the LLM to drive the key loop that decides what to do next at each step.

### Architecture Components
1. **Tool/Function Set:** Collection of callable functions (file access, web search, messaging, etc.)
2. **LLM Integration:** Provides tools to frontier LLM
3. **Permissions & Guardrails:** Security and safety controls
4. **Decision Loop:** Prompts LLM and allows it to pick which tool to use to move forward

### Two Harness Design Philosophies

#### Developer-Specified Workflows (Traditional)
- Higher reliability
- Most practical agentic AI workflows use this approach
- More deterministic behavior
- Less reliance on LLM decision-making

#### LLM-Driven Decision Loops (Emerging)
- LLM decides what to do next at each step
- Historically limited to coding agents (CLI tools)
- Recent frontier LLM advances ("past few months" as of June 2026) have made this viable for broader use cases
- Still "not entirely reliable" but now a viable alternative
- Examples: Claude Code, Codex CLI, Antigravity CLI, OpenCode

### CLI Coding Agents
**Pattern:** Command-line interface agents that use LLM-driven loops  
**Examples:**
- Claude Code
- Codex CLI
- Antigravity CLI
- OpenCode

**Key characteristic:** Main type of agent that uses an LLM to drive the next action (historically)

### Desktop Agent Harness (Non-CLI)
**Evolution:** Extension of CLI agent patterns to desktop environments with easy-to-use interfaces

**Reference Implementation: OpenCoworker**
- Open-source project extending aisuite to support agent harnesses
- Demonstrates harness architecture for desktop agents
- Code available for study of agentic harness patterns

**Use Cases:**
- Messaging automation
- Document creation
- Workflow automation
- Scheduled deliverables (e.g., daily news summaries)
- Local file read/edit operations

### Frontier Model Capability Threshold
**Historical Context:** "In the past few months, frontier LLMs have advanced sufficiently for this style of harness design to provide an important, if still not entirely reliable, alternative."

This suggests a capability threshold was crossed in early 2026 enabling broader LLM-driven agentic loops beyond just coding tasks.