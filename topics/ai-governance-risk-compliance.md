---
tags: [adversarial-attacks, adversarial-prompting, agent-delegation, ai-constitutions, ai-delegates, ai-governance-risk-compliance, ai-integration, benchmark-evals, cybersecurity, democratic-governance, dual-use, frontier-models, institutional-design, jailbreak-prompting, jailbreaking, model-safety, offensive-capabilities, political-ai, political-superintelligence, red-teaming, rlhf, scaling-laws, startup-adoption, transparency-regime, white-box-black-box]
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
  - GPT-5.3 Codex and Opus 4.6 achieve 50% success on tasks taking human experts 3.1-3.2 hours ("roughly half a working day of professional offensive security work")
- **Open-weight diffusion risk**: GLM-5 lags closed-source frontier by only 5.7 months, suggesting "frontier offensive-cyber capability may diffuse into open-weight form on relatively short timelines"
- **Dual-use challenge**: Research highlights fundamental AI challenge as "

### Political AI and Agent Delegation (March 2026)
- **"Political superintelligence" concept (Andy Hall, Stanford)**: Proposes AI could enable "political superintelligence" - systems allowing "tools that help citizens, representatives, and institutions perceive reality more sharply, understand tradeoffs, contest power, and act more effectively"
  - Analogy: "AI is like the printing press... Instead of making information cheap and easily available, it makes intelligence cheap and easily available"
  - **Three-layer framework** for political superintelligence:
    1. **Information layer**: AI changes how governments access/understand data, identify problems, hear from citizens, distribute services. Requires better [[benchmark-evals]] for government-relevant information and purpose-built policy tools.
    2. **Representation layer**: AI agents as "tireless, automated delegates" that monitor politics, suggest votes, or serve as policymakers alongside human supervisors. Key risks: adversarial prompting of agents (politicians funding campaigns to sway agent beliefs), agent ownership conflicts (policy preferences vs. AI company interests).
    3. **Governance layer**: Challenge of private company ownership of political AI infrastructure. Requires mechanisms to govern model "constitutions" and effective oversight systems.
- **Agent reliability requirements**: Political agent deployment requires protection against adversarial prompting and resolution of principal-agent conflicts between users, agents, and operating companies
- **Transparency regime need**: Hall argues for regulations establishing transparency regime for AI systems involved in political/civic functions
- Note: This represents advocacy for governance structures rather than empirical findings about current capabilities

## Cross-References
- [[regulatory-policy]]
- [[lab-dynamics]]