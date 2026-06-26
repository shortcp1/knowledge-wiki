---
tags: [agent-audit-trail, agent-authorization-layer, agent-clearinghouse, agent-execution-limits, agent-governance, agent-governance-architecture, agent-identity, agent-identity-standards, agent-liability, agent-policy-enforcement, agent-vulnerabilities, agentic-commerce, agentic-commerce-governance, agentic-orchestration, agentic-vulnerabilities, ai-governance-risk-compliance, ai-guardrails, ai-insurance, ai-security, asset-classification, authorization-context, automated-adversarial-testing, automated-red-teaming, autonomous-agent-governance, cio-governance-priorities, clearinghouse-architecture, common-crawl, compliance-stack, content-classifiers, culturax, data-governance, deterministic-rules, dual-use-content-classification, enterprise-moats, export-controls, fraud-detection, frontier-model-forum, governance-as-competitive-advantage, governance-as-moat, gray-swan-events, guardrails, human-in-the-loop, human-in-the-loop-governance, hybrid-governance, intent-verification, language-specific-bias, liability-models, llm-for-compliance, llm-governance-tools, misuse-classifier, misuse-detection, multi-agent-governance, mythos-export-control, national-security, national-security-ai, nnsa, nuclear-safeguards, payment-governance, policy-enforcement, privacy-aware-infrastructure, privacy-controls, prompt-injection, public-private-partnership, public-private-partnerships, red-teaming, responsible-ai, retention-policies, risk-signal-evolution, rule-distillation, state-media-bias, switching-costs, systems-of-record, training-data-composition, transaction-authorization]
---

# AI Governance, Risk & Compliance

## Agent Clearinghouse Governance Model (Ball, June 2026)

### Governance Paradigm Shift

**From Compliance Checkbox to Primary Concern**:
- Traditional: Governance was end-of-sales-cycle security review
- Emerging: CIOs prioritize governance from initial evaluation (meeting #1)
- Driver: Autonomous agents create direct operational and compliance risk

**New Enterprise Buying Questions**:
- Old: "Is the model good?" (capability-focused)
- New: "Can I see what every agent did, set policy on what it can touch, and prove it afterward?" (governance-focused)
- Assumption: All models are "good enough" - differentiation is c

## Privacy-Aware Infrastructure (Meta AI, June 2026)

### Core Challenge: Asset Classification at Scale

**Privacy Control Dependency**: Privacy controls (retention, access, allowed-purpose, downstream-sharing, anonymization) require reliable understanding of data before enforcement can operate.

**AI-Native Complexity Factors**:
- New data modalities (embeddings, multimodal inputs)
- Faster iteration cycles
- Derived features across pipeline transformations
- Changing policy interpretations
- Volume/pace exceeds manual review capacity

### PAI Four-Layer Stack (Dependency Pyramid)

1. **Understand**: Asset classification (foundation layer)
2. **Discover**: Identify policy-relevant data flows
3. **Enforce**: Apply retention/access/purpose/sharing constraints
4. **Demonstrate**: Provide verifiable compliance evidence

*Critical dependency*: Errors in classification layer propagate to all downstream controls.

### Asset Classification Scope

**Asset Types**:
- Tables, columns, nested payload fields
- Log keys, event parameters, API fields
- ML features, embeddings, derived datasets
- Data across pipeline transformations

**Ambiguity Example**: Field named "age" could be:
- Personal data (person's age) → strict protections required
- System metadata (cache TTL) → no privacy controls
- *Implication*: Field name alone insufficient for governance decisions

### Meta's Hybrid Classification Pattern

**Architecture Principle**: "LLMs are not the production decision-maker in common cases."

**Four-Component Approach**:

1. **Rich Context Assembly**: Gather distributed context (code, lineage, ownership, semantic annotations, documentation, usage patterns) before model reasoning

2. **LLM Role** (narrow and deliberate):
   - Handle ambiguity, cold start scenarios, novel assets
   - Generate recommendations (not production decisions)
   - Interpret ambiguous signals

3. **Human Review Layer**:
   - Human-reviewed labels kept separate from model-generated recommendations
   - Humans adjudicate reference labels
   - Humans review and approve rule promotions that change enforcement

4. **Rule Distillation**:
   - Extract stable behavior into deterministic, versioned rules
   - Rules handle routine enforcement (low latency, replayable, auditable)
   - LLM role shrinks over time as rule coverage expands

**Design Goal**: Learn from ambiguous signals while moving production enforcement toward deterministic logic.

### Four Recurring Classification Challenges

1. **Noisy/Weak Signals**:
   - Dozens of context fields per asset
   - High token usage dilutes attention
   - Decision boundaries buried in irrelevant/misleading fields
   - Example: "age" field without code resolution triggers false restrictions

2. **Distributed Context**:
   - Relevant context scattered across systems
   - Requires assembly before classification

3. **Evolving Requirements**:
   - Product teams iterate quickly
   - Policy interpretation changes with new capabilities
   - Static rules/periodic review leave gaps

4. **Enforcement Consequences**:
   - False positive → unnecessary downstream restrictions
   - False negative → protection gaps
   - Classifier sits early in enforcement pipeline (error amplification risk)

### Cross-References

- [[ai-engineering-agents]]: Asset classification for AI-generated features/embeddings
- [[ai-native-product-design]]: Fast iteration cycles impact governance systems