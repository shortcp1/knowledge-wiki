---
tags: [adversarial-review, agent-experience, agent-harness, agent-observability, agentic-systems, agentic-workflows, ai-engineering-agents, ai-harness, artifact-generation, automated-refactoring, bug-triage-automation, claude-agent-sdk, code-generation, context-engineering, custom-terminal-ui, custom-tooling, elastic-inference, evolutionary-search, gpu-snapshotting, harness-engineering, ink-library, multi-model-routing, observability-over-code, opinionated-adapters, opinionated-tool-adapters, programmatic-infrastructure, recursive-self-improvement, rl-rollouts, rust-migration, sandbox-environments, sentry-integration, serverless-functions, structured-artifacts, test-driven-agents, workflow-automation, workflow-constraints]---

---
tags: [agentic-ai, ai-coding-agents, ai-engineering-agents, autonomous-debugging, claude-code, claude-fable, coding-agents, cross-model-tool-compatibility, cuda-programming, economic-automation, gpu-kernel-optimization, model-regression, model-specific-tool-training, pre-release-testing, recursive-self-improvement, reinforcement-learning, reinforcement-learning-tool-bias, remote-labor-index, software-quality-assurance, tool-calling, tool-calling-reliability, tool-schema, transaction-management, harness-engineering, agent-harness, workflow-automation, file-system-memory, persistent-state-management, self-improving-agents, evolutionary-search, context-engineering, harness-optimization, loop-engineering, sub-agents, backend-jobs, goal-oriented-loops, bash-commands, artifact-management, auto-research, autoresearch-karpathy, conformance-suites, adversarial-review, language-migration, large-scale-refactoring, rust, zig, bun-runtime]---

## sqlite-utils 4.0rc2: Production Library Development with Claude Fable (July 2026)

**Source**: Simon Willison, "sqlite-utils 4.0rc2, mostly written by Claude Fable (for about $149.25)"

### Business Problem
- Final pre-release review and hardening of sqlite-utils 4.0 library before stable release
- Critical need to identify breaking changes and bugs before committing to SemVer major vers

## Harness Engineering

## What Is an Agent Harness (July 2026)

**Source**: Claire, "What a harness is and how to build one with Claude Agent SDK", Lenny's Newsletter

### Definition
- **Agent harness**: Code written around an AI agent to make it more effective at a specific job
- Not architecturally complex or mysterious—can be as simple as eight files and a terminal UI
- Both Cursor and [[claude-code]] are complex harnesses
- Represents owned infrastructure layer between general-purpose agents and specialized workflows

### When to Build a Harness

**Trigger conditions**:
- Same workflow requires same setup and same outcomes every time
- Job is partly deterministic (defined steps, defined tools) and partly non-deterministic (AI determines approach)
- Example: Sentry bug triage—consistent evidence-gathering process, standardized artifact output

### Design Principles

**Opinionated tool adapters over general MCP access**:
- Custom adapters pull exactly what matters for specific workflow, nothing else
- More effective than broad MCP access that allows agent to "wander"
- Result: faster execution, lower cost, reduced off-script behavior
- Example: Custom Sentry adapter vs. general Sentry MCP access

**Encoded permissions**:
- Constraints built into harness interface rather than prompted each time
- Example: "Investigate only, do not write code" as interface flag vs. repeated prompt instruction
- Eliminates need to remember and restate constraints

**Structured artifact output**:
- Separates one-off investigations from team-wide resources
- Consistent, scannable records without manual write-up
- Example bundle: task log, Sentry issue brief, relevant logs, worker report, HTML summary file

### Technical Advantages

**Multi-model routing**:
- Custom harness enables model selection per workflow step
- Different tool policies per invocation
- Model swapping without interface changes
- General-purpose tools (Claude Code, Codex) locked to single model

**Workflow specificity**:
- [[claude-agent-sdk]] enables precise control over agent behavior for repeated tasks
- Integration with specific tools ([[sentry-integration]], [[linear-integration]])

### Architectural Shift

**From general-purpose to orchestrated specialized**:
- Shift from "general-purpose agents do everything" to "general-purpose agents orchestrate specialized harnesses"
- Open chat fields remain useful but insufficient for consistent, repeatable workflows
- Constrained agent with specific harness produces more consistent output than powerful agent with open prompt

### ChatPRD Case Study: Sentry Bug Triage Harness

**Implementation using [[claude-agent-sdk]]**:
- Automated [[sentry-integration]] bug triage workflow
- Custom tool adapters for evidence gathering
- Permission encoding in interface
- Standardized artifact bundle output
- More consistent results than manual investigation