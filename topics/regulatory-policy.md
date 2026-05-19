---
tags: [adversarial-prompting, ai-constitutions, ai-delegates, capability-gap, claude-mythos, cybersecurity-risk, democratic-governance, export-controls, institutional-design, model-release-policy, open-closed-debate, open-weight-models, political-superintelligence, regulatory-policy]
---

# Regulatory & Policy Landscape

Covers AI regulation and policy developments: EU AI Act implementation, US executive orders and congressional activity, state-level legislation (California, Texas), sector-specific rules (financial services, healthcare), and international coordination frameworks.

Key questions tracked: What is the EU AI Act compliance timeline for different system categories? How are US federal agencies approaching AI governance in their domains? Where are the most consequential pending regulatory decisions?

## Key Claims
<!-- agent-maintained -->

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
  - **Argument for restriction**: Digital infrastructure not ready for open-weight models with advanced cybersecurity capabilities; could enable widespread attacks
  - **Counter-argument**: Policy recommendation "conflates too many general unknowns" and "could actually further weaken cybersecurity readiness" (Lambert, April 2026)
  - **Historical context**: Similar restriction arguments made for GPT-2 (2019) and GPT-4 (2023) did not materialize as predicted
- **Three-component deployment risk**: Building capability-equivalent open system requires: (1) training and releasing weights, (2) effective tool harness, (3) inference compute and software
  - Note: Risk assessment depends on all three components, not just model weights alone
- **Domain-specific vs. general capability distinction**: Cybersecurity capabilities may be easier to replicate in open-weight models than general agentic capabilities due to availability of public training data (e.g., GitHub)
  - Contrast with domains like medicine, law, knowledge work where data availability more limited

## Cross-References
- [[ai-governance-risk-compliance]]
- [[lab-dynamics]]
- [[cybersecurity-ai]]