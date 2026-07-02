---
tags: [intelligent-routing, local-models, async-batch-inference, skill-distillation, agentic-architecture, cost-optimization, agentic-workflows-production]
---

---
tags: [agent-audit-trail, agent-authorization, agent-clearinghouse, agent-context-serving, agent-evals, agent-execution-control, agent-governance, agent-governance-layer, agent-identity, agent-infrastructure, agent-memory, agent-permissioning, agent-permissions, agent-policy-enforcement, agent-telemetry, agent-traces, agentic-architecture, agentic-commerce, agentic-orchestration, agentic-workflows, agentic-workflows-production, ai-agents, ai-agents-meetings, ai-runtime, always-on-agents, amazon-bedrock, ambient-agents, anthropic-claude-tag, async-agents, async-delegation, async-inference, asynchronous-inference, authorization-context, background-agents, background-workers, batch-inference, batch-processing, change-management-costs, channel-permissions, claude-tag, clearinghouse-architecture, cloud-infrastructure, cloud-sandboxes, code-generation, code-ownership-tracking, coding-agents, coinbase-ai-spend, context-window-management, conversational-context, cost-optimization-defaults, cross-channel-coordination, custom-inference-chips, data-as-context, data-context, data-moats, databricks, dynamic-workflows, enterprise-moats, fleet-aware-orchestration, fleet-orchestration, fraud-detection, genie-one, git-webhook-integration, go-to-market-strategy, hours-long-agents, inference-cost-optimization, lakehouse, liability-models, live-operational-context, ltap, meeting-recording, memory-hierarchy, meta-harness, model-routing, modular-permissions, mosaic, multi-agent-coordination, multi-agent-routing, multi-agent-systems, multi-turn-agents, multiplayer-agents, omnigent, openai-frontier, operating-system-for-agents, orchestration-layer, parallel-agents, payment-governance, performance-per-watt, permission-gates, persistent-sessions, portability, proactive-agents, query-decomposition, queued-workloads, rl-fine-tuning, router-first-design, sailboxes, sakana-fugu, shared-context, skill-classifier, slack-integration, slack-native-agents, spend-controls, spot-capacity, stacked-prompts, stateful-compute, stateful-policies, stateful-runtime, stateless-api, strategic-defaults, three-tier-routing]---

## Router-First Architecture for Production Agents

**Design Philosophy** (Theory Ventures, July 2026): "Design your system around routing, not around models. Pick your models last."

### Why Routing Matters More Than Model Selection

**Cost optimization through tier selection**:
- Local models: effectively free per call
- Async batch inference: 90%+ cheaper than real-time (2 orders of magnitude)
- Real-time frontier models: most expensive, should be minority of traffic

**Target distribution**: 70-80% of agent traffic on local models for non-coding work (with proper routing)

### Three-Layer Routing System

See [[inference-efficiency]] for detailed routing architecture:
1. **Skill classifier**: Intent recognition (what is the task?)
2. **Router**: Tier selection (which compute tier?)
3. **Model selector**: Optimization within tier (which specific model?)

### Queueable vs Real-Time Work

**Key insight**: Most agent work does not need sub-second responses

**Queueable operations** (can run async):
- Draft replies
- Repository summaries  
- Diligence memos
- Nightly evaluator runs
- Background analysis tasks

**Real-time operations** (need immediate response):
- Interactive chat responses
- Live debugging sessions
- User-blocking operations

### Cost Optimization Through Defaults

**Coinbase Case Study** (Brian Armstrong, ~June 2026):
- Cut AI spend nearly in half while token usage grew exponentially
- **Not** achieved through friction (spend alerts, manual approvals)
- **Achieved through**: Better defaults, routing, and caching
- Engineers retain freedom to choose any model, but defaults guide most decisions

**Design principle**: Cost control via intelligent defaults, not restrictions

### Feedback-Driven Router Updates

Theory Ventures agent runtime implementation (July 2026):

**Synchronous layer**:
- Predictor annotates routes with five risk features before execution
- Catches known failure patterns: missing context, long dependencies, risky migrations, security-sensitive prompts, high-consequence writes

**Asynchronous layer**:
- Nightly batch evaluator scores previous day's traces
- Updates router weights based on actual performance
- Runs on async inference (Sail) to keep evaluation cost near zero
- Discovers new failure modes not caught by synchronous predictor

See [[inference-efficiency]] for routing implementation details