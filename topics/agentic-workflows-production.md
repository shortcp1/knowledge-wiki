---
tags: [agent-approval, agent-architecture, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-generated-commits, agent-gravity, agent-harness, agent-harness-integration, agent-infrastructure, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agent-workload-migration, agentic-ci-cd, agentic-loop, agentic-loop-patterns, agentic-security, agentic-tasks, agentic-workflows, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-cost-forecasting, ai-sandboxes, ai-sre, ambient-ai, async-agents, autonomous-agents, background-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, ci-cd-agent-load, ci-cd-scaling, cicd-deployment-constraints, claude-opus, cloud-agents, cloud-economics, codex, codex-updates, coding-agents, content-addressed-caching, context-database, context-engineering, context-reprocessing, context-window, conversational-ai, custom-agents, dark-factory, data-exfiltration, data-gravity, databricks, daytona, deepseek-v4-pricing, deployment-automation, deterministic-vs-nondeterministic, docker-compose, dynamic-resource-scaling, edge-compute, eval-infrastructure, exfiltration-attacks, feature-flags, feature-flags-agents, frontier-evals, frontier-models, ghost-libraries, ghost-tokens, github-actions, github-actions-compute, github-copilot, github-infrastructure-scale, harness-architecture, harness-engineering, harness-in-the-box, hidden-token-multipliers, human-in-the-loop, hyperscale-operations, inference-cost, infrastructure-efficiency, knowledge-distillation, latency-optimization, lethal-trifecta, liquid-ai-architecture, local-inference, local-models, localhost-replacement, manager-agents, markdown-workflows, mcp-integration, mcp-protocol, mcp-tools, mcp-vs-cli, meta-efficiency-agents, micro-skills, microsoft-copilot, microsoft-fabric, model-api-coopetition, model-behavior-engineer, model-harness-cotraining, model-lab-strategy, model-orchestration, model-product-stack, model-selection-strategy, non-determinism-control, non-deterministic-outputs, notion-custom-agents, open-source-maintenance, openclaw, operational-automation, out-of-the-box-, supply-chain-security, workiq]
---

# Agentic Workflows in Production

## GitHub: Scaling Infrastructure for Agent-Generated Code (2026)

### Business Problem
**Industry**: Software Development / Developer Tools  
**Company**: GitHub (Microsoft)  
**Business Function**: Platform Infrastructure, Developer Operations

**Problem**: GitHub's infrastructure, originally designed for human developers moving at human speed, faced massive scaling challenges as coding agents began generating code at unprecedented volumes. In 2026, agent-generated commits grew **1400%**, creating orders of magnitude pressure across every dimension:
- Volume of code shipped
- Frequency of commits
- Number of contributors
- CI/CD pipeline load
- Pull request volume
- Database and compute requirements

This resulted in publicly notable uptime issues as the platform struggled to absorb what AI produces.

### AI Patterns Applied

**1. Internal Operational Agents (WorkIQ + MCP)**
- **Pattern**: Multi-agent orchestration for internal operations
- **Implementation**: 
  - WorkIQ system for managing company context
  - Model Context Protocol (MCP) integration
  - Integration across Slack, Teams, email, and GitHub
  - "Micro-skills" architecture replacing large "mega-skills"
  - COO Kyle Daigle's "15 agents on Saturday" workflow
  - Agents used for summarization, communications, marketing, analyst work
  - AI-generated executive presentations for CRO/CFO teams

**2. GitHub Actions as Agent Compute Layer**
- **Pattern**: General-purpose compute infrastructure for agent workloads
- **Implementation**: Actions evolved beyond CI/CD to become compute layer for arbitrary agent code execution
- **Security considerations**: Webhooks, secure execution, supply-chain security

**3. GitHub Copilot Evolution**
- **Pattern**: Multi-surface agent deployment
- **Surfaces**: Code completion → CLI → Desktop app → Cloud agents → SDK
- **Features**: Context awareness, memory, rules, ambient AI
- **Goal**: Make GitHub "act like Kyle wants it to act"

**4. Agent-Generated Code Management**
- **New workflows**: "Prompt requests" vs traditional pull requests
- **Trust mechanisms**: Vouching systems, AI review for agent contributions
- **Open source challenge**: Managing floods of "slop" contributions from agents

### Success Factors

**What Made It Work:**
1. **Rollout through existing workflows** instead of forcing new tools
2. **Micro-skills architecture**: Small, atomic skills vs monolithic mega-skills
3. **Multi-surface strategy**: Meeting users where they already work (Slack, Teams, CLI, desktop)
4. **Leveraging existing infrastructure**: Building on GitHub Actions, webhooks, APIs
5. **Former developer leadership**: COO Kyle Daigle actively coding again, understanding agent capabilities firsthand

**What Created Challenges:**
1. **Infrastructure designed for human speed**: Orders of magnitude mismatch with agent output
2. **CI/CD bottlenecks**: "Can CI/CD keep up when every idea becomes a build?"
3. **Open source maintainer burden**: Massive increase in AI-generated contributions
4. **Uptime pressure**: 14x commit growth causing availability issues
5. **Social contract preservation**: Maintaining human aspects of software development while becoming "operating layer for agents"

### Quantitative Outcomes
- **1400% growth** in agent-generated commits (2026)
- **14x commit growth** overall
- **200M+ developers** on platform (including AI-enabled builders)
- Massive increases in:
  - Actions load
  - Database requirements
  - Monorepo operations
  - Pull request volume

### Generalizability

**This pattern applies to:**

1. **Any platform infrastructure serving both humans and agents**:
   - Code repositories (GitLab, Bitbucket)
   - Project management tools (Jira, Linear)
   - Communication platforms (Slack, Teams already implementing)
   - Document collaboration (Notion, Confluence)

2. **CI/CD and DevOps platforms**:
   - Jenkins, CircleCI, Travis CI
   - Cloud build services (AWS CodeBuild, Google Cloud Build)
   - Infrastructure as Code platforms (Terraform Cloud)

3. **Open source ecosystems**:
   - Package registries (npm, PyPI, RubyGems)
   - Any platform with contributor review workflows
   - Community-driven development platforms

4. **Enterprise operations**:
   - Any company using agents for internal workflows
   - Chief of staff and executive operations roles
   - Cross-functional coordination and summarization

**Key Insight**: When AI doesn't just autocomplete but fundamentally changes operational tempo, infrastructure must evolve from human-speed assumptions to agent-scale requirements. The "micro-skills" pattern and existing workflow integration are critical success factors.

**Critical Question**: "Can current systems around code absorb what AI produces?" This applies broadly to any system mediating between human decision-making and agent execution.