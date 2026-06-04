---
tags: [activation-capping, adversarial-attacks, adversarial-prompting, agent-approval, agent-delegation, agentic-operations, agentic-security, ai-constitutions, ai-delegates, ai-enabled-attacks, ai-governance, ai-governance-risk-compliance, ai-integration, ai-safety, aml-kyc, answer-layer, assistant-alignment, attack-lifecycle, attack-orchestration, autonomous-cyberattacks, b2b-marketing-maturity, benchmark-evals, character-stability, code-security, code-vulnerability-scanning, compliance-automation, compliance-workflows, computer-use-agents, critical-infrastructure, critical-infrastructure-security, cybersecurity, data-exfiltration, data-residency, defensive-ai, democratic-governance, document-processing, dual-use, exfiltration-attacks, financial-services-ai, frontier-models, geo-playbook, governed-inference, governed-inference-portfolio, inference-costs, inference-governance, inference-location, institutional-design, jailbreak-prompting, jailbreaking, lateral-movement, layer-outputs, legal-compliance, legalbench, lethal-trifecta, malware-generation, microsoft-copilot, mitre-attack, model-openness, model-safety, offensive-capabilities, open-weight-models, organizational-intelligence, organizational-intelligence-protection, patching-automation, persona-drift, political-ai, political-superintelligence, post-compromise-techniques, pre-authenticated-links, private-inference, prompt-injection, red-teaming, regulatory-compliance, regulatory-compliance-architecture, responsible-ai-deployment, responsible-deployment, risk-scoring, rlhf, scaling-laws, startup-adoption, threat-actor-classification, threat-detection, transparency-regime, vision-language-models, vlm, vulnerability-scanning, white-box-black-box]
---

# AI Governance, Risk & Compliance

Covers enterprise AI policy frameworks, AI risk management (model auditing, bias testing, explainability), compliance requirements (EU AI Act, state laws, sector-specific rules), and the emerging role of AI governance functions in large organizations.

Key questions tracked: What does the EU AI Act require of different risk-tier systems? How are enterprises structuring AI governance committees? What are the liability exposure points for AI-assisted operations?

## AI-Enabled Cyber Threats
<!-- agent-maintained -->

### Empirical Data on Malicious AI Use (March 2025 - March 2026)
- **Source**: Anthropic Frontier Red Team analysis of 832 accounts banned for malicious cyber activity, mapped to [[mitre-attack]] framework
- **Note**: These 832 cases represent a subset with sufficient detail for thorough assessment, not the total number of banned accounts
- **Publication**: Results partially published in Verizon's 2026 Data Breach Investigations Report (DBIR)

### Key Findings on AI-Enabled Attack Patterns

#### 1. AI Use in Attack Lifecycle
- **Malware writing**: 560/832 accounts (67.3%) used AI for this purpose—the most common application
- **Post-compromise techniques**: Smaller but significant adoption:
  - Lateral movement assistance: 54/832 accounts (6.5%)
  - Account discovery (identifying valid accounts inside compromised environments): rising 8.9% over study period
  - Privilege escalation: increasingly AI-assisted
- **Trend**: Shift from initial access techniques (e.g., AI-assisted phishing fell 8.6%) toward deeper attack lifecycle stages
- **Significance**: Post-compromise techniques previously required high technical knowledge; AI now enables less sophisticated actors to perform these activities

#### 2. Escalation in Threat Actor Risk Levels
- **Risk score increase**: Actors classified as medium-risk or higher jumped from 33% (first six months) to 56% (second six months)—approximately 1.7-fold increase
- **Interpretation**: Evidence consistent with AI enabling attackers to increase their threat level

#### 3. Autonomous Attack Capabilities
- **Attack chaining**: AI can link together multiple discrete stages of cyberattacks
- **Minimal human input**: Higher-risk actors design scaffolding/architectures allowing models to orchestrate attack steps with reduced supervision
- **Operational autonomy**: AI performs "operationally demanding" techniques requiring significant time, oversight, or real-time decision-making

### Breakdown of Traditional Risk Assessment Signals

#### Signals That No Longer Correlate with Risk Level:
- **Number of techniques employed**: Least-skilled actors averaged ~16 distinct techniques; most skilled averaged ~20 (minimal difference)
- **Platform/interface used**: Claude Code, API access, or chat interface did not correlate with actor risk level

#### Signals That Still Indicate Higher Risk (but eroding):
- **Attack lifecycle positioning**: Where in the lifecycle AI is applied matters—concentration on operationally demanding post-compromise techniques vs. initial access
- **Caveat**: This signal is "already eroding" as broader actor population adopts these techniques and more actors classified as higher risk

#### More Durable Risk Indicator:
- **Model scaffolding architecture**: Design of systems that allow models to autonomously chain together attack stages distinguishes highest-risk actors

### Implications for Security Frameworks
- **MITRE ATT&CK limitations**: Framework "does not fully capture the tools and activities that make AI-enabled attackers so dangerous"
- **Challenge**: Behaviors distinguishing highest-risk actors (AI orchestration, autonomous chaining of attack steps) not adequately represented in existing taxonomies
- **Need**: Security frameworks require updating to account for AI-specific threat vectors

See also: [[regulatory-policy]] for governance responses, [[cybersecurity]] for defensive measures