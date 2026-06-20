---
tags: [agent-audit-trail, agent-authorization, agent-clearinghouse, agent-context-serving, agent-evals, agent-execution-control, agent-governance, agent-governance-layer, agent-identity, agent-memory, agent-permissioning, agent-policy-enforcement, agent-telemetry, agent-traces, agent-trust-layer, agentic-commerce, agentic-orchestration, agentic-workflows, agentic-workflows-production, ai-agents-meetings, ai-platform-strategy, authorization-context, change-management-costs, clearinghouse-architecture, conversational-context, data-moats, dynamic-workflows, enterprise-moats, fraud-detection, go-to-market-strategy, liability-models, meeting-recording, multi-agent-coordination, orchestration-layer, payment-governance, strategic-real-estate, switching-costs, system-of-record, systems-of-record, transaction-authorization, unstructured-data, voice-based-systems, wedge-strategy, workflow-orchestration, workflow-switching-costs]
---

# Agentic Workflows in Production

## The Clearinghouse Pattern (Ball, June 2026)

### Core Thesis
**Business Problem**: In the emerging multi-agent enterprise ecosystem, organizations need a trust layer to manage autonomous agents from different vendors that access critical data and execute real transactions. Without centralized authorization, verification, and audit capabilities, agent deployment at scale becomes ungovernable.

**AI Pattern Applied**: Agent Clearinghouse Architecture
- A centralized governance layer that sits between autonomous agents and enterprise systems
- Not the agents themselves, but the authorization and coordination layer
- Analogous to financial market clearinghouses that enable transactions between parties who don't fully trust each other

### Four Control Dimensions
The clearinghouse pattern controls:
1. **Memory**: What agents know (access to historical context and data)
2. **Context**: What agents see and how information is served to them
3. **Execution**: What agents are authorized to do (action boundaries)
4. **Governance**: Permission policies and complete audit trail of agent actions

### Strategic Positioning
**Why This Creates Moats**:
- Migration difficulty exceeds traditional systems of record
- Consolidat

## The Evolution from SaaS to Agentic Moats (Ball, June 2026)

### Core Thesis Update
**Business Problem**: Traditional understanding suggested SaaS moats came from owning the system of record (data gravity). The actual moat was the hundreds of workflows touching that system. For AI/agentic systems, the moat shifts from data layer to orchestration layer.

**Pattern Applied**: Orchestration-Layer Moat Building
- Dynamic workflows (vs static SaaS workflows)
- Moat moves "up a layer" from where data sits to where work gets orchestrated
- System of record equivalent: orchestration platform managing agent workflows

### What Made SaaS Moats Work
**The Real Switching Cost**: Not data portability, but workflow reconstruction
- Porting data to new system of record was feasible
- The impossible part: rebuilding/verifying/testing/securing ALL workflows
- Many workflows were critical path or customer-facing
- Change management cost > value of switching systems

**Key Insight**: The platform with most workflows touching it had the moat (typically the system of record)

### The Agentic Translation
**Moat Location Shift**:
- **SaaS Era**: Moat at data layer → workflows formed around system of record
- **Agentic Era**: Moat at orchestration layer → workflows become dynamic
- The "database" in agentic world = the workflows themselves
- Winner = company owning where workflows get orchestrated

### Go-to-Market Strategy for Agentic Companies
**Anti-Pattern**: Don't try to build orchestration layer from day 1

**Recommended Playbook** (mirrors SaaS system of record evolution):
1. **Start Narrow**: Pick single workflow
   - Choose something appearing commoditized but strategic
   - Select workflow becoming more important (ride the right wave)
   - Do it much better than anyone else
   - Accept that others will assume no defensibility (advantage: underestimation)

2. **Use as Strategic Real Estate**:
   - Build adjacent workflows around initial wedge
   - Expand gradually and go deeper

3. **Build Orchestration Layer Last**:
   - Slowly build orchestration around workflow portfolio
   - Earn the right to "manage" (orchestrate) all workflows/agents
   - "Startups aren't static" - initial focus isn't final state

**Historical Parallel**: Salesforce wasn't touched by thousands of workflows on day 1. Started narrow/niche, owned single use case, got really good, then expanded until workflows built around them.

### Strategic Framework
**The Wedge Strategy**:
- Initial workflow = strategic real estate
- Important: where you start must be defensible territory you can build around
- End state: orchestration platform managing agent ecosystem

### Generalizability
**Applies To**:
- Any B2B function with multiple interconnected workflows
- Enterprise software categories transitioning to agentic architectures
- Vertical SaaS providers evolving to agent-based models
- Horizontal platforms managing cross-functional agent coordination

**Industry Applications**:
- Financial services (transaction orchestration)
- Supply chain (multi-party coordination)
- Healthcare (care coordination workflows)
- Legal (document and process workflows)
- HR/recruiting (candidate journey orchestration)
- Customer support (multi-channel agent coordination)

### Key Metrics for Success
While no quantitative outcomes cited in this analysis, success indicators would include:
- Number of workflows touching orchestration platform
- Percentage of critical-path workflows managed
- Time/cost to migrate away (switching cost proxy)
- Number of integrated agent vendors
- Workflow execution volume and diversity