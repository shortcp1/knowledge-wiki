---
tags: [adversarial-review, agent-experience, agent-memory-architecture, agent-orchestration, agent-runtime, agent-sandboxes, agentic-systems, agentic-workflows, agentic-workflows-production, asynchronous-inference, automated-refactoring, autonomous-agents, bursty-workloads, code-generation, context-engineering, deterministic-rewriting, elastic-compute, elastic-inference, evolutionary-search, goal-oriented-loops, gpu-snapshotting, harness-engineering, linear-integration, local-model-routing, memory-architecture, multi-cloud-capacity, openai-symphony, overnight-processing, preflight-checks, preflight-retrieval, programmatic-infrastructure, recursive-self-improvement, rl-rollouts, rust-migration, sandbox-environments, self-improving-agents, self-improving-systems, serverless-functions, serverless-gpu, skills-library, test-driven-agents, watchdog-monitoring, web-browsing-agents, workflow-automation, workflow-versioning, zero-supervision-workflows]---

---
tags: [agentic-ai, agentic-commerce, agentic-workflows, agentic-workflows-production, autonomous-purchasing, bnpl, conductor-architecture, cuda-programming, economic-automation, evolutionary-algorithms, financial-underwriting, gpu-kernel-optimization, intent-verification, kya-know-your-agent, model-orchestration, multi-model-orchestration, multi-model-systems, orchestrator-models, recursive-self-improvement, remote-labor-index, sep-cma-es, vendor-independence, openai-codex, browser-automation-agents, ebay-scouting, price-arbitrage-agents, small-business-ai, retail-intelligence, psa-certificate-validation, tcgplayer-pricing, collectibles-market-agents, autonomous-browsing, conformance-suites, adversarial-review, parallel-agent-coordination, large-scale-refactoring]---

## Agentic Commerce Infrastructure Gap (Zip Co, July 2026)

### Business Problem
**BNPL Infrastructure Meets Autonomous Commerce**:
- Traditional BNPL designed for humans making purchase decisions with visible intent signals
- Agentic commerce shifts purchasing decisions to software agents
- Core problem: "Infrastructure mismatch: autonomous buyers operating on systems built to verify human intent"
- Critical separation: Intent from action - "person making the purchase and person assuming the debt" no longe

## Memory Architecture: Preflight Pattern (Theory Ventures, July 2026)

**Source**: Tomasz Tunguz, "The AI Preflight Check"

### Core Architectural Pattern

**Central Claim**: "Context size is not the ceiling. Memory architecture is."

Three-stage memory architecture for production agent deployment:

1. **Preflight Retrieval**: Agent inspects skills library, selects relevant skills, loads only those into context window
   - Skills are "consolidated memory"
   - Preflight is the selection mechanism
   - Example workload: "Summarize the Q3 board deck" over 200,000 raw tokens of emails, PDFs, chats

2. **Local Execution**: [[inference-efficiency]] routing pattern
   - Ornith 35B (local 35B-parameter model on Apple Silicon via Ollama) handles ~80% of routine tasks
   - Hard tasks route to frontier models
   - Local model executes on loaded context only

3. **Watchdog + Overnight Processing**: [[inference-efficiency]]
   - Logs every preflight decision, skill invocation as named, versioned artifact
   - Monitors: which skills loaded, decisions made, success rates
   - Overnight [[inference-efficiency#Asynchronous Inference]]: processes day's trail, decides new skill development
   - **Deterministic Rewriting**: Identifies workflow components that should become Rust code (e.g., calendar free/busy comparison)
   - Self-improving loop: rewrites skills library, restarts system

### Skills Library Architecture

**Technical Implementation** (~90 workflow files as of July 2026):
- On-disk indexed storage
- Retrieved by intent match
- Workflows written once, versioned
- Handed to model as tool schemas
- See [[ai-engineering-agents#Skill Distillation]]

### Plateau Behavior

**Empirical Finding**: First day where watchdog suggested zero improvements observed
- Uncertain if sustainable: "I doubt it will continue"
- Hypothesis: "at some level of improvement, the system reaches a plateau. Only genuinely new exceptions need human help"
- **Confidence Level**: Single observation, requires validation

### Cross-References
- Local execution model: [[inference-efficiency#Local Models]]
- Overnight processing: [[inference-efficiency#Asynchronous Inference]]
- Skill development: [[ai-engineering-agents#Skill Distillation]]
- Code generation patterns: [[ai-engineering-agents]]