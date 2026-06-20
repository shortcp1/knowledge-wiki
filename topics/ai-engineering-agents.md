---
tags: [agent-architecture, agent-harness, agent-harness-design, agent-loops, agent-state-tracking, agentic-behavior, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, anthropic, antigravity-cli, autonomous-agents, autonomous-debugging, autonomous-fine-tuning, autonomous-research, autonomous-workflows, backend-development, benchmark-contamination, benchmark-design, benchmark-vs-deployment, browser-automation, chain-of-thought, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, code-quality-evaluation, codex-cli, codex-goals, coding-agents, coding-models, composer, context-caching, cors-debugging, creative-agents, cron-loops, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, deepswe, desktop-agent-harness, desktop-agents, diffusion-transformers, false-positives, feature-implementation, feature-implementation-agents, frontend-code, frontend-coding, frontier-model-competition, frontiercode, function-calling, glm-5.2, goal-based-agents, goal-driven-agents, goal-loops, grok-imagine, heartbeat-loops, hook-loops, html-injection, indexshare, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, javascript-injection, keyboard-simulation, llm-capability-eval, llm-driven-loops, local-server-debugging, long-context, long-horizon-coding, long-running-tasks, loop-design, loop-engineering, low-precision-training, mac-automation, maintainability, memory-systems, mini-swe-agent, mixture-of-experts, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, open-source-agents, open-weights, open-weights-fine-tuning, opencode, opencoworker, orchestration, planning-architectures, post-training, pr-automation, pr-review-automation, proactive-agents, productivity-metrics, program-synthesis, program-synthesis-agents, prompt-engineering, pyobjc, react, recursi, stirrup-harness, swe-agent, swe-bench, system-diagnosis-agents]
---

## Agent Harnesses for Software Engineering

### mini-swe-agent

A lightweight agentic harness used in multiple [[evals-production-deployment]] contexts:

**Use Cases**:
- DeepSWE benchmark: Solves feature implementation tasks from brief prompts, requiring agents to devise solutions from many acceptable possibilities
- ProgramBench: Can be used (alternatively with swe-agent) to replicate programs from executable analysis

**Capabilities**:
- Works with various LLM backends (GPT-5.5, Claude models, Gemini models)
- Handles multi-language code generation (5+ languages in DeepSWE)
- Processes brief specifications into complete implementations
- Access to console for program execution and analysis

**Performance Context**: With GPT-5.5 (xhigh reasoning), achieved 70% success on DeepSWE's 113 problems (June 2026)

### SWE-agent

Established agentic harness for software engineering tasks:

**Use Cases**:
- ProgramBench program replication
- Original SWE-bench evaluations
- Used to build ProgramBench itself (with Claude Sonnet 4.5) through:
  1. Repository identification
  2. Executable program building
  3. Test generation from input/output analysis
  4. Testing environment construction

**Note**: Can be used interchangeably with mini-swe-agent for certain tasks, suggesting compatible interfaces

### Stirrup

**Developer**: Artificial Analysis

**Focus**: System diagnosis and incident response

**Use Cases**:
- ITBench-AA evaluation
- Root cause analysis from system alerts, events, error traces, and metrics
- Multi-application manifest analysis

**Characteristics**:
- Designed for infrastructure-level problem diagnosis
- Processes complex system state including:
  - Multiple simultaneous alerts
  - Event timelines
  - Performance metrics
  - Configuration manifests

## Agent Capabilities Evolution

Recent [[evals-production-deployment]] data (June 2026) reveals significant capability gaps:

**Feature Implementation** (DeepSWE):
- Best: GPT-5.5 at 70%
- 65 point spread between best (GPT-5.5) and third-best (Gemini 3 Flash at 5%)
- Tasks require ~5.5x more code than traditional bug-fixing benchmarks

**Program Synthesis** (ProgramBench, ≥95% test pass):
- Claude Opus 4.7: 3% success rate
- Claude Opus 4.6: 2.5%
- Claude Sonnet 4.6: 1.6%
- No model achieves 100% test pass on any program
- Represents [[long-horizon-coding]] challenge: converting ideas → functional programs without human oversight

**Implications**:
- Bug-fixing capabilities (SWE-bench) significantly exceed feature implementation and program synthesis
- Brief prompt handling remains more challenging than detailed specifications
- Full program creation from ideas represents frontier capability gap
- System diagnosis (ITBench-AA) addresses different skill set: infrastructure reasoning vs. code generation