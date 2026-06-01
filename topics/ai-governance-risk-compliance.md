---
tags: [adversarial-attacks, adversarial-prompting, agent-approval, agent-delegation, agentic-operations, agentic-security, ai-constitutions, ai-delegates, ai-governance, ai-governance-risk-compliance, ai-integration, aml-kyc, answer-layer, b2b-marketing-maturity, benchmark-evals, compliance-automation, compliance-workflows, computer-use-agents, cybersecurity, data-exfiltration, data-residency, democratic-governance, document-processing, dual-use, exfiltration-attacks, financial-services-ai, frontier-models, geo-playbook, governed-inference, governed-inference-portfolio, inference-costs, inference-governance, inference-location, institutional-design, jailbreak-prompting, jailbreaking, legal-compliance, legalbench, lethal-trifecta, microsoft-copilot, model-openness, model-safety, offensive-capabilities, open-weight-models, organizational-intelligence, organizational-intelligence-protection, political-ai, political-superintelligence, pre-authenticated-links, private-inference, prompt-injection, red-teaming, regulatory-compliance, regulatory-compliance-architecture, rlhf, scaling-laws, startup-adoption, transparency-regime, vision-language-models, vlm, white-box-black-box]
---

# AI Governance, Risk & Compliance

Covers enterprise AI policy frameworks, AI risk management (model auditing, bias testing, explainability), compliance requirements (EU AI Act, state laws, sector-specific rules), and the emerging role of AI governance functions in large organizations.

Key questions tracked: What does the EU AI Act require of different risk-tier systems? How are enterprises structuring AI governance committees? What are the liability exposure points for AI-assisted decisions?

## Key Claims
<!-- agent-maintained -->

### Code Execution Security
- **Sandboxing for Code-Generating Agents (OpenAI Codex, May 2026)**: Production deployment of code-generating agents like Codex requires sandbox architectures with:
  - Controlled file access permissions
  - Network restriction capabilities
  - Isolated execution environments
  - This establishes a security baseline for agents that generate and execute code on user systems.

### Compliance Automation Patterns
- **Trust Threshold Economics (a16z, May 2026)**: In compliance applications, "sometimes the market for something done very well is 100x the market for something done just okay"
  - "90% correct product is still 100% wrong" in compliance contexts
  - Technology must cross from "good enough to pilot" to "good enough to trust" before enterprises will deploy
  - Example: VLMs vs OCR for document processing - incremental improvement insufficient; threshold crossing drives adoption
  - Business impact: Mortgage underwriting, business onboarding, insurance claims review shifted from manual to automated only after accuracy threshold crossed

### AI Pattern: Computer Use Agents for Legacy Systems
- **Legacy System Navigation (a16z, May 2026)**: Computer use agents can navigate legacy software "the way a human would, without waiting for an API or a six-month integration project"
  - Addresses major compliance deployment barrier: integration with legacy systems
  - Enables compliance automation without modernizing underlying infrastructure
  - Generalizability: Applicable to any industry with legacy systems requiring compliance oversight (healthcare, manufacturing, energy, transportation)

### Compliance Market Context
- **Regulatory Burden Growth (a16z, May 2026)**: Title 12 CFR (Banks and Banking) added more restrictions 2010-2014 than entire title contained in 1980
  - Traditional response: "throw more people at the problem"
  - Result: TD Bank $3B fine (2024) for failing to monitor 92% of transactions with 70,000 alert backlog from 2018
  - Pattern repeated across major financial institutions with "ballooning teams and growing backlogs"
  - Demonstrates human-scaling approach failure, creating opportunity for AI automation

### Offensive Cybersecurity Capa

## Cross-References
- [[ai-in-legal-compliance]]
- [[build-vs-buy-enterprise-ai]]