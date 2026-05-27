---
tags: [agent-approval, agent-architecture, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-gravity, agent-harness, agent-harness-integration, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agent-workload-migration, agentic-ci-cd, agentic-security, agentic-tasks, agentic-workflows, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-cost-forecasting, ai-sandboxes, ai-sre, autonomous-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, cicd-deployment-constraints, claude-opus, cloud-economics, codex, codex-updates, content-addressed-caching, context-reprocessing, context-window, conversational-ai, custom-agents, dark-factory, data-exfiltration, data-gravity, databricks, daytona, deepseek-v4-pricing, deployment-automation, dynamic-resource-scaling, edge-compute, eval-infrastructure, exfiltration-attacks, feature-flags, feature-flags-agents, frontier-evals, ghost-libraries, ghost-tokens, harness-engineering, hidden-token-multipliers, human-in-the-loop, hyperscale-operations, inference-cost, infrastructure-efficiency, latency-optimization, lethal-trifecta, liquid-ai-architecture, local-inference, localhost-replacement, manager-agents, mcp-tools, mcp-vs-cli, meta-efficiency-agents, microsoft-copilot, microsoft-fabric, model-api-coopetition, model-behavior-engineer, model-harness-cotraining, model-lab-strategy, model-product-stack, non-determinism-control, non-deterministic-outputs, notion-custom-agents, operational-automation, performance-optimization, platform-competition, platform-lock-in, power-bi, pre-authenticated-links, progressive-rollouts, progressive-tool-disclosure, prompt-injection, qwen, react, react-pattern, reflexion, regression-detection, regulated-agent-deployment, regulatory-compliance, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, runtime-personalization, safe-rollouts, sandbox-infrastructure, self-reflection, semantic-layer, shadow-traffic, shopify-ai-stack, simgym-customer-simulation, skills-encoding, software-factories, software-v2, strategic-agents, tool-based-agents, tool-placement, workload-migration]
---

# Agentic Workflows in Production

Tracks patterns, architectures, and operational practices for deploying AI agents in production environments. Covers orchestration, safety mechanisms, compute infrastructure, and real-world deployment constraints.

## Agent Gravity Concept (Tunguz, May 2026)

**Agent Gravity Definition**: The force that keeps agents and their associated workloads on a particular platform, analogous to [[data-gravity]] in the prior decade.
- **Core thesis**: "If data gravity was the most important force in the Decade of Data, agent gravity will be the same in the Decade of Agents"
- Agents require tremendous compute resources, making compute placement a strategic competitive battleground
- The more agents and data running through a platform, the greater the gravitational pull

### Platform Lock-in Dynamics
- **Decision control**: The person building agents—or the agent itself—decides where to run the agent (agent gravity) and where to process data (data gravity)
- **Migration risk**: Agents can enable rapid platform migration by:
  - Siphoning knowledge from semantic layers
  - Migrating data to competing cloud data warehouses
  - Publishing data to alternative BI systems
- **User awareness**: Users may migrate profitable agent workloads and data warehouse workloads "knowingly or unknowingly"

### Databricks-Microsoft Case Study (May 2026)
- Databricks introduced feature on Microsoft platform enabling Power BI customers to manage data and build AI agents in Databricks
- Effect: Made it easier to build agents outside Microsoft's competing offering (Fabric)
- Microsoft reportedly restricted the feature, demonstrating platform defensive strategies
- Illustrates how agent-building capabilities can threaten established platform lock-in

### Strategic Implications
- **Primary competitive dynamic**: "Winning & sustaining agent gravity is the motif of the Decade of Agents"
- Platforms will actively fight to keep agent workloads on their infrastructure
- Agent placement decisions compound with data gravity effects
- See also: [[build-vs-buy-enterprise-ai]] for infrastructure economics considerations