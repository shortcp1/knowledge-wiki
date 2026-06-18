---
tags: [agent-architecture, agent-harness, agent-harness-design, agent-loops, agent-state-tracking, agentic-behavior, agentic-coding, agentic-coding-tools, agentic-loops, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, anthropic, antigravity-cli, autonomous-agents, autonomous-debugging, autonomous-fine-tuning, autonomous-research, autonomous-workflows, backend-development, benchmark-contamination, benchmark-vs-deployment, browser-automation, chain-of-thought, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, code-quality-evaluation, codex-cli, codex-goals, coding-agents, coding-models, composer, context-caching, cors-debugging, creative-agents, cron-loops, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, desktop-agent-harness, desktop-agents, diffusion-transformers, false-positives, frontend-code, frontend-coding, frontier-model-competition, frontiercode, function-calling, glm-5.2, goal-based-agents, goal-driven-agents, goal-loops, grok-imagine, heartbeat-loops, hook-loops, html-injection, indexshare, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, javascript-injection, keyboard-simulation, llm-capability-eval, llm-driven-loops, local-server-debugging, long-context, long-horizon-coding, long-running-tasks, loop-design, loop-engineering, low-precision-training, mac-automation, maintainability, memory-systems, mixture-of-experts, model-specialization, multimodal-alignment, multiturn-reasoning, open-closed-model-gap, open-source-agents, open-weights, open-weights-fine-tuning, opencode, opencoworker, orchestration, planning-architectures, post-training, pr-automation, pr-review-automation, proactive-agents, productivity-metrics, prompt-engineering, pyobjc, react, recursive-self-improvement, reflection-mechanisms, reflexion, reinforcement-learning-from-feedback, research-workflows, reward-hacking, rsi, scheduled-agents, scientific-ai, scratch-html-testing, screencapture-cli, screenshot-automation, subagent-spawning, subagents, work-trees]
---

## Agent Loop Design (Vo, June 2026)

### Core Definition
**What is a loop**: An automated prompt that runs without human intervention. Not a new paradigm—just automation of prompting with specific triggering mechanisms.

**Mental Model**: Design loops like "onboarding an employee"—define what they need to know, what they can do, and how they track progress.

### Four Loop Types

1. **Heartbeat Loops**
   - Continuous execution, runs constantly
   - Use case: Real-time monitoring, immediate response scenarios

2. **Cron Loops** 
   - Scheduled execution (time-based)
   - Example: Daily PR review at 10:15 a.m., weekly skills identification
   - Most predictable for production deployment

3. **Hook Loops**
   - Event-triggered execution
   - Fires when specific conditions/events occur

4. **Goal Loops**
   - Objective-driven execution
   - **Hardest to write well**: Most prone to token waste
   - Runs until specified objective is achieved
   - Requires careful design to avoid burning tokens "for nothing"

### Five Requirements for Production Loops

Every effective loop needs:

1. **Work Trees**: Structured breakdown of tasks the loop performs
2. **Skills**: Defined capabilities and what the agent knows how to do
3. **Plugins/Connectors**: Integration points with external systems
4. **Subagents**: Ability to spawn specialized agents for specific tasks
5. **State Tracking**: Mechanism to track progress and maintain context across runs

### Subagent Architecture

**Subagent Spawning**: Loops can create their own subagents for specialized tasks
- Example: PR review loop spawns subagents to analyze individual files
- Goal loops spawn validating subagents to check their own output in real time
- Enables division of labor within automated workflows

### Implementation Examples

**Claude Code**: Daily aging PR reviewer
- Cron-scheduled at specific time
- Spawns subagents for individual PR analysis
- Alerts team automatically

**Codex**: Weekly skills identification
- Cron-based weekly execution  
- Goal-based subagents for output validation
- Self-validating architecture

### Design Warning Signs

**Two indicators of problematic loop design**:
1. Loop will "get expensive before it gets useful"
2. (Second warning sign not specified in source material)

**Risk**: Poorly designed goal loops burn tokens without delivering value

### Cross-references
- See [[agentic-workflows-production]] for enterprise governance of loop-based agents
- See [[ai-in-product-and-engineering]] for production deployment considerations