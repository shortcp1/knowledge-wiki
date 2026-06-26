---
tags: [agent-audit-trail, agent-authorization, agent-clearinghouse, agent-context-serving, agent-evals, agent-execution-control, agent-governance, agent-governance-layer, agent-identity, agent-infrastructure, agent-memory, agent-permissioning, agent-permissions, agent-policy-enforcement, agent-telemetry, agent-traces, agentic-architecture, agentic-commerce, agentic-orchestration, agentic-workflows, agentic-workflows-production, ai-agents, ai-agents-meetings, ai-runtime, always-on-agents, amazon-bedrock, ambient-agents, anthropic-claude-tag, async-agents, async-delegation, async-inference, asynchronous-inference, authorization-context, background-agents, background-workers, batch-inference, batch-processing, change-management-costs, channel-permissions, claude-tag, clearinghouse-architecture, cloud-infrastructure, cloud-sandboxes, code-generation, code-ownership-tracking, coding-agents, context-window-management, conversational-context, cross-channel-coordination, custom-inference-chips, data-as-context, data-context, data-moats, databricks, dynamic-workflows, enterprise-moats, fleet-aware-orchestration, fleet-orchestration, fraud-detection, genie-one, git-webhook-integration, go-to-market-strategy, hours-long-agents, inference-cost-optimization, lakehouse, liability-models, live-operational-context, ltap, meeting-recording, memory-hierarchy, meta-harness, model-routing, modular-permissions, mosaic, multi-agent-coordination, multi-agent-routing, multi-agent-systems, multi-turn-agents, multiplayer-agents, omnigent, openai-frontier, operating-system-for-agents, orchestration-layer, parallel-agents, payment-governance, performance-per-watt, permission-gates, persistent-sessions, portability, proactive-agents, query-decomposition, queued-workloads, rl-fine-tuning, sailboxes, sakana-fugu, shared-context, slack-integration, slack-native-agents, spend-controls, spot-capacity, stacked-prompts, stateful-compute, stateful-policies, stateful-runtime, stateless-api, strategic-real-estate, swe-bench, switching-costs, system-of-record, systems-of-record, task-delegation, team-delegation-pattern, threshold-monitoring, tool-access-controls, tool-isolation, trainium-chips, transaction-authorization, unstructured-data, vendor-lock-in, vendor-lock-in-insurance, voice-agents, workflow-engines, zero-trust-agents]
---

## Shift to Asynchronous Agent Architecture

**Trend identified**: June 2026  
**Pattern**: Workload migration from synchronous chat to asynchronous, multi-turn agents

### Characteristics of Async Agents
- Run for hours rather than seconds
- Operate as background workers rather than chat assistants
- Execute without human-in-the-loop waiting
- Parallelize multiple agents on single task (e.g., "ten agents on a single task")
- Queue-based rather than real-time request/response

### Use Cases for Background Agents
- Overnight codebase scanning
- Bulk CRM row enrichment
- Document processing pipelines
- Deep research tasks
- Code review workflows
- Cybersecurity analysis

### Infrastructure Requirements

**Stateful compute units** (e.g., Sailboxes from [[inference-efficiency]]):
- Persist for entire task duration
- Maintain state across multi-turn workflow
- Pause during inference API calls
- Resume rapidly when responses arrive
- Billing based on active time only (no idle charges)

**Orchestration needs**:
- Fleet-aware routing across models
- Queue management for batch workloads
- Spot capacity utilization with failover
- Cost optimization through model selection

### Economic Implications
- Trade latency for cost: 6x cost reduction for 2-minute vs. 2-second response times
- Throughput optimization over cold-start latency
- "Token-maxxing": Maximizing work per dollar of compute
- Related to [[build-vs-buy-enterprise-ai]] cost considerations

**Market prediction**: "Vast majority of tokens will flow through a queue" as agents become background infrastructure

## Sail Research Platform

See [[inference-efficiency]] for technical details on fleet-aware orchestration and Sailboxes architecture.