---
tags: [agent-approval, agent-architecture, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-gravity, agent-harness, agent-harness-integration, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agent-workload-migration, agentic-ci-cd, agentic-loop, agentic-loop-patterns, agentic-security, agentic-tasks, agentic-workflows, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-cost-forecasting, ai-sandboxes, ai-sre, autonomous-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, cicd-deployment-constraints, claude-opus, cloud-economics, codex, codex-updates, content-addressed-caching, context-database, context-reprocessing, context-window, conversational-ai, custom-agents, dark-factory, data-exfiltration, data-gravity, databricks, daytona, deepseek-v4-pricing, deployment-automation, deterministic-vs-nondeterministic, dynamic-resource-scaling, edge-compute, eval-infrastructure, exfiltration-attacks, feature-flags, feature-flags-agents, frontier-evals, ghost-libraries, ghost-tokens, harness-architecture, harness-engineering, hidden-token-multipliers, human-in-the-loop, hyperscale-operations, inference-cost, infrastructure-efficiency, latency-optimization, lethal-trifecta, liquid-ai-architecture, local-inference, localhost-replacement, manager-agents, mcp-protocol, mcp-tools, mcp-vs-cli, meta-efficiency-agents, microsoft-copilot, microsoft-fabric, model-api-coopetition, model-behavior-engineer, model-harness-cotraining, model-lab-strategy, model-orchestration, model-product-stack, model-selection-strategy, non-determinism-control, non-deterministic-outputs, notion-custom-agents, operational-automation, performance-optimization, platform-competition, platform-lock-in, power-bi, pre-authenticated-links, production-observability, progressive-rollouts, progressive-tool-disclosure, prompt-injection, qwen, react, react-pattern, reflexion, regression-detection, regulated-agent-deployment, regulatory-compliance, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, runtime-personalization, safe-rollouts, sandbox-isolation, sandbox-security, session-persistence, state-management, tool-registry]
---

## Harness Architecture Framework

**"Harness Era" Thesis (Tunguz, May 2026)**: The shift from SaaS to AI represents a transition from "fixed workflows" to "domesticating" powerful but unpredictable AI systems. This positions agent harnesses as the core competitive differentiator when all companies access the same foundational models.

### Seven Disciplines of Production Agent Harnesses

1. **Context & Memory**
   - Bespoke retrieval systems per vertical (radiology ≠ legal ≠ other domains)
   - Short-term memory: tracking agent state from seconds/minutes ago
   - Large-scale specialized retrieval: image databases for radiology, billion-document keyword search
   - **Context Database**: captures organizational SOPs, business recipes, and processes; must evolve as people and processes change
   - Cross-reference: [[ai-engineering-agents]]

2. **Tools & Action**
   - Tool registry exposing available actions
   - Argument validation before dispatch
   - Approval gates for sensitive operations
   - Failure handling and result parsing back into agent loop
   - **MCP as standard**: Model Context Protocol emerged as connective tissue for tool integration
   - Harness quality measured by: number of safely exposed tools + clean failure handling
   - Cross-reference: [[mcp-tools]], [[agent-approval]]

3. **Orchestration & Loop**
   - Core agentic pattern: think → act → observe → repeat
   - Planning, task decomposition, sub-agent delegation
   - Retry logic and stop conditions
   - **Closed-loop learning**: systems that improve from each run will differentiate vendors
   - Cross-reference: [[agentic-workflows]], [[react-pattern]]

4. **State & Persistence**
   - Crash resilience: resume at step N rather than restart from zero
   - Mechanisms: file systems, checkpoints, session threads, artifact storage
   - Critical for enterprise multi-user environments
   - Prevents work loss in long-running tasks

5. **Sandbox & Compute**
   - Isolated Unix workspaces per agent
   - Controlled network egress
   - Credential management outside model context
   - Requirements: security, confidentiality, scale performance
   - Cross-reference: [[agent-sandboxes]], [[ai-sandboxes]]

6. **Observability & Governance**
   - "You cannot trust what you cannot see"
   - Full step tracing and tool call logging
   - [[evals-production-deployment]] as regression tests
   - Human-in-the-loop for high-stakes decisions
   - Guardrails for policy enforcement
   - Evals catch regressions before customer impact
   - Cross-reference: [[human-in-the-loop]], [[regression-detection]]

7. **Cost & Workflow Optimization**
   - Architectural judgment: deterministic vs non-deterministic components
   - Model selection per task: frontier vs medium vs small vs fine-tuned
   - Knowledge placement: skills vs memory storage
   - Cross-reference: [[ai-cost-forecasting]], [[model-selection-strategy]]

### Competitive Dynamics

**Market Segmentation**: Major AI labs will dominate categories they prioritize through speed and direct model control. Thousands of vertical markets remain available for startups building specialized harnesses.

**Core Thesis**: "When every company has access to the same model, the best riders win." Competitive advantage shifts from model access to harness quality and vertical specialization.