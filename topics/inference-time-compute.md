---
tags: [reinforcement-learning, in-context-learning, sample-efficiency, continual-learning, verifiable-training, computer-use-agents, inference-time-compute]
---

---
tags: [agentic-reasoning, agi-bottlenecks, ai-research-automation, alphago, best-of-n-sampling, chain-of-thought, coding-agents, credit-assignment, credit-assignment-problem, deepseek-r1, expert-data, formal-verification, grpo, inference-time-compute, inference-time-scaling, inference-time-verification, iterative-evaluation, lean-proofs, lean-theorem-proving, mathematical-reasoning, mcts, mixture-of-experts, model-distillation, monte-carlo-tree-search, off-policy-training, open-weights, policy-gradient, pope, post-training, privileged-on-policy-exploration, putnam-exam, reasoning-models, reinforcement-learning, rejection-sampling, rl-exploration, rl-training-signals, rl-training-targets, rlhf, rlvr, rollout-generation, sample-efficiency, self-consistency, self-play, self-refinement, swe-bench, synthetic-data, synthetic-data-generation, training-costs, verified-generation, parallel-rollouts, deterministic-simulators, context-window-scaling, in-context-learning, continual-learning, sample-efficiency-deficit, environment-quality, grindability]---

# Inference-Time Compute & Reasoning Models

Covers test-time scaling: chain-of-thought reasoning, process reward models, search-based approaches (MCTS, beam search over reasoning traces), and models trained to "think longer." Includes OpenAI o-series, DeepSeek-R1, and the emerging o1/reasoning model paradigm.

Key questions tracked: What is the scaling law for inference-time compute? When does more thinking help vs. hurt? How does this change the economics of AI APIs?

## Key Claims

### Conceptual Foundations (Weng, May 2025)

**Test-time compute (thinking time)**: Core research area since ~2016 (Graves et al. 2016, Ling et al. 2017, Cobbe et al. 2021), formalized as using additional computation during inference rather than fixed forward passes.

**Computational perspective**: In standard Transformers, computation per generated token ≈ 2 × parameters. For MoE models: computation = 2 × parameters / sparsity (where sparsity = fraction of experts active).
- **CoT advantage**: Enables variable compute allocation based on problem d

### Rollout Generation at Scale (Dwarkesh, June 2026)

**GRP

### In-Context Learning as Alternative to Weight Updates (Dwarkesh, June 2026)

**Continual learning may be unnecessary**: If in-context learning improves across longer horizons, weight updates from deployment may not be required for on-the-job learning. Analogy: human employees often take 6+ months to become net productive; with sufficiently large context windows, this learning period could fit within context.

**Architectural progress**: "Tons of architectural innovations on the transformer which dramatically increase the length of context you can store." Prediction: "With a couple more years of progress, why couldn't we have arbitrarily large context windows?"

**Session-level vs training-level efficiency**: Training sample efficiency may be ~1/1-millionth of human performance, but this is a one-time cost amortized across billions of sessions. What matters: "how smart, general, and sample efficient the model is within a session."

**Empirical observation**: "AIs are able to solve more and more ambitious problems across longer and longer time spans - anybody who's been using these models for coding knows that."

### Domain Characteristics for RL Training (Dwarkesh, June 2026)

**Grindability as critical factor**: Verifiability alone insufficient for rapid progress. Domains must be "grindable"—supporting many parallel rollouts against deterministic, replayable simulators.

**Computer use as counterexample**: Despite clear verifiability (e.g., "did the desired Etsy item get ordered"), progress has been "much slower than coding and math." 

**Reasons for computer use lag**:
- Less high-quality multimodal data during pretraining
- Video consumes context window faster
- **Cannot run parallel rollouts**: "You can't have a thousand agents go try the same checkout flow on Amazon.com. Because Andy Jassy will find and detect your bots and shut your ass down."

**Workaround**: Building clones of Slack, Gmail, and other applications—but "currently, this is a very labor-intensive and unscalable way to build environments."

**Future solution**: Once AIs can code well enough to build high-fidelity clones themselves, computer use progress expected to accelerate. This creates dual benefit: building clones is itself "a great RL objective for coding."

**Sample efficiency bottleneck**: Models' extreme training sample inefficiency means "unless you can build a very replayable training target for a domain, the models will struggle to make much progress."

**Unsolved domains**: Many AGI-relevant skills lack grindable environments: "How would we train an AI to build a business? How would you make an AI that&" [article truncated]

See also: [[rl-environment-quality]], [[post-training-rlhf]], [[model-architecture]]