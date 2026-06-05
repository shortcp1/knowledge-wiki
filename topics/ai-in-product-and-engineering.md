---
tags: [agent-infrastructure, agent-legibility, agent-orchestration, agent-token-costs, agentic-ai, agentic-token-consumption, ai-budgeting, ai-code-review-bottleneck, ai-coding-agents, ai-in-product-and-engineering, ai-tool-economics, anthropic-claude, api-pricing, async-agents, autonomous-agents, autoregressive-transformer, backend-acceleration, backend-development, background-agents, behavioral-data-moats, biotech-ai-tools, cancer-treatment-matching, ci-cd-scaling, cicd-deployment-constraints, claude-anthropic, claude-code, code-generation, code-quality-bottleneck, codex, codex-adoption, coding-agent-acceleration-rates, coding-agents, cognition-devin, content-addressed-caching, context-engineering, cursor, cursor-adoption, cursor-agents-pane, cursor-ide, cursor-michael-truell, dark-factory, data-quality-blockers, developer-definition-expansion, devin, engineering-ai-maturity, enterprise-adoption, enterprise-ai-budgeting, enterprise-pricing, financial-orchestration, frontend-acceleration, frontend-development, function-specific-adoption, ghost-libraries, github-actions, github-copilot, github-copilot-evolution, github-spark, harness-engineering, infrastructure-acceleration, infrastructure-engineering, intuit-quickbooks-workforce, liquid-ai-architecture, low-code-transparency, mcp-integration, micro-skills, monetization-strategy, multimodal-biotech-data, open-source-maintenance, openai-codex, openai-frontier, operational-coordination, operational-coordination-layer, pharma-licensing, product-market-fit, productivity-measurement, prompt-requests, proprietary-datasets, quickbooks, ramp-coding-agent, research-acceleration, research-workflows, saas-pricing, shopify-ai-stack, simgym-customer-simulation, smb-operations, smb-software-integration, software-acceleration, software-development-acceleration, spatial-transcriptomics, spec-to-pr, spec-to-pull-request, supply-chain-security, symphony, symphony-orchestration, tangent-auto-research, tangle-ml-workflows, team-architecture, three-waves-coding-tools, token-billionaires]
---

# AI in Product & Engineering

Tracks how product and engineering teams are integrating AI tools into their workflows, including adoption patterns, productivity gains, infrastructure changes, and organizational impacts.

## Key Claims

### Differential Acceleration by Software Function (Apr 2026)
**Source**: Andrew Ng, The Batch Issue 350, Apr 24, 2026

**Business Problem**: Understanding realistic expectations for coding agent acceleration across different types of software work to architect teams effectively.

**AI Pattern**: Coding agents applied across different software engineering functions.

**Industry/Function**: Software development across all industries.

**Success Factors - Ranked by Acceleration Level**:

1. **Frontend Development (Most Accelerated)**:
   - **Why it succeeds**: Coding agents are fluent in popular frontend languages (TypeScript, JavaScript) and frameworks (React, Angular)
   - **Key capability**: Agents can examine their own work by operating a web browser, enabling effective iteration loops
   - **Limitation**: LLMs still weak at visual design, but fast at implementation given a design
   - **Use case**: Building web pages (e.g., ecommerce product description pages)

2. **Backend Development (Moderate-High Acceleration)**:
   - **Why less accelerated**: More human steering needed to think through corner cases leading to subtle bugs or security flaws
   - **Debugging complexity**: Backend bugs can cause non-intuitive downstream effects (e.g., corrupted databases with occasional incorrect results)
   - **Database migrations**: Easier with coding agents but still hard and require careful handling to prevent data loss
   - **Skill gap persists**: Skilled developers still design and implement far better backends than inexperienced developers using coding agents
   - **Use case**: Building APIs for data queries

3. **Infrastructure (Moderate Acceleration)**:
   - **Why less effective**: LLMs have relatively limited knowledge of infrastructure and complex tradeoffs
   - **Trust issues**: Critical infrastructure decisions rarely trusted to agents alone
   - **Testing bottleneck**: Infrastructure requires testing/experimentation period where fast coding doesn't help much
   - **Debugging difficulty**: Finding subtle infrastructure bugs (e.g., network misconfigurations) requires deep engineering expertise
   - **Use case**: Scaling sites to 10K+ active users while maintaining 99.99% reliability

4. **Research (Least Accelerated)**:
   - **Why least effective**: Research involves thinking through new ideas, formulating hypotheses, running experiments, interpreting results, modifying hypotheses, and iterating to conclusions
   - **Limited impact area**: Coding agents only speed up research code writing and experiment orchestration/tracking
   - **Non-coding bottlenecks**: Much research work doesn't involve coding
   - **Marginal help**: Today's agents provide only marginal assistance to research work overall

**Generalizability**: This acceleration hierarchy applies across software development in any industry. The pattern suggests organizations should adjust team expectations and velocity targets based on function:
- Frontend teams: Dramatically faster implementation expectations
- Backend teams: Significantly faster but still require skilled oversight
- Infrastructure teams: Modest acceleration, expert judgment still critical
- Research teams: Minimal expectation shifts from pre-agent baseline

**Organizational Impact**: Understanding these distinctions is critical for realistic team planning, velocity expectations, hiring decisions, and resource allocation in software organizations.

---

[Previous content continues...]