---
tags: [agent-architecture, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-harness, agent-harness-integration, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agentic-ci-cd, agentic-tasks, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-sandboxes, ai-sre, autonomous-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, cicd-deployment-constraints, claude-opus, cloud-economics, codex, codex-updates, content-addressed-caching, conversational-ai, custom-agents, dark-factory, daytona, deepseek-v4-pricing, deployment-automation, dynamic-resource-scaling, edge-compute, eval-infrastructure, feature-flags, feature-flags-agents, frontier-evals, ghost-libraries, harness-engineering, human-in-the-loop, hyperscale-operations, infrastructure-efficiency, latency-optimization, liquid-ai-architecture, local-inference, localhost-replacement, manager-agents, mcp-tools, mcp-vs-cli, meta-efficiency-agents, model-api-coopetition, model-behavior-engineer, model-harness-cotraining, model-lab-strategy, model-product-stack, non-determinism-control, non-deterministic-outputs, notion-custom-agents, operational-automation, performance-optimization, progressive-rollouts, progressive-tool-disclosure, qwen, react, react-pattern, reflexion, regression-detection, regulated-agent-deployment, regulatory-compliance, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, runtime-personalization, safe-rollouts, sandbox-infrastructure, self-reflection, shadow-traffic, shopify-ai-stack, simgym-customer-simulation, skills-encoding, software-factories, software-factory, spec-driven-development, stateful-environments, stateful-sandboxes, symphony, symphony-orchestration, systems-over-models, tangent-auto-research, tangle-ml-workflows, task-decomposition, task-routing-patterns, temporal-workflows, thought-action-observation-loop, token-billionaires, token-budget-unlimited, token-spend-optimization, tokenmaxxing, tool-use, tree-of-thoughts, vector-store, wealth-management, workflow-engines, zero-human-code]
---

# Agentic Workflows Production

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchmark. This represents a ~47x improvement in solving real-world software engineering problems over ~2.5 years.
- **METR Time Horizons**: AI systems show rapid progress in completing increasingly complex tasks measured by human-equivalent time horizons. GPT-3.5 (2022) could handle tasks taking a person a few minutes; frontier models by 2026 can reliably complete multi-hour tasks (specific 50% reliability threshold not provided in excerpt, but trend indicates continuous expansion of task complexity).
- **Industry Adoption Pattern (2026)**: "Vast majority" of people at frontier labs and Silicon Valley now code entirely through AI systems, with increasing use of AI for test writing and code verification. This suggests

## Strategic Shifts in Agent Development

### Model Labs Becoming Agent Labs (May 2026)
- **Product surface moving up-stack**: Model quality alone no longer sufficient moat; winning products require "model + harness + workflow + UI + memory + economics" integration (Greg Brockman, OpenAI, May 2026)
- **Stance reversal**: Major shift from OpenAI's previous position that model providers should focus solely on models, with Greg Brockman now stating "the model alone is no longer the product"
- **Industry-wide pivot**: 
  - AI21 shut down model team, pivoting entirely to agents (May 2026)
  - DeepSeek building "Harness team" for first time (May 2026)
  - Pattern: "model <> harness <> product symbiosis" now considered requirement for top-tier products

### Model-Harness Co-training Strategy
- **Closed ecosystem concern**: Models co-trained with proprietary harnesses may only perform meaningfully with closed-source agent systems
- **Strategic implication**: Enables model labs to funnel users to their agent products at expense of model/API access, potentially reducing model co-opetition
- **Validation vs lock-in**: "Systems over Models" advocates see this as validation, but nuance involves potential for increased platform lock-in through post-training

### Coding Agent Product Differentiation (May 2026)

#### OpenAI Codex Updates
- **Codex Thursday No. 6 features**: 
  - Appshots capability
  - /goal command improvements
  - Remote computer use while locked
  - Annotation mode
  - Plugin sharing
  - Analytics dashboard
- **Workflow displacement**: Users reporting haven't opened IDE in over a month; Greg Brockman: "hard to remember coding before Codex"
- **Product maturity issues**: Remote workflows reported as buggy despite feature availability

#### Claude Coding Tools
- **ClaudeDevs expansion**: Auto mode expanded to Pro plan with Sonnet 4.6 support (May 2026)
- **Antigravity 2.0**: Required clarification and patches for IDE support after user backlash

#### Interface Evolution
- **Ambient AI + Agentic AI**: Framed as "new seam of computing interfaces"
- **Harness research convergence risk**: Concern that harness research converging on "replicate Claude Code" rather than exploring broader interface possibilities

### Production Deployment Patterns

#### Product Stack Requirements
- **Required components**: Model quality, harness engineering, workflow integration, UI/UX, memory systems, cost economics
- **Integration depth**: Top products require deep symbiosis across all layers rather than modular composition

#### Remote Development Capabilities
- **T3 Code remote feature**: Reported as ahead of alternatives for remote development workflows
- **Codex remote use**: Available while system locked, but workflow stability issues reported

Cross-references: [[model-architecture]] for co-training implications, [[ai-engineering-agents]] for broader agent capabilities