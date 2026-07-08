---
tags: [harness-engineering, recursive-self-improvement, workflow-automation, agentic-systems, context-engineering, evolutionary-search, ai-engineering-agents]
---

---
tags: [agentic-ai, ai-coding-agents, ai-engineering-agents, autonomous-debugging, claude-code, claude-fable, coding-agents, cross-model-tool-compatibility, cuda-programming, economic-automation, gpu-kernel-optimization, model-regression, model-specific-tool-training, pre-release-testing, recursive-self-improvement, reinforcement-learning, reinforcement-learning-tool-bias, remote-labor-index, software-quality-assurance, tool-calling, tool-calling-reliability, tool-schema, transaction-management, harness-engineering, agent-harness, workflow-automation, file-system-memory, persistent-state-management, self-improving-agents, evolutionary-search, context-engineering, harness-optimization, loop-engineering, sub-agents, backend-jobs, goal-oriented-loops, bash-commands, artifact-management, auto-research, autoresearch-karpathy]---

## sqlite-utils 4.0rc2: Production Library Development with Claude Fable (July 2026)

**Source**: Simon Willison, "sqlite-utils 4.0rc2, mostly written by Claude Fable (for about $149.25)"

### Business Problem
- Final pre-release review and hardening of sqlite-utils 4.0 library before stable release
- Critical need to identify breaking changes and bugs before committing to SemVer major vers

## Harness Engineering for Recursive Self-Improvement (July 2026)

**Source**: Lilian Weng, "Harness Engineering for Self-Improvement", Lil'Log

### Conceptual Foundation
**Recursive Self-Improvement (RSI)**: Historical concept from I. J. Good (1965) defining "ultraintelligent machine" as system that can surpass humans in all intellectual activities and design better machines to improve itself.

**Modern AI Interpretation**: AI uses its current intelligence to improve the cognitive machinery that produces its intelligence. This includes:
- Model rewriting its own weights directly
- Model improving training pipeline and deployment system
- Enabling better successor models with improved performance on economically valuable tasks

**Key Insight**: "The layer between the raw model and the real-world context seems to be as important as the model's raw intelligence (i.e. the evals right after pretraining)"

### Harness Definition
**Core Components**: System surrounding base model that orchestrates:
- Execution and decision-making about how model thinks and plans
- Tool calling and actions
- Perception and context management
- Artifact storage
- Result evaluation

**Scope Beyond Early Agent Frameworks**: Evolution from "agent = LLM + memory + tools + planning + action" to include:
- Workflow design (loop engineering)
- Evaluation
- Permission controls
- Persistent state management
- Runtime and software system design

**Operating System Analogy**: Like an OS, harness should encapsulate complicated logic while keeping interface simple. Configs, tool interfaces, and protocols may gradually standardize across industry.

### Design Principle
**Deliberate Simplicity**: Design should be "deliberately simple and generic to enable generalization, likely with reference to existing software engineering practices to benefit from pretraining knowledge"

### Pattern 1: Workflow Automation
**Goal-Oriented Loop Structure**:
- Plan → Execute → Observe/Test → Improve → Execute again
- Loop continues until goal is achieved
- May trigger proactive requests to users for task specification clarity or execution preferences

**Example - Codex Agent Loop**: Agent calls tools, tool responses affect model's next generation (simplified workflow)

**Reference Implementation**: Karpathy's autoresearch repo (https://github.com/karpathy/autoresearch) as "clean example" of workflow construction

**Key Characteristic**: Workflow graph emphasizes model analyzing its own trajectories and failure cases, iterating through "agent runtime" rather than static prompt template

### Pattern 2: File System as Persistent Memory
**Core Pattern**: "Simple control over rich states and artifacts"

**Design Principle**: Harness should NOT carry entire workflow and logs in context. Instead, should keep durable state in files.

**Long-Horizon Challenge**: Artifacts often grow much longer than model's trained context window:
- Experiment logs
- Code diffs
- Paper summaries
- Error traces
- Past rollout trajectories

**Foundation Skill**: "Learning how to read, write, and edit the file system (commonly via bash commands) is a foundation skill for LLMs"

**Benefit**: Managing persistent memory in simple form of files leverages existing software engineering practices

### Pattern 3: Sub-agent and Backend Jobs
**Referenced but not detailed in excerpt**

### Harness Optimization Directions
**Three Areas Mentioned**:
1. Context Engineering
2. Workflow Design
3. Self-Improving Harness (including evolutionary search and joint optimization with model weights)

**Cross-reference**: [[recursive-self-improvement]] for broader RSI concepts, [[model-architecture]] for model weight optimization aspects