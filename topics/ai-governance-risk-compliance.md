---
tags: [agent-design-patterns, agent-governance, agentic-workflows, ai-governance, ai-governance-risk-compliance, artifact-scoping, automated-rollback, blast-radius-containment, credential-management, least-privilege, policy-as-code, production-controls, trust-boundaries]
---

---
tags: [agent-audit-trail, agent-authorization-layer, agent-clearinghouse, agent-execution-limits, agent-governance, agent-governance-architecture, agent-identity, agent-identity-standards, agent-liability, agent-policy-enforcement, agent-vulnerabilities, agentic-commerce, agentic-commerce-governance, agentic-orchestration, agentic-vulnerabilities, ai-governance-risk-compliance, ai-guardrails, ai-insurance, ai-security, alignment-verification, anthropic-research, artifact-scoped-governance, asset-classification, authorization-context, automated-adversarial-testing, automated-red-teaming, autonomous-agent-governance, behavioral-monitoring, cio-governance-priorities, clearinghouse-architecture, common-crawl, compliance-stack, content-classifiers, culturax, data-governance, deterministic-rules, dual-use-content-classification, enterprise-moats, error-blast-radius, explicit-accountability, export-controls, fraud-detection, frontier-model-forum, governance-as-competitive-advantage, governance-as-moat, governance-maturity, gray-swan-events, guardrails, hidden-reasoning-monitoring, human-in-the-loop, human-in-the-loop-governance, hybrid-governance, intent-verification, internal-state-monitoring, j-lens, j-space, jacobian-lens, language-specific-bias, liability-models, llm-for-compliance, llm-governance-tools, llm-transparency, mckinsey-ai-trust-survey, mechanistic-interpretability, misuse-classifier, misuse-detection, model-control, model-internals, model-transparency, multi-agent-governance, mythos-export-control, narrow-write-channels, national-security, national-security-ai, neuron-analysis, nnsa, nuclear-safeguards, output-channel-constraints, payment-governance, policy-as-code, policy-enforcement, stated-vs-actual-behavior, trust-boundaries, version-controlled-policy, action-boundary-governance, agent-credential-management, agent-retirement-policy, automated-rollback, headcount-rule, permission-creep-prevention, policy-and-provenance-graph, prompt-injection-defense, scif-model, tool-description-poisoning]---

## Model Transparency and Control

### I

## Production Agent Governance Architecture (K&L Gates Roundtable, June 2026)

**Problem statement:** "You've now just given yourself a virus with a credit card and no ability to shut it off." —Governance foundation leader on agents shipped without automated rollback

**Core diagnostic:** Build side raced ahead, governance trails behind. Agents act continuously at machine speed with authority that paper policies cannot reach. Underlying problems (least privilege, change control, observability) are not new—the acceleration is.

### Three Foundational Positions

1. **The model is the wrong target** — Risk lives where agent takes action, not in token generation
2. **The control belongs in code** — Policy enforcement must be structural, not prompt-based
3. **The engineering discipline already exists** — Apply existing software security practices

### The Headcount Rule (Strongest Consensus)

**Principle:** An agent should never hold more access than the person who authorized it.

**Failure mode:** Permission creep
- RFP detector becomes CRM writer
- Ticket-closer accumulates write authority no one approved  
- Coding agent rewrites 40% of repository after offhand approval

### Governance at Action Boundary

**Target location:** "As models cross the threshold from advisor to taking action, the spot between the model and the action is where you need the delegated authority. That's where your guardrail needs to live." —Veteran AI engineer and founder

**Why model-focused governance fails:** Model produces tokens; action costs customer records, CRM rewrites, wire transfers.

### Policy-as-Code Requirements

**Anti-pattern:** "A prompt that says 'don't do that' is not a control."

**Why human-readable governance fails:**
- Policy documents drift
- Human reviewers skim  
- Degradation when actor is machine acting thousands of times per hour

**Structural fix:**
- Policy enforced in code path
- Scoped tools
- Immutable policy-and-provenance graph (agent reads, never writes)
- Versioned policy traveling with code
- "We are used to saying 'yes, allow all, everything' to these agents. We used to assume the code had been tested. Now agents can break those boundaries easily." —Security executive

### Blast Radius Containment

**SCIF analogy:** Sealed enclave where sensitive work happens, nothing leaves until human inspection
- Read-only inputs
- Segregated outputs  
- Sandboxed execution

**Appliance model:** "I look at an agent much more like an appliance. My dishwasher does a job, in a certain way, and it only washes what's inside the dishwasher." —Governance architect

**Tool-level controls:**
- Scope to minimum required per use case
- Read widely, write narrowly
- Lock write authority to single artifact type, one action per run
- Default new agents to dry-run mode

### Identity Management Architecture

**Current anti-pattern:** Agents inherit personal access tokens by default

**Required practices:**
- Every agent gets own credentials
- Rotate credentials regularly
- Scan for credential exposure
- **Validation case:** Leader planted key deliberately, picked up within one day

**Lineage controls:**
- Child agents inherit equal or narrower scope  
- Every handoff intercepted and policy-checked
- Every agent gets named owner
- Every retirement pathway defined before owner leaves
- **Risk:** Orphaned agents = orphaned risk

### Infrastructure as Attack Surface

**Key insight:** "We're building this beautiful castle of identity and separation on top of infrastructure that already has big problems." —Startup CEO and former security executive

**Why model red-teaming is insufficient:** Breach lands in infrastructure layer—tools called, inputs read, retrieval indexes

**Prompt injection assumption:** Treat all untrusted input as hostile instruction
- Tickets, emails, support transcripts, web pages
- **Documented case:** Buried instruction at support-agent boundary triggered unauthorized password resets

**Expanded threat surface:**
- Tool descriptions (poisoning can turn well-behaved model into attacker's instrument)
- MCP servers (part of the agent)  
- Retrieval indexes (part of the agent)
- AI-generated code no one fully read

### Governance Maturity Gap

**Common failure:** Most governance programs stop at the agent, miss human failure modes in authorization

**Event type:** Senior AI leaders gathering (AI Realized + AiGovOps Foundation, June 17, 2026)
**Format:** Three tables, Chatham House Rule, no vendor pitches
**Tone:** Specific, technical, impatient with abstraction