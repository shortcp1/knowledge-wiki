---
tags: [agentic-tasks, agentic-workflows-production, ai-code-review-bottleneck, behavioral-data-moats, cicd-deployment-constraints, claude-opus, content-addressed-caching, edge-compute, latency-optimization, liquid-ai-architecture, local-inference, qwen, shopify-ai-stack, simgym-customer-simulation, tangent-auto-research, tangle-ml-workflows, task-routing-patterns, token-budget-unlimited, tokenmaxxing]
---

# Agentic Workflows in Production

Covers real deployments of multi-step AI agent systems in production environments: human-in-the-loop designs, failure recovery, audit trails, latency management, and cost control. Distinguishes between what works in demos vs. what ships to customers.

Key questions tracked: What agent architectures are actually in production at scale? Where do agents fail in ways that matter? How are teams handling agent observability and debugging?

## Key Claims
<!-- agent-maintained -->

### Coding Agents
- **Codex Windows Deployment (OpenAI, May 2026)**: OpenAI shipped Codex on Windows with a secure sandbox implementation. Key production requirements included:
  - Controlled file system access
  - Network access restrictions
  - Safe code execution environment
  - This represents a production-grade coding agent deployment pattern addressing security constraints.
- **Codex CLI & Claude Code (April 2026)**: Both are production coding harnesses that wrap LLMs in engineered application layers. They represent the "agentic harness" pattern for software engineering tasks, managing:
  - Repository context
  - Tool design
  - Prompt-cache stability
  - Memory across coding sessions
  - Long-session continuity
  - These are distinguished from base models by their surrounding system engineering

### System Architecture Patterns
- **Three-Layer Coding Harness Architecture (Raschka, April 2026)**:
  1. **Model Family Layer**: The base LLM or reasoning model ("engine")
  2. **Agent Loop Layer**: Control flow that drives iterative work
  3. **Runtime Supports Layer**: Environment feedback, tool execution, state management
  - This layered pattern represents the production de

### Task Routing and Workload Distribution (May 2026)
- **Local vs. Cloud Task Routing Pattern (Tunguz, May 2026)**: Individual knowledge worker experiment revealing natural task distribution for hybrid local/cloud agent systems
  - **Context**: 1,478 AI agent tasks analyzed over 5 weeks
  - **Task taxonomy by suitability for local inference**:
    - **High-suitability (41.8% of tasks)**: Email & Inbound (11.5%), Scheduling (17.2%), Summarization (12.4%), Admin (0.7%)
    - **Medium-suitability (22.9%)**: Market Research (13.0%), Engineering (9.9%) - split between simple (local) and complex (cloud)
    - **Low-suitability (35.3%)**: Other/unstructured requests requiring frontier model reasoning
  - **Routing criteria emerging from usage**:
    - **Route to local**: Structured workflows, predictable outputs, high frequency, latency-sensitive, output feeds into systems
    - **Route to cloud**: Multi-source synthesis, architectural decisions, novel problem-solving, polish/presentation required
  - **Key architectural insight**: ~50% of knowledge work agent tasks suitable for local inference on consumer hardware (35B quantized models)
  - **Performance requirement**: Local must be 2x faster to justify quality gap (~20% reasoning benchmark difference)
  - **Quality-latency trade-off**: "For agent tasks where output feeds into another system, terseness is a feature" - suggests local models' brevity advantage
  - **Generalizability**: Pattern likely applies to other high-frequency knowledge work roles (customer support, sales ops, analyst workflows)
  - See [[inference-efficiency]] for local vs. cloud performance economics