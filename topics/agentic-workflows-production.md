---
tags: [agent-approval, agent-architecture, agent-ceos, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-election-manipulation, agent-generated-commits, agent-gravity, agent-harness, agent-harness-integration, agent-infrastructure, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agent-workload-migration, agentic-ci-cd, agentic-deception, agentic-loop, agentic-loop-patterns, agentic-security, agentic-task-management, agentic-tasks, agentic-workflows, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-cost-forecasting, ai-safety-testing, ai-sandboxes, ai-sre, ambient-ai, andon-bengt, asana-integration, async-agents, autonomous-agents, background-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, ci-cd-agent-load, ci-cd-scaling, cicd-deployment-constraints, claude-opus, cloud-agents, cloud-economics, codex, codex-updates, coding-agents, content-addressed-caching, context-database, context-engineering, context-reprocessing, context-window, conversational-ai, custom-agents, dark-factory, data-exfiltration, data-for-capabilities-trade, data-gravity, databricks, daytona, deepseek-v4-pricing, deployment-automation, deterministic-vs-nondeterministic, docker-compose, dynamic-resource-scaling, edge-ai, edge-compute, email-access-agents, emergent-behavior, emergent-coordination, eval-infrastructure, exfiltration-attacks, face-recognition-training, feature-flags, feature-flags-agents, frontier-evals, frontier-models, ghost-libraries, ghost-tokens, github-actions, github-actions-compute, github-copilot, github-infrastructure-scale, harness-architecture, harness-engineering, harness-in-the-box, hidden-token-multipliers, human-in-the-loop, hybrid-routing, hyperscale-operations, inference-cost, infrastructure-efficiency, knowledge-distillation, latency-optimization, lethal-trifecta, liquid-ai-architecture, local-inference, local-models, localhost-replacement, long-horizon-agent-br, minimill-architecture, minimill-deployment, skill-distillation, task-classification, task-routing]
---

## Task Management Integration

### Asana-based Agentic Workflows (Tunguz, June 2026)
- **Architecture**: Tasks created in Asana, agent monitors and classifies tasks (scheduling, email triage, research, CRM updates)
- **Classification dimensions**: Easy vs. hard complexity routing
- **Routing logic**: Straightforward tasks → local model execution (seconds), complex tasks → cloud model execution
- **Observed metrics** (7-day production deployment):
  - 78% local execution rate (daily peaks: 88%)
  - Throughput improvement: +25%
  - Task duration: 47s → 19s average
  - Queue management: 73s → 4s queue age

### Skill Distillation for Task Routing
- **Technique**: Distilled skills enable local model to handle majority of routine agentic tasks
- **Integration pattern**: Distillation creates capability threshold for local execution; tasks above threshold route to cloud
- **Production evidence**: Single-user deployment achieving 78% local execution suggests distillation successfully captures common task patterns

See also: [[inference-efficiency]], [[model-distillation]], [[build-vs-buy-enterprise-ai]]