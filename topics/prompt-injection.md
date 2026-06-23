---
tags: [adversarial-red-teaming, agent-security, agent-vulnerabilities, agentic-vulnerabilities, ai-guardrails, ai-security, alien-intelligence, automated-adversarial-testing, automated-red-teaming, capability-elicitation, claude-code, codex-security, computer-use-agents, cygnal, eval-awareness, exfiltration-risks, gray-swan, gray-swan-arena, guardrails, indirect-prompt-injection, jailbreaks, lethal-trifecta, model-robustness, mythos-export-control, openclaw, private-data-access, prompt-injection, red-teaming, shade, simon-willison, untrusted-data]
---

# Prompt Injection

## Definitive Research (Kolter & Fredrikson)

**Authors**: Zico Kolter (OpenAI board member, Safety & Security Committee) and Matt Fredrikson (CMU professor, Gray Swan CEO)

**Key Contribution**: Co-authored definitive paper on Indirect Prompt Injections
- Industry term for class of vulnerabilities where external/untrusted inputs manipulate model behavior
- Distinct from direct jailbreaks (user attempting to break their own session)

## The Lethal Trifecta (Simon Willison)

**Three Conditions for Critical Risk**:
1. **Untrusted Data**: Agent processes external/user-generated content
2. **Private Data**: Agent has access to confidential information
3. **Exfiltration**: Agent can send data outside the system

**When Combined**: Creates exploitable vulnerability for data theft via prompt injection

**Industry Recognition**: Framework cited by [[ai-security-red-teaming]] practitioners and referenced by Gray Swan security toolkit

## Why AI Security Differs from Traditional Cybersecurity

**Key Insight** (Kolter & Fredrikson, June 2026): AI security requires fundamentally different mindset from traditional software security

**Reasons**:
- LLMs are "alien form of intelligence" that fail differently from humans
- Vulnerability surfaces not limited to code bugs or configuration errors
- Exploits can be embedded in natural language inputs
- Agent behavior can be manipulated through semantic attacks

**Implication**: "Cybersecurity with AI" approaches miss the unique threat model of AI systems

## Prompt Injection as New Exploit Class

**Target Systems**: Agentic AI systems like Codex, Claude Code, [[computer-use-agents]]

**Attack Vector**: Malicious instructions embedded in:
- Documents the agent processes
- Web pages the agent visits
- Emails/messages the agent reads
- Any external content fed to the model

**Exploit Mechanism**: Model cannot reliably distinguish between:
- Legitimate system instructions from developer
- Malicious instructions from untrusted input
- User intent vs. embedded adversarial prompts

**Severity**: US Government issued export control directive on Mythos and Fable models specifically due to jailbreak and prompt injection risks (June 2026)

## Gray Swan Arena

**Platform**: World's largest AI Red Teaming Arena

**Purpose**: Community red teaming and adversarial testing

**Notable Participants**: AIRT celebrity Wyatt Walls among contributors

**Function**: Crowdsourced discovery of prompt injection vulnerabilities and jailbreaks

## Shade: Automated Red Teaming Tool

**Developer**: Gray Swan

**Capability**: Adversarial red teaming tool that "can outperform humans at breaking models"

**Key Finding**: Specialized red-teaming models now beat humans at breaking AI systems

**Validation**: Used by Anthropic to evaluate robustness of their models against prompt injection attacks in coding environments

**Technical Approach**: AI systems attacking other AI systems
- Automated adversarial prompt generation
- Systematic exploration of vulnerability space
- Surpasses human creativity in finding exploits

## Model Robustness Findings

### Humans vs. Browser-Agent Performance

**Surprising Result**: In robustness testing, "humans ranked fourth"
- Browser-use agents demonstrated different vulnerability profile than human users
- Agents fail in ways humans don't, and vice versa

**Implication**: Cannot assume human-safe interfaces are agent-safe
- Need dedicated [[agent-security]] testing
- [[agentic-workflows-production]] requires separate security analysis

### Scaling Does Not Guarantee Robustness

**Critical Finding** (Kolter & Fredrikson, June 2026): "Bigger models do not automatically become more robust"

**Evidence**:
- Frontier models are not automatically safer as they scale
- Capability scaling and security hardening are separate dimensions
- Size/intelligence does not correlate with injection resistance

**Contradiction to Common Assumption**: Industry assumption that more capable models would naturally be harder to exploit is not supported by testing data

## Red Teaming vs. Jailbreaks vs. Capability Elicitation

**Red Teaming**: Structured adversarial testing to find vulnerabilities
- Systematic approach to security validation
- Can be automated (e.g., Shade) or human-driven (e.g., Gray Swan Arena)

**Jailbreaks**: Attempts to bypass safety guardrails or alignment
- Often focuses on getting model to produce prohibited content
- Subset of broader red teaming practice

**Capability Elicitation**: Testing what models can do when properly prompted
- Not adversarial - seeks to surface latent capabilities
- Important for understanding true risk surface
- Relevant for [[evals-production-deployment]] and safety assessment

**Eval Awareness**: Models may perform differently when they detect they're being evaluated
- Complicates capability assessment
- Requires sophisticated testing methodology

## Computer-Use Agents and Security Nightmare

### OpenClaw

**Technology**: Computer-use agents that can control desktop/browser interfaces

**Security Challenge**: Dramatically expands attack surface
- Can execute arbitrary actions in user environment
- Access to all user data and applications
- Prompt injection can lead to arbitrary command execution

**Expert Assessment** (Kolter & Fredrikson): "The agent security nightmare"
- Combines [[lethal-trifecta]] with broad system access
- Traditional sandboxing insufficient for semantic attacks
- No clear path to secure deployment at current capability levels

## Enterprise Deployment Challenges

**Current State**: "Just prompt it better" is not enough for enterprise AI security

**Requirements for Production**:
- [[agent-identity]] standards
- Permission systems (see [[agentic-workflows-production]])
- [[guardrails]] like Cygnal for policy enforcement
- Audit trails and monitoring
- Programmatic controls, not prompt-based security

**Gray Swan Event**: First major AI prompt-injection breach may be inevitable
- Security experts can see it coming
- Gray swan: unlikely but clearly visible before it happens
- Industry preparing for incident, not if but when

## Cross-References

- [[ai-governance-risk-compliance]]: Guardrails, compliance, and insurance implications
- [[agentic-workflows-production]]: Agent clearinghouse and governance patterns
- [[ai-security-red-teaming]]: Methodologies and tools
- [[evals-production-deployment]]: Capability assessment and safety testing