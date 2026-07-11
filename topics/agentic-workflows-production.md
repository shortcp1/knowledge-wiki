---
tags: [agent-design-patterns, agent-governance, agentic-workflows, agentic-workflows-production, ai-brand-discoverability, ai-citation-sources, ai-governance, artifact-scoped-agents, artifact-scoping, automated-rollback, blast-radius, blast-radius-containment, credential-management, generative-engine-optimization, geo-optimization, human-in-the-loop, least-privilege, policy-as-code, policy-enforcement, production-controls, tool-boundary-enforcement, trust-boundaries]
---

---
tags: [adversarial-review, agent-experience, agent-memory-architecture, agent-orchestration, agent-runtime, agent-sandboxes, agentic-systems, agentic-workflows, agentic-workflows-production, ai-evolution, artifact-scoped-agents, asynchronous-inference, automated-refactoring, autonomous-agents, autonomous-replication, bounded-outputs, bursty-workloads, code-generation, context-engineering, decision-records, deterministic-rewriting, digital-darwinism, digital-evolution, elastic-compute, elastic-inference, evolutionary-ai, evolutionary-search, goal-oriented-loops, gpu-snapshotting, harness-engineering, institutional-memory, lamarckian-inheritance, linear-integration, local-model-routing, memory-architecture, model-merging, multi-cloud-capacity, narrow-write-channels, openai-symphony, overnight-processing, policy-as-code, population-dynamics, preflight-checks, preflight-retrieval, programmatic-infrastructure, read-widely-write-narrowly, recursive-self-improvement, rl-rollouts, rust-migration, sandbox-environments, self-improving-agents, self-improving-systems, self-modification, self-replication, serverless-functions, serverless-gpu, skills-library, test-driven-agents, version-controlled-policy, watchdog-monitoring, web-browsing-agents, workflow-automation, workflow-versioning, zero-supervision-workflows, agent-retirement-pathways, agent-scope-creep, child-agent-governance, dry-run-mode, orphaned-agents, permission-creep, read-only-inputs, scoped-tools, segregated-outputs, tool-boundary-controls]---

## Agentic Commerce Infrastructure Gap (Zip Co, July 2026)

## Governing Agents at Scale: Production Patterns (AI Realized Now Executive Roundtable, June 2026)

**Business Problem**: Enterprise organizations running agents in production needed governance frameworks that could handle delegated authority and blast radius at machine speed.

**AI Pattern Applied**: Multi-agent systems with production governance controls

**Industry/Function**: Cross-industry, senior AI leadership level

**What Made It Succeed**:
- **Govern the action, not the model**: Core reframe from senior AI leaders - focus governance on what agents do, not how models work
- **Policy-as-code enforcement**: Policy encoded in code that agents cannot edit themselves
- **Tool boundary containment**: Blast radius contained at the tool boundary where agents interact with systems
- **Substrate-as-attack-surface**: Treating the execution substrate (runtime environment, APIs, tool access) as the primary security concern
- **Specific human-in-the-loop definitions**: HITL scoped precisely to failure modes rather than generic oversight
- **Authority-based risk assessment**: Recognition that delegated authority creates blast radius, not model capability alone

**Key Insight**: Authority is what creates blast radius in agent systems. The containment strategy must focus on where agents exercise authority (tools, actions, system access) rather than attempting to constrain model behavior directly.

**Source**: AI Realized Now executive roundtable co-hosted with AiGovOps Foundation (anonymized under Chatham House Rule)

**Generalizability**: This governance pattern applies to any domain deploying agents with:
- System write access
- Financial transaction authority
- Customer-facing actions
- Compliance obligations
- Multi-agent orchestration

Relevant for: Financial services, healthcare, legal, manufacturing, supply chain, customer service, IT operations.

## Artifact-Scoped Agent Design (Chris Butler, AI Realized Now, July 2026)

**Business Problem**: Enterprise AI teams building agentic workflows that are slow, opaque, and hard to govern because they're scoped to roles ("PM agent", "compliance officer agent") rather than outputs.

**AI Pattern Applied**: Artifact-scoped agents (agents designed around specific, bounded outputs rather than job titles)

**Industry/Function**: Cross-industry, product management, compliance, any knowledge work function

**Anti-Pattern Identified**: Role-based agent scoping
- **Why it fails**: 
  - Roles are ambiguous and multi-faceted
  - No clear definition of "done"
  - Unclear input requirements
  - Creates "chatbots with ambitions" rather than reliable automation
  - Hard to govern due to scope ambiguity

**Success Pattern**: Artifact-scoped agents
- **Why it succeeds**:
  - Agent knows exactly what to produce (e.g., launch readiness report, compliance status table)
  - Clear input requirements
  - Explicit definition of completion
  - Bounded scope enables governance
  - Focuses on specific outputs teams already depend on

**Key Principle**: "Scope agents to artifacts" - the specific, bounded outputs a team already depends on, not the roles that produce them.

**Generalizability**: Universal pattern for knowledge work automation:
- Financial reporting and analysis
- Compliance documentation
- Status reports and dashboards
- Research briefs
- Technical documentation
- Customer communications
- Contract review summaries
- Risk assessments

Any function producing recurring, structured artifacts with defined quality criteria can apply this pattern.