---
tags: [bnpl, agentic-commerce, kya-know-your-agent, autonomous-purchasing, intent-verification, financial-underwriting, agentic-workflows-production]
---

---
tags: [agent-framework, agent-skills, agentic-architecture, agentic-primitives, agentic-workflows-production, async-batch-inference, business-agents, cost-optimization, intelligent-routing, local-models, mcp-servers, skill-distillation, v0-coding-agent, vercel-eve, agentic-commerce, bnpl-agents, know-your-agent, kya, agent-intent-verification, agent-authorization-commerce, autonomous-buyers, infrastructure-mismatch, payment-agents, purchase-agents]---

## Agentic Commerce Infrastructure Gap (Zip Co, July 2026)

### Business Problem
**BNPL Infrastructure Meets Autonomous Commerce**:
- Traditional BNPL designed for humans making purchase decisions with visible intent signals
- Agentic commerce shifts purchasing decisions to software agents
- Core problem: "Infrastructure mismatch: autonomous buyers operating on systems built to verify human intent"
- Critical separation: Intent from action - "person making the purchase and person assuming the debt" no longer the same

### AI Pattern: Autonomous Purchase Agents
**Agentic Commerce Deployment**:
- AI agents purchasing, financing, and managing transactions on behalf of consumers
- Agents act as intermediaries between consumer intent and transaction execution
- Decision-making process becomes opaque to infrastructure layer
- Agents execute "exactly as instructed but produce outcomes consumer never wanted"

### Industry Impact: Payments/BNPL
**Function**: Consumer credit and point-of-sale financing
**Company**: Zip Co (Rory Herriman, CTO/COO)
**Challenge Domain**: Three critical verification questions:
1. "How do you verify intent when the buyer is software?"
2. "How do you underwrite a purchase when the decision-making process is invisible?"
3. "Who bears responsibility when an agent acts exactly as instructed but produces an outcome the consumer never wanted?"

### KYA Framework Emergence
**Know Your Agent Paradigm**:
- New acronym emerging alongside KYC (Know Your Customer)
- Requirements extending beyond agent authority verification
- Must prove "action reasonably reflected the user's objectives" - not just authorization but alignment
- BNPL providers positioned as "early test case" for broader payments ecosystem

### Success/Failure Factors
**Infrastructure Adaptation Required**:
- Traditional signal loss: BNPL relied on step-by-step human signals (product selection, price review, financing choice, terms acceptance)
- Each step provided risk and intent assessment data
- Agent-mediated transactions eliminate these intermediate verification points
- Open question: How to rebuild trust and risk models for opaque agent decision-making

### Generalizability: High
**Applicable to**:
- All consumer lending (credit cards, personal loans, mortgages)
- E-commerce platforms (product selection, vendor choice)
- Insurance purchasing and claims
- Healthcare appointment scheduling and provider selection
- Travel booking and itinerary management
- Subscription service management
- Any transaction where intent verification and responsibility assignment matter

**Pattern**: Whenever autonomous agents act as intermediaries in financial or high-stakes decisions, infrastructure must evolve from verifying human intent to verifying agent authority + alignment with user objectives