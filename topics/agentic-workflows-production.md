---
tags: [agent-approval, agent-architecture, agent-composition, agent-compute, agent-compute-infrastructure, agent-deployment, agent-gravity, agent-harness, agent-harness-integration, agent-legibility, agent-orchestration, agent-safe-production-forks, agent-sandboxes, agent-self-configuration, agent-workload-migration, agentic-ci-cd, agentic-loop, agentic-loop-patterns, agentic-security, agentic-tasks, agentic-workflows, agentic-workflows-production, ai-agents, ai-code-review-bottleneck, ai-cost-forecasting, ai-sandboxes, ai-sre, async-agents, autonomous-agents, background-agents, bare-metal-infrastructure, bare-metal-scheduling, behavioral-data-moats, chain-of-thought, cicd-deployment-constraints, claude-opus, cloud-agents, cloud-economics, codex, codex-updates, coding-agents, content-addressed-caching, context-database, context-engineering, context-reprocessing, context-window, conversational-ai, custom-agents, dark-factory, data-exfiltration, data-gravity, databricks, daytona, deepseek-v4-pricing, deployment-automation, deterministic-vs-nondeterministic, docker-compose, dynamic-resource-scaling, edge-compute, eval-infrastructure, exfiltration-attacks, feature-flags, feature-flags-agents, frontier-evals, frontier-models, ghost-libraries, ghost-tokens, harness-architecture, harness-engineering, harness-in-the-box, hidden-token-multipliers, human-in-the-loop, hyperscale-operations, inference-cost, infrastructure-efficiency, knowledge-distillation, latency-optimization, lethal-trifecta, liquid-ai-architecture, local-inference, local-models, localhost-replacement, manager-agents, markdown-workflows, mcp-protocol, mcp-tools, mcp-vs-cli, meta-efficiency-agents, microsoft-copilot, microsoft-fabric, model-api-coopetition, model-behavior-engineer, model-harness-cotraining, model-lab-strategy, model-orchestration, model-product-stack, model-selection-strategy, non-determinism-control, non-deterministic-outputs, notion-custom-agents, operational-automation, out-of-the-box-agents, performance-optimization, platform-competition, platform-lock-in, procedural-knowledge, procedural-knowledge-retrieval, skill-distillation, skill-files, workflow-automation]
---

# Agentic Workflows in Production

## Personal Agent Architecture Pattern (Tunguz, 2026)

Three-layer architecture for personal productivity agents:

1. **Knowledge Base Layer**: Local markdown files (QMD pattern) storing ~80 workflow files in `~/memories`. Agent searches this before answering procedural questions.

2. **Skills Layer**: Atomic `SKILL.md` files, each describing one discrete job. Written and evaluated by frontier models (Opus 4.7, GPT-5.1, Gemini 3 Pro). System iteratively writes, tests, and rewrites until accuracy converges. Includes recall checks against QMD to ensure correct keyword surfacing.

3. **Agent Loop Layer**: Local model executing Plan → Tool Call → Observe → Refine pattern. Calls out to 17 Rust APIs and multiple MCP integrations.

### Skill Distillation Pattern

**Definition**: Frontier model authors and refines procedural skill files; smaller local model (Qwen 35B, Gemma 26B) executes them. Teacher transfers procedural knowledge through markdown rather than weights.

**Distinguishing characteristics**:
- NOT classical knowledge distillation (compressing soft probability outputs into weights)
- NOT instruction tuning (baking behavior into weights via prompt-response pairs)
- NOT RAG (which retrieves facts)
- IS procedural retrieval: smaller model follows steps rather than learning the capability

**Properties**:
- Skills are inspectable, versionable, hot-swappable
- Teacher model rotates based on frontier capabilities
- Student model rotates based on cost optimization
- Library becomes institutional knowledge independent of model weights

### Autonomous Skill Generation

Nightly batch process analyzes historical logs to identify needed new skills. Mirrors pattern described by Pete Koomen at Y Combinator.

### Production Use Cases

Reported applications: inbox management, deal pipeline, blog publishing, calendar management, research workflows. Presentation: "less like a chatbot & more like a small operating system."

## Cross-References
- [[rag-vs-finetuning-vs-wiki]]
- [[model-architecture]]
- [[mcp-protocol]]