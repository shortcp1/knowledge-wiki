---
tags: [agent-architecture, agent-harness, agent-harness-design, agentic-behavior, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, anthropic, antigravity-cli, autonomous-agents, autonomous-debugging, autonomous-fine-tuning, autonomous-research, backend-development, benchmark-contamination, benchmark-vs-deployment, browser-automation, chain-of-thought, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, code-quality-evaluation, codex-cli, codex-goals, coding-agents, composer, context-caching, cors-debugging, creative-agents, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, desktop-agent-harness, desktop-agents, diffusion-transformers, false-positives, frontend-code, frontier-model-competition, frontiercode, function-calling, goal-driven-agents, grok-imagine, html-injection, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, javascript-injection, keyboard-simulation, llm-capability-eval, llm-driven-loops, local-server-debugging, long-running-tasks, low-precision-training, mac-automation, maintainability, memory-systems, mixture-of-experts, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, open-source-agents, open-weights, open-weights-fine-tuning, opencode, opencoworker, orchestration, planning-architectures, post-training, proactive-agents, productivity-metrics, prompt-engineering, pyobjc, react, recursive-self-improvement, reflection-mechanisms, reflexion, reinforcement-learning-from-feedback, research-workflows, reward-hacking, rsi, scientific-ai, scratch-html-testing, screencapture-cli, screenshot-automation, self-reflection, software-development-acceleration, specialized-tools, strategic-iteration, streaming-asr, swe-bench, swe-bench-pro-hard-aa, synthetic-data-generation, task-automation, task-decomposition, terminal-bench, tool-calling, tool-use, tool-use-patterns, tree-of-thoughts, vector-st]
---

=== ai-engineering-agents ===

== Cursor Composer ==

=== Composer 2.5 (June 2026) ===
**Architecture**: Based on [[moonshot]] Kimi K2.5, mixture-of-experts transformer with 1.04 trillion parameters, 32 billion active per token

**Training Methodology**:
- Started with Kimi 2.5 open weights
- Additional pretraining on large code dataset
- Reinforcement learning using simulated agentic harness matching Cursor CLI tools
- Rewarded for success, brevity, and elegance of output
- **Text feedback during RL**: Model receives textual correction suggestions (e.g., better tool calls) loaded into context window, using correct output for teaching
- **Synthetic task scaling**: 25x more synthetic tasks than Composer 2, focusing on harder problems (e.g., feature deletion with artifact cleanup and testing)
- Model generator for synthetic tasks: undisclosed

**Context & Capabilities**:
- Input: up to 200,000 tokens
- Function calling, reasoning, context caching
- Image output via tool calls

**Pricing**:
- Standard: $0.50/$0.20/$2.50 per million input/cached/output tokens
- Fast mode: $3.00/$0.50/$15 per million input/cached/output tokens
- Subscriptions from $20/month

**Performance** (as of June 2026):
- Artificial Analysis Coding Agent Index: 63 (3rd overall)
  - Behind Claude Opus 4.7 max reasoning (67) and GPT-5.5 xhigh reasoning (65)
  - Outperforms both at lower reasoning settings
- SWE-Bench-Pro-Hard-AA: 1st place
- Time per task: 6.7 minutes (2nd place, vs Claude Opus 4.8 medium at 8.8 min)
- Cost per task (fast mode): $0.44 (2nd place, vs Claude Opus 4.7 Max at $4.14)
- CursorBench (Cursor's internal benchmark, simulating terse inputs and harder problems):
  - Composer 2.5: 63.2%
  - Claude Opus 4.7 max: 64.8%
  - GPT-5.5 max: 64.3%
  - **Outperforms both at default settings** (61.6% and 59.2% respectively)

**Design Philosophy**: Built specifically for agentic coding, with model and harness co-designed. Training harness matches deployment environment (Cursor CLI).

=== Composer 2 (March 2026) ===
Previous version, also based on Kimi K2.5. Training recipe published in paper.

== Related Benchmarks ==
- **Artificial Analysis Coding Agent Index**: Composite of SWE-Bench-Pro-Hard-AA, Terminal-Bench v2, and SWE-Atlas-QnA
- **CursorBench**: Cursor's internal benchmark designed to better simulate real agentic coding with terse user inputs and harder problems
- See also [[swe-bench]], [[frontiercode]]