---
tags: [intelligent-routing, local-models, async-batch-inference, skill-distillation, agentic-architecture, cost-optimization, inference-efficiency]
---

---
tags: [4-bit-quantization, agentic-ai, agentic-coding, agentic-tasks, apple-foundation-models, apple-silicon, async-inference, asynchronous-inference, batch-inference, code-generation-agents, coding-benchmarks, coding-models, context-caching, context-window, context-window-expansion, cost-optimization, custom-inference-chips, data-movement-optimization, deepseek, dense-attention, device-memory-constraints, energy-efficiency, expert-routing, external-memory-management, flash-memory-inference, fleet-aware-orchestration, fleet-orchestration, frontend-coding, glm-5.2, hybrid-transformer-mamba, indexcache, indexshare, inference-cost-optimization, inference-efficiency, inference-optimization, inference-pricing, inference-speed, instruction-following-pruning, jalapeno-chip, latent-moe, llm-inference-chips, local-models, long-context, long-context-processing, ma-activity, mamba-2, memory-compute-networking-balance, meta-learning, mixture-of-experts, mixture-of-experts-alternatives, model-distillation, model-fusion, model-routing, model-selection, mtp, multi-teacher-distillation, multi-token-prediction, near-real-time-inference, nemotron-3-super, nvfp4, nvidia, on-device-inference, open-source-models, open-weights, openai-chip, performance-per-watt, proximal-policy-optimization, quadratic-complexity, queued-inference, ram-vs-flash, read-evaluate-print-loop, real-time-inference, recursive-language-models, reward-hacking, rlm, routing-architecture, sail-research, slack-integration, sliding-window-attention, sparse-attention, sparse-attention-indexer, speculative-decoding, spot-capacity, subquadratic, swe-bench, test-time-training, throughput-optimization, tokens-per-dollar, tokens-per-second, transformer-architecture, ttt-e2e, vendor-lock-in, weight-compression, weight-update]---

## IndexShare for Speculative Decoding

**Introduced**: GLM-5.2 (June 2026)  
**Developer**: Z.ai  
**Purpose**: Improved multi-token prediction (MTP) to boost acceptance rates in speculative decoding

### Technical Details
- Exte

## Async vs Real-Time Inference Cost Delta

**Source**: Tomasz Tunguz (July 2026), Theory Ventures
**Cost Reduction**: Async batch reasoning runs ~2 orders of magnitude (90%+) cheaper than real-time inference

### Key Claims
- Local compute described as "close to free" for on-device models
- Real cost question: what fraction of work actually needs real-time answers?
- **Coinbase case study** (Brian Armstrong, ~June 2026): Cut AI spend nearly in half while token usage grew, via better defaults, routing, and caching

### Architecture Implications
- Most AI work can be queued rather than requiring sub-second responses
- Tasks suitable for async: draft replies, repo summaries, diligence memos, nightly evaluator runs
- See [[agentic-workflows-production]] for queueing patterns
- See [[ai-engineering-agents]] for skill distillation enabling local model usage

## Model Routing Architecture

**Emerging Pattern**: Router-first design over model-first design

### Three-Layer Routing System

1. **Skill Classifier** (Intent Recognition Layer)
   - Converts raw user request into concrete operation labels
   - Examples: draft-a-reply, summarize-a-repo, run-a-migration
   - This is a language understanding problem
   - Output: operation type, not model selection

2. **Router** (Scheduling Layer)
   - Decides which tier (local/async/real-time) executes the classified operation
   - **Does not read the prompt** — reads classifier label plus metadata
   - Input features: complexity, context size, historical success rate
   - This is a scheduling problem, not a language problem
   - Enables A/B testing different models against same operation

3. **Model Selector** (Tier Optimization Layer)
   - Picks cheapest model within selected tier that meets confidence threshold
   - Final decision point for specific model choice

### Reported Traffic Distribution
- **70-80% of agent traffic** can run on local models for most non-coding work (claim, July 2026)
- Prerequisite: skill distillation to flatten operation set (see [[ai-engineering-agents]])
- Remaining 20-30% requires remote inference (real-time or async)

### Design Principle
**"Design your system around routing, not around models. Pick your models last."** (Tunguz, July 2026)

This inverts the common pattern of selecting frontier models first then building architecture around them.

## Feedback Mechanisms for Routing

### Synchronous Failure-Mode Signals
- Predictor annotates incoming routes with risk features:
  - Missing repo context
  - Long dependency chains
  - Risky migrations
  - Security-sensitive prompts
  - High-consequence writes
- Catches known-hard tasks before they fail

### Nightly Closed-Loop Feedback
- Batch evaluator scores yesterday's traces overnight
- Updates router weights based on actual performance
- Runs on async inference to keep evaluation cost near zero
- Discovers new failure modes the synchronous predictor missed
- See [[agentic-workflows-production]] for async agent patterns