---
tags: [adversarial-attacks, adversarial-prompting, agent-approval, agent-delegation, agentic-operations, agentic-security, ai-constitutions, ai-delegates, ai-governance, ai-governance-risk-compliance, ai-integration, answer-layer, b2b-marketing-maturity, benchmark-evals, cybersecurity, data-exfiltration, data-residency, democratic-governance, dual-use, exfiltration-attacks, frontier-models, geo-playbook, governed-inference, governed-inference-portfolio, inference-costs, inference-governance, inference-location, institutional-design, jailbreak-prompting, jailbreaking, lethal-trifecta, microsoft-copilot, model-openness, model-safety, offensive-capabilities, open-weight-models, organizational-intelligence, organizational-intelligence-protection, political-ai, political-superintelligence, pre-authenticated-links, private-inference, prompt-injection, red-teaming, regulatory-compliance, regulatory-compliance-architecture, rlhf, scaling-laws, startup-adoption, transparency-regime, white-box-black-box]
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

### Offensive Cybersecurity Capabilities and Dual-Use Concerns (April 2026)
- **Scaling law for cyberoffense**: Lyptus Research found clear trend of more advanced models achieving better

### Data Exfiltration via Agentic Systems (May 2026)
- **Microsoft Copilot Cowork vulnerability (May 2026)**: Demonstrates persistent challenge in securing agentic systems against data exfiltration:
  - Agent was allowed to send emails to user's inbox without approval
  - Messages containing external images triggered network requests to attacker-controlled servers
  - OneDrive pre-authenticated download links could be exfiltrated via [[prompt-injection]]
  - When user opened compromised agent-sent message, embedded images leaked data through image load requests
  - **Key architectural flaw**: Lack of approval gates for agent-initiated communications combined with rendering of external resources
  - This represents a concrete instance of the "lethal trifecta" (agent permissions + prompt injection + data access)
  - Related to [[agentic-workflows-production]] security considerations