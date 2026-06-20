---
tags: [agentic-reasoning, agi-bottlenecks, ai-research-automation, alphago, best-of-n-sampling, chain-of-thought, coding-agents, credit-assignment, credit-assignment-problem, deepseek-r1, expert-data, formal-verification, grpo, inference-time-compute, inference-time-scaling, inference-time-verification, iterative-evaluation, lean-proofs, lean-theorem-proving, mathematical-reasoning, mcts, mixture-of-experts, model-distillation, monte-carlo-tree-search, off-policy-training, open-weights, policy-gradient, pope, post-training, privileged-on-policy-exploration, putnam-exam, reasoning-models, reinforcement-learning, rejection-sampling, rl-exploration, rl-training-signals, rl-training-targets, rlhf, rlvr, rollout-generation, sample-efficiency, self-consistency, self-play, self-refinement, swe-bench, synthetic-data, synthetic-data-generation, training-costs, verified-generation]
---

# Inference-Time Compute & Reasoning Models

Covers test-time scaling: chain-of-thought reasoning, process reward models, search-based approaches (MCTS, beam search over reasoning traces), and models trained to "think longer." Includes OpenAI o-series, DeepSeek-R1, and the emerging o1/reasoning model paradigm.

Key questions tracked: What is the scaling law for inference-time compute? When does more thinking help vs. hurt? How does this change the economics of AI APIs?

## Key Claims

### Conceptual Foundations (Weng, May 2025)

**Test-time compute (thinking time)**: Core research area since ~2016 (Graves et al. 2016, Ling et al. 2017, Cobbe et al. 2021), formalized as using additional computation during inference rather than fixed forward passes.

**Computational perspective**: In standard Transformers, computation per generated token ≈ 2 × parameters. For MoE models: computation = 2 × parameters / sparsity (where sparsity = fraction of experts active).
- **CoT advantage**: Enables variable compute allocation based on problem d

### Rollout Generation at Scale (Dwarkesh, June 2026)

**GRPO rollout intensity**: Models generate "hundreds to thousands of rollouts per task" during training - far exceeding human practice patterns (1-2 attempts per problem).

**Connection to [[post-training-rlhf]]**: This massive rollout generation serves as synthetic data for RL training, requiring verifiers to identify correct solutions from the generated distribution.