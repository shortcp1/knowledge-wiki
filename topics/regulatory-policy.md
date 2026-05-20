---
tags: [adversarial-prompting, ai-constitutions, ai-delegates, ai-safety-benchmarks, capability-gap, claude-mythos, cybersecurity-risk, democratic-governance, export-controls, institutional-design, model-approval-process, model-release-policy, national-security-ai, nist-evaluation, open-closed-debate, open-weight-models, political-superintelligence, pre-deployment-testing, pre-release-evaluation, regulatory-policy, trains, trains-task-force]
---

# Regulatory & Policy Landscape

Covers AI regulation and policy developments: EU AI Act implementation, US executive orders and congressional activity, state-level legislation (California, Texas), sector-specific rules (financial services, healthcare), and international coordination frameworks.

Key questions tracked: What is the EU AI Act compliance timeline for different system categories? How are US federal agencies approaching AI governance in their domains? Where are the most consequential pending regulatory decisions?

## Key Claims
<!-- agent-maintained -->

### U.S. Pre-Release Model Evaluation (May 2026)
- **TRAINS program**: Testing Risks of AI for National Security (TRAINS), a multi-agency task force overseen by NIST's Center for AI Standards and Innovation (CAISI), will assess national-security risks posed by AI models prior to deployment
  - **Focus areas**: Cybersecurity, biosecurity, and chemical weapons risks
  - **Participating agencies**: Departments of Commerce, Defense, Energy, and Homeland Security; National Security Administration; National Institutes of Health
  - **Distinguishing features**: Designed for rapid response; draws on multiple federal agencies (unlike other disclosed NIST groups)
  - **Voluntary agreements**: Google, Microsoft, and xAI agreed to provide models with "limited or absent guardrails"; Anthropic and OpenAI had agreed to similar terms in 2024
  - **Purpose**: Enable collaborative private-public research into capabilities and risks evaluation, as well as risk mitigation
  - **Benchmark disclosure**: TRAINS has not disclosed which benchmarks it intends to use for evaluation
  - See [[evals-production-deployment]] for CAISI benchmark methodology
  - See [[ai-governance-risk-compliance]] for related security evaluation frameworks

- **Pending executive order**: White House is considering an executive order that would require AI models to gain approval before deployment (as of May 2026)
  - Note: Details of controls or approval criteria not yet disclosed
  - Would represent shift from voluntary to mandatory pre-release testing

- **Policy reversal context**: Trump Administration shifted from laissez-faire approach to pre-release scrutiny following Claude Mythos Preview announcement (April 2026)
  - January 2025: Trump Administration assigned advisors to craft AI Action Plan focused on "sustaining and enhancing America's global AI dominance" by suspending/eliminating Biden-era regulatory policies
  - Biden Administration (2023): Executive order required developers to notify government when training models with processing requirements corresponding to ~1 trillion parameters
  - March 2026: White House rejected Anthropic's attempt to limit military use of Claude for surveillance and autonomous weapons; banned Claude from military use entirely
  - April 2026: Anthropic announced Claude Mythos Preview could autonomously exploit vulnerabilities in major operating systems and applications
  - May 2026: White House opposed Anthropic's plan to expand Mythos preview from 50 to 120 organizations, citing national security concerns and questions about Anthropic's computational capacity
  - **Open question**: Whether Anthropic will challenge administration's authority to limit preview model distribution (company has not stated position as of May 2026)

### Proposed Regulatory Frameworks (March 2026)
- **Transparency regime for political AI (Andy Hall proposal)**: Stanford political economy researcher advocates for regulations establishing transparency requirements for AI systems used in civic/political contexts
  - Context: Response to "political superintelligence" concept - AI systems that help citizens/representatives/institutions understand policy, contest power, and act effectively
  - Governance challenges identified:
    - Private company control of political AI infrastructure
    - Need for public oversight of model "constitutions" (company-created rules governing model behavior)
    - Protection against adversarial manipulation of AI agents acting as citizen delegates
  - Note: This is academic/policy advocacy rather than pending legislation
  - See [[ai-governance-risk-compliance]] for technical governance requirements

### Open-Weight Model Policy Debate (April 2026)
- **Cybersecurity-focused restrictions**: Claude Mythos release (April 2026) triggered renewed calls for restricting open-weight AI model releases
  - **Argument for restriction**: Digital i