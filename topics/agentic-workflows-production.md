---
tags: [agent-approval, agent-architecture, agent-ceos, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-election-manipulation, agent-generated-commits, agent-gravity, agent-harness, agent-harness-integration, agent-infrastructure, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-safety, agent-sandboxes, agent-self-configuration, agent-workload-migration, agentic-ci-cd, agentic-deception, agentic-loop, agentic-loop-patterns, agentic-security, agentic-task-management, agentic-tasks, agentic-workflows, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-cost-forecasting, ai-safety-testing, ai-sandboxes, ai-sre, ambient-ai, andon-bengt, asana-integration, async-agents, autonomous-agents, background-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, ci-cd-agent-load, ci-cd-scaling, cicd-deployment-constraints, claude-opus, cloud-agents, cloud-economics, code-sandbox, codex, codex-updates, coding-agents, content-addressed-caching, context-database, context-engineering, context-reprocessing, context-window, conversational-ai, custom-agents, dark-factory, data-exfiltration, data-for-capabilities-trade, data-gravity, databricks, datasette, daytona, deepseek-v4-pricing, deployment-automation, deterministic-vs-nondeterministic, docker-compose, dynamic-resource-scaling, edge-ai, edge-compute, email-access-agents, emergent-behavior, emergent-coordination, eval-infrastructure, exfiltration-attacks, face-recognition-training, feature-flags, feature-flags-agents, frontier-evals, frontier-models, ghost-libraries, ghost-tokens, github-actions, github-actions-compute, github-copilot, github-infrastructure-scale, harness-architecture, harness-engineering, harness-in-the-box, hidden-token-multipliers, human-in-the-loop, hybrid-routing, hyperscale-operations, inference-cost, infrastructure-efficiency, knowledge-distillation, latency-optimization, lethal-trifecta, liquid-ai-architecture, local-, micropython, micropython-wasm, plugin-sandboxing, plugin-systems, python-sandboxing, wasm-sandboxing, wasmtime, webassembly]
---

## Code Execution Sandboxing

### WebAssembly-based Python Sandboxing (2026)

**MicroPython-WASM Approach**: Simon Willison released `micropython-wasm` (alpha, June 2026) as a sandbox solution for running Python code safely within Python applications. Implementation uses MicroPython compiled to WebAssembly, executed via the `wasmtime` Python library.

**Key Requirements Met**:
- Clean PyPI installation with cross-platform binary wheels
- Memory and CPU limits enforceable (prevents resource exhaustion attacks like `while True: s += "longer string"`)
- Strict filesystem access control (can be disabled entirely or limited to specific files)
- Network access control through host-mediated layer
- Host function interaction support
- Active maintenance (wasmtime library is actively maintained)

**Technical Architecture**:
- WebAssembly provides isolation designed and battle-tested in browsers (~decade of production use)
- Dynamic language execution requires full interpreter compiled to WASM (not just compilation target)
- MicroPython chosen over CPython variants due to WASM compilation support
- Note: Pyodide (browser Python-in-WASM) explicitly not supported for server-side use

**Use Cases**:
- Plugin systems for [[ai-engineering-agents]] (Datasette, LLM, sqlite-utils)
- Data transformation (Datasette Enrichments)
- Scheduled tasks with controlled external data fetching
- `datasette-agent-micropython` plugin for Datasette Agent

**Security Posture**: Author explicitly notes alpha status and advises caution ("Should you trust my vibe-coded sandbox?" section mentioned but not detailed in excerpt). WebAssembly sandbox characteristics align with browser security model.

**Alternative Approaches Rejected**:
- JavaScript engines (V8): Too complex for embedding, existing Python wrappers insufficiently maintained or carry security warnings
- Direct CPython: No isolation capabilities

**Cross-references**: Relevant to [[ai-engineering-agents]] plugin architectures, [[agentic-security]] threat models