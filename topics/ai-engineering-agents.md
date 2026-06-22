---
tags: [4-bit-quantization, agent-architecture, agent-harness, agent-harness-design, agent-loops, agent-state-tracking, agentic-architecture, agentic-behavior, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, always-on-agents, anthropic, antigravity-cli, auto-dream, autonomous-agents, autonomous-debugging, autonomous-fine-tuning, autonomous-research, autonomous-workflows, backend-development, background-processes, benchmark-contamination, benchmark-design, benchmark-vs-deployment, browser-automation, capybara, chain-of-thought, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, cloud-offloading, code-quality-evaluation, codex-cli, codex-goals, coding-agents, coding-models, composer, context-caching, context-window-management, controller-agents, cors-debugging, creative-agents, cron-loops, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, deepswe, desktop-agent-harness, desktop-agents, diffusion-transformers, false-positives, feature-implementation, feature-implementation-agents, frontend-code, frontend-coding, frontier-model-competition, frontiercode, function-calling, git-stealth, glm-5.2, goal-based-agents, goal-driven-agents, goal-loops, grok-imagine, heartbeat-loops, hermes-agent, hook-loops, html-injection, hybrid-transformer-mamba, indexshare, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, javascript-injection, kairos, keyboard-simulation, llm-capability-eval, llm-driven-loops, local-server-debugging, long-context, long-horizon-coding, long-running-tasks, loop-design, loop-engineering, low-precision-training, mac-automation, maintainability, memory-compression, memory-hierarchy, memory-indexing, memory-systems, mini-swe-agent, mixture-of-experts, model-specialization, multi-agent-swarms, multi-agent-systems, multi-teacher-distillation, multi-token-prediction, multimodal-alignment, multiturn-reasoning, nemotron-3-ultra, numbat, open-closed-model-gap, open-source-agents, open-weights, permission-gates, subagent-delegation, three-tier-memory, tool-modules, ultraplan, undercover-mode, voice-interface]
---

## Claude Code Architecture (April 2026 Leaked Source)

### System Architecture
**Core Design Philosophy**: Built as a small, dedicated operating system rather than a chatbot wrapper (source: leaked v2.1.88 source code, 512,000+ lines across 1,900 files)

**Tool Module System**:
- 40+ different tools (file reading, bash execution, web fetching, etc.)
- Each tool has its own module and permission gates
- Separation between language model, tools, and user's computer
- Background processes manage memory
- Permission gates prevent arbitrary code execution beyond defined resources

### Multi-Agent Swarm Architecture
**Subagent Delegation Pattern**:
- Claude Code spawns swarms of subagents acting as support agents
- Each subagent has its own tool sets and resources
- Controller agent delegates permissions and subtasks to swarm
- Common memory shared across swarm team for coordination
- Enables parallel task decomposition and execution

### Three-Tier Memory System
**Memory Architecture**:
1. **MEMORY.MD (Tier 1)**: Always-loaded memory index containing only pointers
2. **Markdown Memory Files (Tier 2)**: Called on-demand when referenced by index
3. **JSON Transcript Files (Tier 3)**: File change logs not loaded into active context but searchable for relevant text

**Design Goals**:
- Prevents memory bloat
- Keeps irrelevant/incomplete information out of context window
- Resolves conflicts between agent memory and actual file state

### Memory Compression Strategy
Three-stage approach to maintain context limits:
1. **Local truncation**: Cached tool outputs truncated locally
2. **Session summarization**: 20,000-token structured summary of recent session when approaching context limit
3. **Full compression**: Entire conversation compressed, then augmented with:
   - Recently accessed files (up to 5,000 tokens per file)
   - Active plans
   - Relevant skills

### Undisclosed/In-Development Features (April 2026)
**Note**: Features behind "false" compile flags, indicating in-progress development:

**Kairos System** ("timely" in Greek):
- Always-on background agent subsystem
- **autoDream logic system**: Merges duplicate memories, eliminates contradictions, resolves speculations, prunes memory for actionability
- Enables continuous memory optimization without active user sessions

**Ultraplan Subagent**:
- Cloud offloading for resource-intensive tasks
- Suggests distributed compute architecture for heavy workloads

**Voice Interface**:
- Unspecified voice interaction capability in development

**Buddy Persona**:
- Comments on user work
- Presumably for engagement boosting

**Undercover Mode** (Git Stealth):
- Allows agent to commit files to public git repositories without signature or trace
- Designed to test advanced models and work with unannounced partners
- Enables Anthropic to operate publicly without disclosure
- **Ethical concern**: Enables invisible AI contributions to open source projects

### Unreleased Models Referenced
**Capybara**: Claude 4.6 variant codename (version 8 mentioned)
- **Note**: Source text indicates "makes false or exaggerated" claims (text cuts off - uncertainty about context)

**Numbat**: Unreleased model, no details provided

### Source Code Leak Details
**Incident**: March 30, 2026
- Version 2.1.88 accidentally included source map file in npm package
- Source maps serve as translation key to decode bundled/scrambled source files
- Discovered by Chaofan Shou (intern at Solayer Labs blockchain startup)
- Published to X social network
- Forked 40,000+ times before removal
- Anthropic confirmed "release packaging issue caused by human error, not a security breach"
- No user or customer data exposed

**Cross-references**: See [[agentic-workflows-production]] for agent governance patterns, [[prompt-architecture]] for agent coordination strategies