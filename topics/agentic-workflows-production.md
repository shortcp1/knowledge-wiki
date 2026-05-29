---
tags: [agent-approval, agent-architecture, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-gravity, agent-harness, agent-harness-integration, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agent-workload-migration, agentic-ci-cd, agentic-loop, agentic-loop-patterns, agentic-security, agentic-tasks, agentic-workflows, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-cost-forecasting, ai-sandboxes, ai-sre, async-agents, autonomous-agents, background-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, cicd-deployment-constraints, claude-opus, cloud-agents, cloud-economics, codex, codex-updates, coding-agents, content-addressed-caching, context-database, context-engineering, context-reprocessing, context-window, conversational-ai, custom-agents, dark-factory, data-exfiltration, data-gravity, databricks, daytona, deepseek-v4-pricing, deployment-automation, deterministic-vs-nondeterministic, docker-compose, dynamic-resource-scaling, edge-compute, eval-infrastructure, exfiltration-attacks, feature-flags, feature-flags-agents, frontier-evals, ghost-libraries, ghost-tokens, harness-architecture, harness-engineering, harness-in-the-box, hidden-token-multipliers, human-in-the-loop, hyperscale-operations, inference-cost, infrastructure-efficiency, latency-optimization, lethal-trifecta, liquid-ai-architecture, local-inference, localhost-replacement, manager-agents, mcp-protocol, mcp-tools, mcp-vs-cli, meta-efficiency-agents, microsoft-copilot, microsoft-fabric, model-api-coopetition, model-behavior-engineer, model-harness-cotraining, model-lab-strategy, model-orchestration, model-product-stack, model-selection-strategy, non-determinism-control, non-deterministic-outputs, notion-custom-agents, operational-automation, out-of-the-box-agents, performance-optimization, platform-competition, platform-lock-in, power-bi, pre-authenticated-links, production-observability, progressive-rollouts, progressive-tool-disclosure, prompt-injection, qwen, react, repo-setup, scoped-secrets, spec-to-pr, spec-to-pull-request, three-waves-agent-evolution, uncontrolled-vibe-coding, video-based-testing, vm-snapshots]
---

# Agentic Workflows in Production

## Key Claims
<!-- agent-maintained -->

### Three Waves of AI Coding Agent Evolution (2023-2026)
- **First Wave - Developer-in-the-Loop**: Tools like GitHub Copilot and Cursor tab autocomplete made developers faster but kept them heavily in the loop. Workflow remained centered around and bottlenecked by the developer's local IDE workflow - developer watching the model, accepting/rejecting changes, pushing code one interaction at a time.
- **Second Wave - Local Agents**: Tools like Claude Code, Windsurf, and Cursor's agents pane introduced first one and increasingly many terminals running concurrently within the local development environment.
- **Third Wave - Async/Background Agents (2025-2026)**: Following the December 2025 model inflection, the industry shifted to **agent orchestration** and **end-to-end development**. Agents work in the background with their own repo, machine, shell, browser, tests, memory, and review loops. Developers set up the "factory that creates their software" - fleets of agents they interact with as teammates rather than tools embedded in their flow. The workflow is "spec to pull request" becoming practical in production.
  - **Architecture shift**: Agents no longer sit solely inside the developer's flow but work independently in background/cloud environments
  - **Key enabler**: December 2025 model quality improvements made spec-to-PR workflows production-viable
  - **Industry adoption**: Wave of companies building background agents including Shopify, Stripe, Paradigm, Razorpay, Ramp (using Modal)

*Note: Previous guest Steve Yegge proposed 8 finer-grained levels to agent adoption; this three-wave model is a higher-level abstraction*

### Devin Production Metrics (Cognition, 2025-2026)
- **PR Growth**: Devin achieved 7x growth in merged pull requests
- **Commit Share**: Rose from 16% to 80% of commits across Cognition's own repositories
- **Context Engineering**: Term coined by Walden Yan (Cognition CPO/Cofounder) to describe the practice of structuring information for agent consumption

### Background Agent Architecture Patterns
- **Brain-Machine Separation**: Devin separates the "brain" (decision-making) from the "machine" (execution environment) for security and permissions management
- **Harness-in-the-Box vs Out-of-the-Box**: Two distinct architectural approaches to agent deployment infrastructure
- **Core Infrastructure Requirements**:
  - Full VMs (not just Docker) for complete isolation
  - VM snapshots for state management
  - Scoped secrets for security
  - GitHub bot integrations
  - Slack integrations for PM/developer interaction
  - Video-based testing capabilities
  - Docker Compose for complex service orchestration
- **Hardest Problem**: Repo setup remains one of the most challenging technical problems in background agent deployment
- **Docker Limitations**: "Docker is not always enough" for production agent environments - full VMs often required

### Multi-Agent Sentiment Shift (2024-2026)
- **2024**: Industry sentiment strongly against multi-agent systems
- **2025-2026**: Shift to "approaches that actually work" as model quality improved and architectural patterns matured

### Agent Product Economics & Monetization
- **Seat-Based Pricing Challenge**: $20/seat agent products face tricky monetization economics
- **Cognition Revenue Model**: Sells beyond just Devin tool access - includes infrastructure, onboarding, integrations, and adoption support
- **Funding Signal**: Cognition raised $1B Series D (announced ~May 2026), reportedly "way oversubscribed" despite proliferation of DIY agent frameworks and managed agent offerings

### Production Agent Workflows
- **AI Code Review**: Agents handling automated code review in production
- **SRE Auto-Triage**: Agents performing site reliability engineering issue triage
- **PMs Shipping Code from Slack**: Product managers able to ship code directly via Slack-integrated agents without touching IDE
- **Hybrid Frontier/Sub-Frontier Systems**: Production systems combining frontier models with smaller, specialized models

### Key Failure Mode: Uncontrolled Vibe Coding
- **Risk**: When agents operate with insufficient constraints, codebases can regress to the quality of "your worst engineer"
- **Implication**: Background agents require guardrails, review loops, and quality controls to maintain codebase standards

### Competitive Landscape Context
- **Agent Framework Proliferation**: LangGraph, Pydantic, Flue and others making DIY agents easier
- **Managed Agent Offerings**: Anthropic, Gemini (Google), and Amazon offering managed agent services
- **Major Agent-First Companies**: Sierra, Decagon, Notion, Cursor positioned as "major decacorn agent labs"
- **Industry Custom Builds**: Despite availability of products, major companies continuing to build proprietary agents

## Cross-References
- See [[ai-engineering-agents]] for broader agent framework landscape
- See [[ai-in-product-and-engineering]] for enterprise adoption patterns and coding assistant evolution
- See [[mcp-protocol]] for tool integration standards (noted limitations in multi-agent orchestration)
- See [[liquid-ai-architecture]] for related infrastructure patterns