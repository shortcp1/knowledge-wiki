---
tags: [agentic-architecture, agentic-workflows, async-batch-inference, conductor-model, cost-optimization, evolutionary-algorithms, fugu, inference-efficiency, intelligent-routing, local-models, model-orchestration, multi-model-routing, multi-model-systems, orchestrator-models, sep-cma-es, skill-distillation, vendor-independence]
---

---
tags: [4-bit-quantization, agentic-ai, agentic-coding, agentic-tasks, apple-foundation-models, apple-silicon, async-inference, asynchronous-inference, batch-inference, code-generation-agents, coding-benchmarks, coding-models, context-caching, context-window, context-window-expansion, cost-optimization, custom-inference-chips, data-movement-optimization, deepseek, dense-attention, device-memory-constraints, energy-efficiency, expert-routing, external-memory-management, flash-memory-inference, fleet-aware-orchestration, fleet-orchestration, frontend-coding, glm-5.2, hybrid-transformer-mamba, indexcache, indexshare, inference-cost-optimization, inference-efficiency, inference-optimization, inference-pricing, inference-speed, instruction-following-pruning, jalapeno-chip, latent-moe, llm-inference-chips, local-models, long-context, long-context-processing, ma-activity, mamba-2, memory-compute-networking-balance, meta-learning, mixture-of-experts, mixture-of-experts-alternatives, model-distillation, model-fusion, model-routing, model-selection, mtp, multi-teacher-distillation, multi-token-prediction, near-real-time-inference, nemotron-3-super, nvfp4, nvidia, on-device-inference, open-source-models, open-weights, openai-chip, performance-per-watt, proximal-policy-optimization, quadratic-complexity, queued-inference, ram-vs-flash, read-evaluate-print-loop, real-time-inference, recursive-language-models, reward-hacking, rlm, routing-architecture, sail-research, slack-integration, sliding-window-attention, sparse-attention, sparse-attention-indexer, speculative-decoding, spot-capacity, subquadratic, swe-bench, test-time-computing, test-time-training, throughput-optimization, tokens-per-dollar, tokens-per-second, transformer-architecture, ttt-e2e, vendor-lock-in, weight-compression, weight-update]---

## IndexShare for Speculative Decoding

## Orchestrator Models: Multi-Model Routing (Sakana AI, July 2026)

### Architecture Pattern: Dedicated Orchestration Models
**Fugu and Fugu-Ultra System Design**:
- **Function**: Models trained specifically to orchestrate other models and agents rather than complete tasks directly
- **Input/Output**: Text and images in, text out
- **Worker Pool**: Claude Opus 4.8, Gemini 3.1 Pro, GPT-5.5, undisclosed open models, recursive self-calls
- **Unified API**: Single interface abstracts heterogeneous model backends
- **Key differentiation**: Fugu optimizes for speed (discrete tasks), Fugu-Ultra optimizes for performance (long-running tasks)

### Training Methodology: Score-Based Model Selection
**Supervised Fine-Tuning Phase**:
- Base: Undisclosed large language model
- Task domains: Coding, mathematics, language understanding, multistep reasoning, agentic tool use
- **Verification-based scoring**: Each worker model completes tasks multiple times with verifiable outputs
- **Distribution matching**: Train orchestrator to match distribution of success percentages across worker models
- Workers vary in abilities across different task elements (claim: different models excel at different subtask types)

**Evolutionary Optimization Phase**:
- Algorithm: sep-CMA-ES (evolutionary algorithm)
- Objective: Select optimal models for customized agentic tasks under fixed step budgets
- Harness compatibility: Claude Code, Codex, OpenCode
- **Constraint**: Fixed number of steps per task completion

**Reinforcement Learning Phase (Fugu-Ultra only)**:
- Algorithm: GRPO (Group Relative Policy Optimization)
- Training objective: Prompt worker LLMs to perform five-step agentic workflows
- Success criterion: Solutions match human solutions
- Generalization: Extended trained five-step workflows to arbitrary-length steps

### Operational Modes
**Fugu (Speed-Optimized)**:
- Sequential decision-making: Selects which model to call at each step until output generation
- Use case: Discrete tasks (basic coding, chat)

**Fugu-Ultra (Performance-Optimized)**:
- **Task decomposition**: Divides input into subtasks before execution
- **Agentic workflow design**: Constructs end-to-end workflow terminating in output generation
- **Parallel execution**: Can prompt multiple models simultaneously for different subtasks
- **Recursive decomposition**: Can call itself to further subdivide subtasks into granular tasks
- Use case: Long-running tasks (extensive coding, research)

### Conductor Component (Fugu-Ultra)
**Coordination Architecture**:
- **Function**: Coordinates multi-agent systems within Fugu-Ultra
- **Task breakdown**: Decomposes tasks into subtasks and assigns to agents
- **Agent autonomy**: Each agent independently selects tools within its subtask scope
- **Shared memory**: Agents can observe tool calls made by other agents
- **Multi-agent orchestration**: Enables parallel, independent agent operation with coordination

### Performance Claims
**Benchmark Results**:
- **Fugu and Fugu-Ultra outperformed**: Claude Fable 5, Claude Mythos Preview, GPT-5.5 on Terminal Bench 2.1, GPQA-Diamond, LiveCodeBench
- **Fugu-Ultra outperformed**: Claude Fable 5, Claude Mythos Preview, GPT-5.5 on CharXiv Reasoning, CTI-Realm
- **Fugu-Ultra state-of-the-art**: SWE-Bench Pro, Humanity's Last Exam, LiveCodeBench Pro (outperformed all available models)
- **Aggregate performance**: Comparable to [[model-architecture|Claude Mythos 5]] and GPT-5.6 Sol
- **Key advantage claim**: Achieves frontier performance without dependency on particular model

### Pricing Model
**Fugu**: Priced at top underlying model's standard rate
**Fugu-Ultra**: 
- Standard context (≤272K tokens): $5/$30/$0.50 per 1M input/output/cached tokens
- Extended context (>272K tokens): 2x standard rates
- Subscription tiers: $20/$100/$200 per month (standard/pro/max with 1x/10x/30x usage limits)
- **Pricing includes**: All submodels and agents

### Availability and Transparency
**Distribution**: Sakana API, OpenRouter, Vercel, other providers (unavailable in Europe)
**Undisclosed**: Orchestration recipes, training datasets, base model architectures, parameter counts
**Compatibility**: OpenAI Codex, tool use, high and extra high reasoning levels

### Cost-Efficiency Pattern
**Economics**: Pay-per-use model enables cost optimization through intelligent routing without maintaining multiple model subscriptions
**Vendor independence**: Single API reduces [[inference-efficiency|vendor-lock-in]] while accessing multiple frontier models
**Adaptive allocation**: Orchestrator can route to most cost-effective model for each subtask type

Cross-references: [[agentic-workflows-production]] for production deployment patterns, [[model-architecture]] for underlying model capabilities