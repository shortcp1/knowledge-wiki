---
tags: [advisor-training, ai-wealth-management-advisory, claude-integration, conversational-ai, crm-rag, firm-scaling, founder-knowledge-transfer, human-in-the-loop, knowledge-transfer, non-deterministic-outputs, regulatory-compliance, runtime-personalization, secure-ai-deployment, sop-automation, wealth-advisory-workflows, wealth-management]
---

# AI in Wealth Management & Advisory

Tracks AI deployment across RIA, broker-dealer, and wealth management platforms: advisor productivity tools, client-facing AI, personalized financial planning, portfolio commentary generation, and compliance automation specific to the advisory space.

Key questions tracked: Which compliance constraints are most binding for AI in advisory? How are custodians (Schwab, Fidelity, Pershing) building or enabling AI? What is the evidence on advisor productivity multipliers?

## Key Claims
<!-- agent-maintained -->

### Citi Sky (Citi Wealth + Google DeepMind, 2026)
**Business Problem**: Shift wealth management from scheduled, pull-based advisor interaction to continuous, always-on advice availability while maintaining regulatory compliance and human oversight.

**AI Pattern Applied**: Conversational agent (multimodal, voice-enabled) with strict guardrails
- Built on Google DeepMind models
- Real-time portfolio, market, and opportunity insights
- Voice and multimodal interfaces for conversational experience
- **Does NOT execute trades** — interprets, explains, and prepares only
- Human advisors remain final point of control

**What Made It Work**:
- **System design over model intelligence**: Strict routing, Citi-specific tool use, and tightly bound context to ensure agent operates within defined limits
- **Separation of concerns**: Personalization kept separate from model reasoning — applied at runtime through controlled data access rather than embedded in training
- **Non-determinism mitigation**: Engineering controls to ensure consistency in regulated environment (generative AI inherently produces different outputs for same input)
- **Clear regulatory boundaries**: Agent cannot execute, only advise and surface insights

**Industry/Function**: Banking / Wealth

### Rocky (Experience Your Wealth RIA, 2026)
**Business Problem**: Scale advisory firm beyond founder while ensuring consistent delivery of founder's planning philosophy and approach. Traditional osmosis-based training (junior advisors sitting in meetings) became inefficient with AI notetakers, creating bottleneck where team constantly needed founder input.

**AI Pattern Applied**: RAG over proprietary firm content + conversational agent
- Claude integrated directly into CRM (Slant) with secure access to client database
- Private cloud environment for firm IP and knowledge base
- AI-generated SOP document trained on meeting notes, transcripts, and firm data
- Acts as "thinking partner" for team to answer planning scenario questions

**What Made It Work**:
- **Security-first approach**: Solved data security by choosing CRM (Slant) with native Claude integration + secure private cloud via CyberSecureRIA
- **Consolidation over complexity**: No data warehouse needed — centralizing all data in one CRM was sufficient for AI to work effectively
- **Training on authentic interactions**: Used actual internal firm meetings and client meeting transcripts to teach firm's approach
- **Judgment layer preserved**: Team trained to evaluate when to trust Rocky, when to push back, when to escalate to founder
- **Realistic expectations**: Rocky not expected to be perfect; acts as filter reducing (not eliminating) founder escalations

**What Made It Fail Initially**:
- First attempt using contractor on Upwork failed (scope/execution issue)
- Required outside technical help (CyberSecureRIA) to properly set up secure infrastructure

**Industry/Function**: Wealth Management / Advisory Operations & Training

**Firm Size**: 3-person RIA (demonstrates viability for small firms)

**Quantitative Outcomes**:
- Reduced frequency of team escalations to founder for planning questions
- Enabled team to "go deeper with each client" faster
- Supported growth without proportional hiring ("continue to grow without needing to hire additional team as rapidly")
- Specific metrics not disclosed

**Generalizability**:
- **Professional services scaling pattern**: Law firms, accounting firms, consulting practices where founder/partner expertise must be replicated across junior staff
- **Expert knowledge transfer**: Medical practices (attending physicians training residents), engineering firms (senior engineers mentoring juniors)
- **Regulated advisory contexts**: Insurance advisors, mortgage brokers, tax advisors — anywhere where consistent application of complex rules + firm philosophy is critical
- **Small team environments**: Pattern explicitly designed for solo/small teams (3-10 people) where training bottlenecks limit growth
- **High-touch service businesses**: Any business where personalized advice quality determines client retention and scaling requires replicating founder judgment