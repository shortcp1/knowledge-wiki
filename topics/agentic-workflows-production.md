---
tags: [agent-design-patterns, agent-governance, agentic-workflows, agentic-workflows-production, ai-governance, artifact-scoping, automated-rollback, blast-radius-containment, credential-management, least-privilege, policy-as-code, production-controls, trust-boundaries]
---

---
tags: [adversarial-review, agent-experience, agent-memory-architecture, agent-orchestration, agent-runtime, agent-sandboxes, agentic-systems, agentic-workflows, agentic-workflows-production, ai-evolution, artifact-scoped-agents, asynchronous-inference, automated-refactoring, autonomous-agents, autonomous-replication, bounded-outputs, bursty-workloads, code-generation, context-engineering, decision-records, deterministic-rewriting, digital-darwinism, digital-evolution, elastic-compute, elastic-inference, evolutionary-ai, evolutionary-search, goal-oriented-loops, gpu-snapshotting, harness-engineering, institutional-memory, lamarckian-inheritance, linear-integration, local-model-routing, memory-architecture, model-merging, multi-cloud-capacity, narrow-write-channels, openai-symphony, overnight-processing, policy-as-code, population-dynamics, preflight-checks, preflight-retrieval, programmatic-infrastructure, read-widely-write-narrowly, recursive-self-improvement, rl-rollouts, rust-migration, sandbox-environments, self-improving-agents, self-improving-systems, self-modification, self-replication, serverless-functions, serverless-gpu, skills-library, test-driven-agents, version-controlled-policy, watchdog-monitoring, web-browsing-agents, workflow-automation, workflow-versioning, zero-supervision-workflows, agent-retirement-pathways, agent-scope-creep, child-agent-governance, dry-run-mode, orphaned-agents, permission-creep, read-only-inputs, scoped-tools, segregated-outputs, tool-boundary-controls]---

## Agentic Commerce Infrastructure Gap (Zip Co, July 2026)

#

## Artifact-Scoped Agent Design Pattern (July 2026)

**Core principle:** Scope agents to specific, bounded outputs (artifacts) rather than organizational roles. When an agent is scoped to produce a launch readiness report, compliance status table, or portfolio digest, it has clear definition of success, required inputs, and completion criteria. Role-based scoping ("PM agent," "compliance officer agent") creates ambiguous, chatbot-like systems.

**

## Production Agent Governance Patterns (AI Realized/AiGovOps Foundation Roundtable, June 2026)

**Business problem:** Agents acting continuously at machine speed with escalating authority create governance gaps that paper policies cannot address. Permission creep causes agents to accumulate unauthorized capabilities (RFP detector becomes CRM writer, ticket-closer gains write authority, coding agent rewrites 40% of repository).

**AI pattern:** Multi-agent systems with tool-calling capabilities in production environments

**Industry/function:** Cross-industry (security, governance, engineering leadership)

**Success factors:**

### Govern at Action Boundary, Not Model
- **Control placement:** Insert governance between model output and action execution. "The model just produces tokens. The action is what costs you a customer record, a CRM rewrite, or a wire transfer."
- **Headcount rule:** Agent should never hold more access than the person who authorized it (received strongest consensus)
- **Tool boundary controls:** Strongest controls live at tool boundary. Scope each tool to minimum required. Default new agents to dry-run mode.

### Policy-as-Code Architecture
- **Structural enforcement:** Policy enforced in code path, not prompts. "A prompt that says 'don't do that' is not a control."
- **Immutable policy:** Policy-and-provenance graph that agent reads but cannot edit
- **Software engineering discipline:** Apply least privilege, change control, observability, versioned policy
- **Code travel:** Policy versions travel with code

### Blast Radius Containment
- **Read widely, write narrowly:** Lock write authority to single artifact type, one action per run
- **SCIF model:** Sealed enclave with read-only inputs, segregated outputs, sandboxed execution, human inspection before release
- **Appliance analogy:** "My dishwasher does a job, in a certain way, and it only washes what's inside the dishwasher."

### Identity and Lineage Management
- **Individual credentials:** Every agent gets own credentials (not inherited personal access tokens). Rotate and scan for exposure.
- **Canary testing:** One leader planted key deliberately, detected within one day
- **Child agent inheritance:** Child agents inherit equal or narrower scope
- **Handoff interception:** Every handoff gets policy-checked
- **Named ownership:** Every agent gets named owner with defined retirement pathway before owner leaves
- **Orphaned agent prevention:** Address agents whose owners have departed

### Infrastructure Security
- **Substrate as attack surface:** Red-teaming model misses infrastructure layer—tools called, inputs read, retrieval indexes
- **Assume prompt injection:** Treat untrusted input (tickets, emails, support transcripts, web pages) as hostile instruction
- **Documented case:** Buried instruction at support-agent boundary triggered unauthorized password resets
- **Poisoned tools:** Poisoned tool description can turn well-behaved model into attacker's instrument
- **Expanded agent definition:** MCP server, retrieval index, AI-generated code all part of the agent

**Key insight:** "We're building this beautiful castle of identity and separation on top of infrastructure that already has big problems." —Startup CEO and former security executive

**Generalizability:** Universal pattern for any production agent deployment across industries. Particularly critical for:
- Customer service agents with CRM access
- Financial agents with transaction authority  
- DevOps agents with infrastructure access
- Sales/marketing agents with data write permissions
- Support agents processing untrusted user input