---
tags: [adversarial-attacks, adversarial-prompting, agent-delegation, agentic-operations, ai-constitutions, ai-delegates, ai-governance, ai-governance-risk-compliance, ai-integration, answer-layer, b2b-marketing-maturity, benchmark-evals, cybersecurity, data-residency, democratic-governance, dual-use, frontier-models, geo-playbook, governed-inference, governed-inference-portfolio, inference-costs, inference-governance, inference-location, institutional-design, jailbreak-prompting, jailbreaking, model-openness, model-safety, offensive-capabilities, open-weight-models, organizational-intelligence, organizational-intelligence-protection, political-ai, political-superintelligence, private-inference, red-teaming, regulatory-compliance, regulatory-compliance-architecture, rlhf, scaling-laws, startup-adoption, transparency-regime, white-box-black-box]
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
- **Scaling law for cyberoffense**: Lyptus Research found clear trend of more advanced models achieving better cyberattack capabilities
  - Capability doubling time: 9.8 months across frontier models since 2019; 5.7 months for models since 2024
  - GPT-5.3 Codex and Opus 4.6 achieve 50% success on tasks taking h

### Regulatory Constraints on Inference Architecture (May 2026)
- **Compliance-driven inference location requirements**: Multiple regulatory frameworks create hard constraints (not preferences) on data movement and processing:
  - **EU AI Act**: High-risk categories impose specific requirements
  - **HIPAA (U.S. Healthcare)**: Restricts PHI processing and location
  - **GLBA (Financial Services)**: Sectoral exam requirements for financial data
  - **GDPR**: Data-processor obligations and data residency requirements
  - **Architectural implication**: Inference architecture must meet auditability and data sovereignty requirements by design
  - **Risk-tiered approach**: Regulation sharpens both model openness and inference location decisions independently

### Sensitive Data Exposure Through Inference (May 2026)
- **Inference input scope in enterprise systems**: Every inference operation potentially exposes multiple sensitive data types:
  - Technical: Prompts, retrieved documents, embeddings, source code, agent traces, workflow logs, tool calls
  - Business: Customer records, product data, support histories
  - **Risk assessment**: Each element can expose sensitive information, requiring workload-by-workload evaluation
  - **Industry-specific examples of protected organizational intelligence**:
    - Manufacturing: Process-improvement data, plant telemetry, defect patterns, supplier bottlenecks, product tolerances
    - Banking: Underwriting logic, compliance workflows, transaction patterns, risk models
    - Pharma: Molecule data, clinical trial signals, regulatory strategy, research hypotheses