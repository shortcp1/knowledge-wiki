---
tags: [agent-legibility, agent-orchestration, agent-token-costs, agentic-ai, agentic-token-consumption, ai-budgeting, ai-code-review-bottleneck, ai-in-product-and-engineering, anthropic-claude, api-pricing, async-agents, autonomous-agents, autoregressive-transformer, background-agents, behavioral-data-moats, biotech-ai-tools, cancer-treatment-matching, cicd-deployment-constraints, claude-anthropic, code-generation, code-quality-bottleneck, codex, codex-adoption, coding-agents, cognition-devin, content-addressed-caching, context-engineering, cursor-adoption, cursor-agents-pane, cursor-ide, cursor-michael-truell, dark-factory, data-quality-blockers, devin, engineering-ai-maturity, enterprise-adoption, enterprise-pricing, function-specific-adoption, ghost-libraries, harness-engineering, liquid-ai-architecture, monetization-strategy, multimodal-biotech-data, openai-codex, openai-frontier, pharma-licensing, product-market-fit, productivity-measurement, proprietary-datasets, ramp-coding-agent, saas-pricing, shopify-ai-stack, simgym-customer-simulation, spatial-transcriptomics, spec-to-pr, spec-to-pull-request, symphony, symphony-orchestration, tangent-auto-research, tangle-ml-workflows, three-waves-coding-tools, token-billionaires, token-budget-explosion, token-budget-unlimited, token-consumption, tool-fragmentation, variable-costs, virtual-cells, windsurf, zero-human-code]
---

# AI in Product & Engineering

Tracks AI applications in software development and product management: coding assistants (Copilot, Cursor, Claude), AI-assisted code review, test generation, PR automation, and AI-driven product analytics and roadmapping. Also includes AI tools for scientific and biotech product development.

Key questions tracked: What is the actual productivity multiplier from coding AI? Which workflows see the highest adoption? How are engineering orgs restructuring around AI tools?

## Key Claims
<!-- agent-maintained -->

### Enterprise AI Adoption Patterns
- **Shopify Internal AI Adoption (December 2025 - April 2026)**: Shopify experienced a "phase transition" in internal AI usage following a December 2025 model-quality inflection. By April 2026, the company had "near-universal A

### Three Waves of AI Coding Tools (2023-2026)
- **First Wave - Developer Acceleration**: GitHub Copilot and Cursor tab autocomplete made developers faster but kept them heavily in the loop. Workflow bottlenecked by developer's local IDE-centered flow.
- **Second Wave - Local Agents**: Claude Code, Windsurf, Cursor's agents pane - concurrent terminal execution within local environment.
- **Third Wave - Async/Background Agents (2025-2026)**: Shift to agent orchestration driving end-to-end development. "Spec to pull request" workflows becoming production-viable after December 2025 model inflection. Developers now "build the factory that creates their software" - managing fleets of agents as teammates rather than embedded tools.

*Source: Cognition CPO Walden Yan and Cursor's Michael Truell, May 2026*

### Cursor Product Evolution
- **Michael Truell (Cursor) - May 2026**: "Cursor is no longer primarily about writing code. It is about helping developers build the factory that creates their software. This factory is made up of fleets of agents that they interact with as teammates: providing initial direction, equipping them with the tools to work independently, and reviewing their work."
- **Product Components**: Tab autocomplete (first wave), agents pane (second wave), moving toward background agent orchestration (third wave)

### Cognition Devin Adoption Metrics
- **Internal Usage at Cognition**: Devin grew from 16% to 80% of commits across Cognition's own repositories
- **PR Volume**: 7x growth in merged pull requests
- **Context Engineering**: Walden Yan coined term to describe structuring information for agent consumption
- **Funding**: $1B Series D (announced ~May 2026), "way oversubscribed"

### Enterprise Custom Agent Development (2025-2026)
Wave of major companies building proprietary background agents despite availability of commercial products:
- **Shopify**: Building custom background agents
- **Stripe**: Building custom background agents  
- **Paradigm**: Building custom background agents
- **Razorpay**: Building custom background agents
- **Ramp**: Built coding agent using Modal infrastructure

*Pattern suggests companies prefer control/customization over off-the-shelf solutions even as products mature*

### Windsurf Evolution
- **Windsurf 2.0**: Released with enhanced capabilities (specific features not detailed in source)
- **Product Category**: Second-wave local agent (concurrent terminals)

### December 2025 Model Inflection
- **Industry-Wide Shift**: December 2025 marked a model quality inflection point that made spec-to-PR workflows practical in production
- **Workflow Enablement**: Enabled transition from second-wave (local agents) to third-wave (async/background agents)
- **Adoption Impact**: Triggered "phase transition" in enterprise adoption (see Shopify case)

### Coding Agent Market Structure
- **Major Agent-First Companies**: Sierra, Decagon, Notion, Cursor described as "major decacorn agent labs"
- **DIY Ecosystem**: LangGraph, Pydantic, Flue frameworks making custom agents easier
- **Managed Services**: Anthropic, Gemini (Google), Amazon offering managed agent platforms
- **Seat Pricing**: $20/seat model for agent products faces "tricky" monetization economics

## Cross-References
- See [[agentic-workflows-production]] for detailed architecture patterns and background agent infrastructure
- See [[ai-engineering-agents]] for agent frameworks and orchestration approaches
- See [[mcp-protocol]] for tool integration standards