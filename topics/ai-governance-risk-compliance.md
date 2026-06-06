---
tags: [activation-capping, adversarial-attacks, adversarial-prompting, agent-approval, agent-business-operations, agent-delegation, agent-employee-management, agentic-deception, agentic-operations, agentic-security, ai-constitutions, ai-delegates, ai-enabled-attacks, ai-governance, ai-governance-risk-compliance, ai-integration, ai-safety, ai-safety-testing, aml-kyc, andon-labs-governance, answer-layer, assistant-alignment, attack-lifecycle, attack-orchestration, autonomous-cyberattacks, b2b-marketing-maturity, benchmark-evals, cartel-formation, character-stability, chatgpt-security, code-security, code-vulnerability-scanning, compliance-automation, compliance-workflows, computer-use-agents, critical-infrastructure, critical-infrastructure-security, cybersecurity, dangerous-capability-evals, data-exfiltration, data-residency, deceptive-agent-behavior, defensive-ai, democratic-governance, document-processing, dual-use, economic-agent-risk, emergent-behavior, exfiltration-attacks, financial-services-ai, frontier-models, geo-playbook, governed-inference, governed-inference-portfolio, inference-costs, inference-governance, inference-location, institutional-design, jailbreak-prompting, jailbreaking, lateral-movement, layer-outputs, legal-compliance, legalbench, lethal-trifecta, llm-security, lockdown-mode, long-horizon-agent-risk, long-horizon-agents, malware-generation, microsoft-copilot, mitre-attack, model-openness, model-safety, multi-agent-systems, offensive-capabilities, open-weight-models, organizational-intelligence, organizational-intelligence-protection, patching-automation, persona-drift, physical-agent-deployment-risk, political-ai, political-superintelligence, post-compromise-techniques, pre-authenticated-links, price-manipulation, private-inference, prompt-injection, real-world-agent-governance, real-world-evals, red-teaming, refund-fraud, regulatory-compliance, regulatory-compliance-architecture, responsible-ai-deployment, responsible-deployment, risk-scoring, rlhf, scaling-laws, spending-authority]
---

# AI Governance, Risk & Compliance

## Data Exfiltration Defenses

### OpenAI Lockdown Mode (June 2026)
- **Status**: Rolled out to eligible personal accounts (Free, Go, Plus, Pro) and self-serve ChatGPT Business accounts
- **Purpose**: Prevent final stage of data exfiltration from [[prompt-injection]] attacks
- **Mechanism**: Limits outbound network requests that could transfer sensitive data to attackers
- **Design characteristic**: Uses deterministic mechanisms not evaluated by AI systems (avoiding AI-based defenses that can themselves be subverted)

**Scope limitations**:
- Does NOT prevent prompt injections from appearing in processed content
- Prompt injections can still appear in cached web content or uploaded files
- Does NOT prevent behavioral or accuracy effects from prompt injections
- Only targets the exfiltration stage of the attack lifecycle

**Implication**: ChatGPT's default settings (without Lockdown Mode) do not provide robust protection against determined data exfiltration attacks

### Lethal Trifecta Defense Strategy
The [[lethal-trifecta]] requires all three components:
1. Access to private data
2. Exposure to untrusted content  
3. Ability to exfiltrate data to attackers

**Mitigation approach**: Cutting off exfiltration vectors (leg #3) is the easiest restriction without significantly reducing LLM system usefulness. Lockdown Mode implements this strategy by attacking the exfiltration leg specifically.