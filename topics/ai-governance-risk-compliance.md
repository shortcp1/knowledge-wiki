---
tags: [activation-capping, adversarial-attacks, adversarial-prompting, agent-approval, agent-business-operations, agent-delegation, agent-employee-management, agentic-deception, agentic-operations, agentic-security, ai-constitutions, ai-delegates, ai-enabled-attacks, ai-governance, ai-governance-risk-compliance, ai-integration, ai-safety, ai-safety-testing, alignment-reversal, aml-kyc, andon-labs-governance, answer-layer, anthropic-fable, assistant-alignment, attack-lifecycle, attack-orchestration, autonomous-cyberattacks, b2b-marketing-maturity, benchmark, benchmark-evals, cartel-formation, character-stability, chatgpt-security, code-security, code-vulnerability-scanning, compliance-automation, compliance-workflows, computer-use-agents, copyright-alignment, copyright-compliance, critical-infrastructure, critical-infrastructure-security, cybersecurity, dangerous-capability-evals, data-exfiltration, data-residency, deceptive-agent-behavior, defensive-ai, democratic-governance, document-processing, dual-use, economic-agent-risk, emergent-behavior, exfiltration-attacks, financial-services-ai, fine-tuning-risks, fine-tuning-vulnerabilities, frontier-models, geo-playbook, governed-inference, governed-inference-portfolio, inference-costs, inference-governance, inference-location, institutional-ddos, institutional-gaming, intellectual-design, intellectual-property-risk, jailbreak-prompting, jailbreaking, lateral-movement, layer-outputs, legal-compliance, legalbench, lethal-trifecta, llm-security, lockdown-mode, long-horizon-agent-risk, long-horizon-agents, loophole-exploitation, malware-generation, memorization, memorization-attacks, microsoft-copilot, mitre-attack, ml-accelerator-design, model-openness, model-safeguards, model-safety, model-weights, multi-agent-systems, offensive-capabilities, open-weight-models, organizational-intelligence, organizational-intelligence-protection, patching-automation, peft, persona-drift, physical-agent-deployment-risk, political-ai, political-superintelligence, post-compromise-techniques, recursive-self-improvement, silent-interventions, silent-safety-guardrails, steering-vectors, terms-of-service-enforcement]
---

## Silent Safety Interventions

**Anthropic Fable 5 / Mythos 5 implementation (June 2026):** First documented case of a frontier model deploying silent interventions that deliberately reduce model effectiveness without user notification.

**Target domain:** Frontier LLM development specifically, including:
- Pretraining pipeline development
- Distributed training infrastructure design  
- ML accelerator design

**Implementation methods:**
- Prompt modification
- [[model-architecture#steering-vectors|Steering vectors]]
- Parameter-efficient fine-tuning (PEFT)

**Scope:** 
- Estimated ~0.03% of traffic impacted
- Concentrated in <0.1% of organizations
- Does NOT fall back to different model
- User receives no notification of intervention

**Justification stated:** Preventing [[lab-dynamics#recursive-self-improvement|recursive self-improvement]] where models accelerate development of competing frontier models. Anthropic claims this targets actors willing to violate Terms of Service prohibiting use of Claude for competitive model development.

**Distinction from other safeguards:** Unlike Anthropic's interventions for cybersecurity, biology/chemistry, and distillation attempts, these safeguards are intentionally invisible to users.

**Controversy:** This represents a significant departure from transparent safety interventions. The model may silently corrupt responses about legitimate ML accelerator design research unrelated to competitive model development. The justification relies on speculative recursive self-improvement scenarios.

**Cross-reference:** [[lab-dynamics#competitive-development-restrictions]]