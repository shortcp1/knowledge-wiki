---
tags: [agent-architecture, agent-composition, agent-deployment, agent-harness, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-self-configuration, agentic-tasks, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-sre, autonomous-agents, bare-metal-infrastructure, behavioral-data-moats, chain-of-thought, cicd-deployment-constraints, claude-opus, cloud-economics, codex, content-addressed-caching, conversational-ai, custom-agents, dark-factory, deployment-automation, edge-compute, feature-flags, feature-flags-agents, frontier-evals, ghost-libraries, harness-engineering, human-in-the-loop, hyperscale-operations, infrastructure-efficiency, latency-optimization, liquid-ai-architecture, local-inference, manager-agents, mcp-tools, mcp-vs-cli, meta-efficiency-agents, model-behavior-engineer, non-determinism-control, non-deterministic-outputs, notion-custom-agents, operational-automation, performance-optimization, progressive-rollouts, progressive-tool-disclosure, qwen, react, react-pattern, reflexion, regression-detection, regulated-agent-deployment, regulatory-compliance, runtime-personalization, safe-rollouts, self-reflection, shadow-traffic, shopify-ai-stack, simgym-customer-simulation, skills-encoding, software-factories, software-factory, spec-driven-development, symphony, symphony-orchestration, tangent-auto-research, tangle-ml-workflows, task-decomposition, task-routing-patterns, temporal-workflows, thought-action-observation-loop, token-billionaires, token-budget-unlimited, token-spend-optimization, tokenmaxxing, tool-use, tree-of-thoughts, vector-store, wealth-management, workflow-engines, zero-human-code]
---

# Agentic Workflows in Production

Covers real deployments of multi-step AI agent systems in production environments: human-in-the-loop designs, failure recovery, audit trails, latency management, and cost control. Distinguishes between what works in demos vs. what ships to customers.

Key questions tracked: What agent architectures are actually in production at scale? Where do agents fail in ways that matter? How are teams handling agent observability and debugging?

## Key Claims
<!-- agent-maintained -->

### Citi Sky: Regulated Agent Deployment Pattern (2026)
**Pattern**: Customer-facing conversational agent in highly regulated environment (financial services)

**Architecture Decisions**:
- **Strict routing and bounded context**: Agent operates only within Citi-defined tool use and data access limits
- **Runtime personalization vs. training-time**: User-specific context applied at inference, not embedded in model training — reduces hallucination risk and maintains compliance
- **Determinism enforcement**: System design controls to counter generative AI's inherent non-determinism (same input → different outputs)
- **Hard capability boundaries**: Agent cannot execute transactions, only interpret and prepare
- **Human-in-the-loop**: Advisors remain "final point of control" for all material actions

**Key Engineering Challenge** (per JP Suh, Google DeepMind): "The challenge is not building intelligence, but controlling it" in regulated environments where consistency is mandatory.

**Production Trade-offs**:
- Sacrifices model flexibility for regulatory compliance
- Separates reasoning from personalization to maintain audit trail
- Uses controlled data access layer rather than RAG over unrestricted corpus

**Generalizability**: This "bounded agent" pattern applies to:
- Healthcare diagnostics (advisory only, clinician executes)
- Legal research platforms (suggest, don't file)
- Government services (guide, don't transact)
- Enterprise procurement (recommend, don't purchase)

## Cross-References
- [[ai-wealth-management-advisory]]
- [[ai-governance-risk-compliance]]