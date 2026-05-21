---
tags: [wealth-management, conversational-ai, non-deterministic-outputs, runtime-personalization, regulatory-compliance, human-in-the-loop, ai-wealth-management-advisory]
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

**Industry/Function**: Banking / Wealth Management (high-net-worth client advisory)

**Quantitative Outcomes**: Not disclosed

**Key Insight**: "Wealth management is moving from a pull model to a presence model" — advice becomes background presence rather than scheduled event. This compresses advisors' surface area, shifting their role to "fewer but higher-stakes moments where judgment, context, and trust actually matter."

**Generalizability**:
- **High-stakes regulated advisory**: Legal, healthcare consulting, financial planning, tax advisory — anywhere non-deterministic AI must operate under strict compliance
- **Always-on expert augmentation**: Technical support, customer success, enterprise IT helpdesk — continuous availability with human escalation
- **Personalization via runtime data access**: Any domain requiring user-specific context without embedding PII in training (healthcare, education, government services)

## Cross-References
- [[rag-over-proprietary-content]]
- [[ai-in-legal-compliance]]
- [[ai-in-finance-accounting]]
- [[agentic-workflows-production]]