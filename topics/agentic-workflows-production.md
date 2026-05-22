---
tags: [agent-architecture, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-harness, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agentic-ci-cd, agentic-tasks, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-sandboxes, ai-sre, autonomous-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, cicd-deployment-constraints, claude-opus, cloud-economics, codex, content-addressed-caching, conversational-ai, custom-agents, dark-factory, daytona, deployment-automation, dynamic-resource-scaling, edge-compute, eval-infrastructure, feature-flags, feature-flags-agents, frontier-evals, ghost-libraries, harness-engineering, human-in-the-loop, hyperscale-operations, infrastructure-efficiency, latency-optimization, liquid-ai-architecture, local-inference, localhost-replacement, manager-agents, mcp-tools, mcp-vs-cli, meta-efficiency-agents, model-behavior-engineer, non-determinism-control, non-deterministic-outputs, notion-custom-agents, operational-automation, performance-optimization, progressive-rollouts, progressive-tool-disclosure, qwen, react, react-pattern, reflexion, regression-detection, regulated-agent-deployment, regulatory-compliance, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, runtime-personalization, safe-rollouts, sandbox-infrastructure, self-reflection, shadow-traffic, shopify-ai-stack, simgym-customer-simulation, skills-encoding, software-factories, software-factory, spec-driven-development, stateful-environments, stateful-sandboxes, symphony, symphony-orchestration, tangent-auto-research, tangle-ml-workflows, task-decomposition, task-routing-patterns, temporal-workflows, thought-action-observation-loop, token-billionaires, token-budget-unlimited, token-spend-optimization, tokenmaxxing, tool-use, tree-of-thoughts, vector-store, wealth-management, workflow-engines, zero-human-code]
---

# Agentic Workflows in Production

Covers real deployments of multi-step AI agent systems in production envir

## Key Claims

### Agent Compute Infrastructure - Daytona Case Study (2026)

**Business Problem**: AI agents need stateful, instantly-scalable compute environments that can handle real-world software engineering workflows. Traditional localhost development and cloud infrastructure (Kubernetes/EKS/GKS) cannot meet the requirements of production agent workloads.

**AI Pattern Applied**: Agent sandboxes - composable computers accessible via API that provide:
- Stateful environments (not disposable execution boxes)
- Fast startup (~60ms for single sandbox, ~75 seconds for 50,000 sandboxes)
- Dynamic resource scaling (zero to 100,000 CPUs)
- Cross-platform support (Linux, Windows, macOS)
- Stateful snapshots for persistence

**Industry & Function**: AI Infrastructure / Developer Tools

**What Made It Succeed**:
- **Architectural choices**: Bare metal infrastructure with custom scheduler (not Kubernetes-based)
- **Product timing**: Pivoted from human dev environments to AI sandboxes when agents became default way of software development
- **Performance**: 60ms single sandbox startup enables real-time agent workflows
- **Scale**: Can handle extreme spikiness of RL/eval workloads
- **Open source strategy**: Helps agents integrate Daytona directly
- **New Year's Eve 2025/2026 MVP**: Customers "begged for API keys" after rapid prototype

**Quantitative Outcomes**:
- Largest customer runs ~850,000 sandboxes per day
- RL/eval workloads grew from 0% to ~50% of usage in months
- 50,000 sandboxes can spin up in ~75 seconds
- Single sandbox startup: ~60ms
- Workload spikes: zero to 100,000 CPUs for RL training runs

**Key Technical Insights**:
- **CLI vs MCP**: Ivan suggests CLI may give agents more power than Model Context Protocol
- **Kubernetes limitations**: Traditional K8s painful for agent workloads due to:
  - Slow startup times
  - Poor handling of extreme spikiness
  - Not optimized for stateful, long-running agent sessions
- **Stateful snapshots**: Critical for agent workflows that span multiple sessions
- **Cross-platform necessity**: Every AI agent may need a computer, including Windows/macOS (not just Linux)
- **Apple licensing constraints**: macOS sandboxes particularly challenging due to licensing restrictions

**Infrastructure Pattern**: "End of localhost" - development environments (and now agent environments) move from local machines to API-accessible cloud infrastructure. This thesis took over a decade to materialize, first attempted with CodeAnywhere browser IDE, finally realized with agent workloads.

**Generalizability**:
- **RL/eval workloads**: Any company doing reinforcement learning or large-scale model evaluation faces same zero-to-massive spike pattern
- **Software factories**: Autonomous code generation systems need stateful, long-running environments
- **AI research labs**: Frontier model development requires massive, dynamic compute for eval runs
- **CI/CD for agents**: Traditional CI/CD assumptions break when agents generate PRs - need new infrastructure patterns
- **Multi-agent systems**: Each agent may need isolated, stateful compute environment
- **Any domain where agents need to interact with real software environments**: testing, deployment, operations

**Market Context (2026)**:
- Consolidating "LLM OS stack" becoming standard toolkit
- Products getting "Computer" capability: Perplexity, Manus, Cursor
- Research evals assuming computer access: TerminalBench, GDPVal, Harbor
- Daytona one of small set of AI infra companies "booming" due to this shift

**Business Model Implications**:
- Customers compare against EKS/GKS and say they're "never going back"
- Ivan predicts AI cloud may look more like Stripe (API-first, usage-based) than AWS (infrastructure-centric)
- AI SaaS companies just reselling tokens may face "cold shower" - infrastructure layer has different economics

**Production Bottlenecks Identified**:
- Git operations and CI/CD systems not designed for agent-generated PRs
- Agent collaboration patterns stress traditional code review workflows
- Need for Windows/macOS environments (not just Linux) limits infrastructure options
- Apple licensing creates hard constraints on macOS sandbox availability