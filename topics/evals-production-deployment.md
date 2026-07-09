---
tags: [adversarial-testing, agent-benchmarks, agent-personality-eval, agent-vulnerabilities, agentic-bug-finding, agentic-harness, agentic-workflows, agents-last-exam, ai-safety-evaluations, ai-security, arc-agi, arc-prize, automated-red-teaming, autonomous-agents, benchmark-design, benchmark-evaluation-methodology, benchmark-methodology, benchmark-replacement, bespoke-evaluation-interfaces, binary-reverse-engineering, biology-benchmarks, biosecurity, bug-finding-evals, capability-probing, capture-the-flag, catastrophic-risk, claude-3-7-sonnet, claude-sonnet-5, clear-pass-fail-signals, coding-agent-indices, coding-agents, coding-evals, composite-scoring, ctf-evals, custom-benchmarks, cybench, cyber-ranges, cybersecurity-agent-evaluation, cybersecurity-benchmarks, cybersecurity-capabilities, cybersecurity-evals, data-retention-constraints, deepswe, docker-sandboxing, domain-expert-red-teaming, dual-use-ai, dual-use-capabilities, economically-useful-tasks, evals-production-deployment, evaluation-methodology, evaluation-transparency, expert-vetted-benchmarks, exploit-generation, fallback-scoring, false-positive-detection, feature-implementation, feature-implementation-evals, first-solve-time, frontier-red-team, frontier-red-teaming, frozen-inputs, goal-loop-evals, goal-loop-pattern, gray-swan-arena, guardrails, gut-feel-scoring, human-in-the-loop, human-judgment, human-written-tests, humanitys-last-exam, incalmo, incident-diagnosis, information-security-protections, intelligence-indices, intercode-ctf, jailbreak-testing, jailbreaking, lateral-movement, llm-as-judge, llm-as-judge-limitations, llm-judge, llm-judge-prioritization, long-horizon-agentic-tasks, model-benchmarking, model-evaluation, model-fallback-evaluation, model-personality, model-routing, model-selection-strategy, multi-agent-orchestration, multi-language-evals, multi-stage-attacks, national-security, national-security-risk, national-security-risk-assessment, network-reconnaissance, personal-benchmarks, prd-evaluation, private-codebase-evals, production-deployment, program-replication, program-synthesis, program-synthesis-evals, prompt-filtering, prompt-injection, proprietary-benchmarks, red-teaming, threat-model-definition]
---

## Frontier Threats Red Teaming

**Definition**: Specialized adversarial testing focused on national security-relevant capabilities (biosecurity, cybersecurity) requiring intensive time investment and subject matter expertise.

### Resource Requirements
- **Expert time**: 100+ hours per domain with subject matter experts (decades of experience)
- **Anthropic biology case study**: 150+ hours with top biosecurity experts (July 2023)
- Close collaboration between domain experts and LLM experts required

### Methodology Components

**Threat Model Definition**: Structured analysis covering:
- What information types are dangerous
- How information combines to create harm
- Required accuracy and frequency thresholds for danger
- Multi-step information chaining requirements (not single harmful outputs)

**Capability Probing**: Domain experts learning to:
- Interact optimally with models
- Execute jailbreaks
- Assess true capabilities in target domain

**Evaluation Development**: Building automated, repeatable evaluations based on expert knowledge with supporting tooling infrastructure.

**Security Requirements**:
- Bespoke, secure interfaces without public deployment safeguards
- Partnerships with trusted third parties
- Strong information security protections for sensitive findings
- Findings shared selectively with government, labs, stakeholders

### Key Findings Pattern (Biology Domain)

**Current Capabilities**:
- Frontier models can produce sophisticated, accurate, expert-level knowledge
- Frequency varies by specific area studied
- Indication of capability scaling with model size
- Tool access likely to advance capabilities further

**Risk Assessment**: Unmitigated LLMs could:
- Accelerate bad actor efforts relative to internet-only access
- Enable tasks impossible without LLM assistance
- Effects characterized as "small today, but growing relatively fast"
- **Timeline**: Near-term risks (2-3 years from July 2023) if unmitigated
- However: mitigations exist to "substantially reduce these risks"

**Strategic Context**: Work creates baseline risk evaluation and repeatable methodology for scaling across multiple domains. See [[ai-governance-risk-compliance]] for policy framework and [[lab-dynamics]] for organizational commitments.