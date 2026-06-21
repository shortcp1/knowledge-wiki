---
tags: [4-bit-quantization, agent-architecture, agent-harness, agent-harness-design, agent-loops, agent-state-tracking, agentic-behavior, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, anthropic, antigravity-cli, autonomous-agents, autonomous-debugging, autonomous-fine-tuning, autonomous-research, autonomous-workflows, backend-development, benchmark-contamination, benchmark-design, benchmark-vs-deployment, browser-automation, chain-of-thought, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, code-quality-evaluation, codex-cli, codex-goals, coding-agents, coding-models, composer, context-caching, cors-debugging, creative-agents, cron-loops, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, deepswe, desktop-agent-harness, desktop-agents, diffusion-transformers, false-positives, feature-implementation, feature-implementation-agents, frontend-code, frontend-coding, frontier-model-competition, frontiercode, function-calling, glm-5.2, goal-based-agents, goal-driven-agents, goal-loops, grok-imagine, heartbeat-loops, hermes-agent, hook-loops, html-injection, hybrid-transformer-mamba, indexshare, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, javascript-injection, keyboard-simulation, llm-capability-eval, llm-driven-loops, local-server-debugging, long-context, long-horizon-coding, long-running-tasks, loop-design, loop-engineering, low-precision-training, mac-automation, maintainability, memory-systems, mini-swe-agent, mixture-of-experts, model-specialization, multi-teacher-distillation, multi-token-prediction, multimodal-alignment, multiturn-reasoning, nemotron-3-ultra, open-closed-model-gap, open-source-agents, open-weights, open-weights-fine-tuning, openclaw, opencode, opencoworker, orchestration, planning-architectures, post-training, pr-automation, pr-review-automation, reasoning-budget, reasoning-modes, tool-use]
---

## Nemotron 3 Ultra: Agent-Optimized Model

**Released**: June 2026  
**Developer**: Nvidia  
**Design Focus**: Long-running agentic tasks

### Agent-Specific Features

#### Reasoning Control
- **Three reasoning modes**: off, regular, medium
- **Reasoning budget**: Configurable resource allocation for reasoning steps
- Allows developers to balance reasoning depth with speed/cost requirements

#### Tool Use
- Native tool use capabilities integrated during post-training
- Reinforcement learning specifically included agentic tasks in training environments
- See [[model-architecture]] for full training pipeline details

#### Agent Harness Integration
- Fine-tuned specifically for open agent harnesses:
  - **Hermes Agent**: Community agent framework
  - **OpenClaw**: Open-source agent harness
- Optimized for long-running autonomous workflows
- 1M token context window supports extended agent sessions

### Training for Agentic Behavior
- Multi-domain reinforcement learning across:
  - Reasoning tasks
  - Coding tasks
  - **Agentic tasks** (explicitly included)
  - Chat interactions
  - Safety constraints
  - Usability optimization
- Automatically verifiable rewards during RL phase
- Multi-Teacher On-Policy Distillation with domain-specialized teachers

### Performance Characteristics
- **Speed**: ~183 tokens/second (fastest among comparable open-weights models)
- **Context**: 1M tokens (supports long agent sessions)
- Prioritizes sustained performance for long-running tasks over peak benchmark scores
- See [[inference-efficiency]] for technical optimizations

### Availability for Agent Development
- Open weights under OpenMDW-1.1 license
- Training recipes and reinforcement learning environments published
- Enables community fine-tuning for specialized agent applications
- API access via Nvidia and partners at $0.60/$2.60 per million input/output tokens

**Cross-references**: [[model-architecture]], [[inference-efficiency]], [[reasoning-modes]], [[tool-use]], [[open-weights-fine-tuning]]