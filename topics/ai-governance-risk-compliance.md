---
tags: [activation-capping, adversarial-attacks, adversarial-prompting, agent-approval, agent-delegation, agentic-operations, agentic-security, ai-constitutions, ai-delegates, ai-governance, ai-governance-risk-compliance, ai-integration, ai-safety, aml-kyc, answer-layer, assistant-alignment, b2b-marketing-maturity, benchmark-evals, character-stability, code-security, code-vulnerability-scanning, compliance-automation, compliance-workflows, computer-use-agents, critical-infrastructure, critical-infrastructure-security, cybersecurity, data-exfiltration, data-residency, defensive-ai, democratic-governance, document-processing, dual-use, exfiltration-attacks, financial-services-ai, frontier-models, geo-playbook, governed-inference, governed-inference-portfolio, inference-costs, inference-governance, inference-location, institutional-design, jailbreak-prompting, jailbreaking, layer-outputs, legal-compliance, legalbench, lethal-trifecta, microsoft-copilot, model-openness, model-safety, offensive-capabilities, open-weight-models, organizational-intelligence, organizational-intelligence-protection, patching-automation, persona-drift, political-ai, political-superintelligence, pre-authenticated-links, private-inference, prompt-injection, red-teaming, regulatory-compliance, regulatory-compliance-architecture, responsible-ai-deployment, responsible-deployment, rlhf, scaling-laws, startup-adoption, transparency-regime, vision-language-models, vlm, vulnerability-scanning, white-box-black-box]
---

# AI Governance, Risk & Compliance

Covers enterprise AI policy frameworks, AI risk management (model auditing, bias testing, explainability), compliance requirements (EU AI Act, state laws, sector-specific rules), and the emerging role of AI governance functions in large organizations.

Key questions tracked: What does the EU AI Act require of different risk-tier systems? How are enterprises structuring AI governance committees? What are the liability exposure points for AI-assisted decisions?

## Key Claims
<!-- agent-maintained -->

### Code Execution Security
- **Sandboxing for Code-Generating Agents (OpenAI Codex, May 2026)**: Production deployment of code-generating agents like Codex r

### Cybersecurity Vulnerability Detection at Scale
- **Project Glasswing (Anthropic, April-June 2026)**: Controlled deployment of Claude Mythos Preview to critical infrastructure organizations for automated vulnerability scanning
  - **Business Problem**: Software vulnerabilities in critical infrastructure pose catastrophic risk; traditional manual code review cannot scale to match attack surface
  - **AI Pattern Applied**: Specialized frontier model (Claude Mythos Preview) for code vulnerability detection, plus supplementary product (Claude Security using Opus 4.8) for broader deployment
  - **Industry/Function**: Critical infrastructure across power, water, healthcare, communications, hardware, software vendors; cybersecurity function
  - **Scale**: ~200 organizations across 15+ countries, each serving 100M+ people
  - **Quantitative Outcomes**: 10,000+ high- or critical-severity vulnerabilities discovered in first weeks by initial 50 partners
  - **Success Factors**:
    - Gated access model with security requirements for partners before model access
    - Multi-week collaboration with security industry, open-source maintainers, and US government before expansion
    - Focus on organizations where attacks would be "catastrophic" with global/national security implications
    - Provided tooling to help partners triage findings at scale
    - Expanded use cases beyond detection: patch writing, pre-release vulnerability checks, penetration testing, threat detection/response automation
  - **Bottleneck Identified**: Verification, disclosure, and patching of vulnerabilities now rate-limiting factor rather than discovery
  - **Generalizability**: Pattern applies to any domain where:
    - Code quality/security is critical at scale (financial services, defense, telecom)
    - Manual review cannot keep pace with codebase size
    - Automated detection generates high volumes requiring triage infrastructure
    - Responsible disclosure and coordination mechanisms exist
  - **Governance Approach**: Tiered rollout (50 initial, then ~150), security vetting before access, collaboration with government/industry before expansion
  - **Market Dynamics Context**: Anthropic expects "within 6 to 12 months" many AI companies will have Mythos-class models, potentially "without safeguards that prevent misuse"—driving urgency for defensive adaptation
  - **Future Direction**: Shift from pure vulnerability discovery toward disclosure, patching, deployment of fixes; industry-wide standards and infrastructure development for "era of powerful cyber models"