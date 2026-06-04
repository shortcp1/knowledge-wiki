---
tags: [agentic-reasoning, agi-bottlenecks, ai-research-automation, alphago, best-of-n-sampling, chain-of-thought, coding-agents, credit-assignment, credit-assignment-problem, deepseek-r1, formal-verification, grpo, inference-time-compute, inference-time-scaling, inference-time-verification, iterative-evaluation, lean-proofs, lean-theorem-proving, mathematical-reasoning, mcts, mixture-of-experts, monte-carlo-tree-search, off-policy-training, open-weights, policy-gradient, post-training, putnam-exam, reasoning-models, reinforcement-learning, rejection-sampling, rl-training-signals, rl-training-targets, rlvr, self-consistency, self-play, self-refinement, swe-bench, training-costs, verified-generation]
---

# Inference-Time Compute & Reasoning Models

Covers test-time scaling: chain-of-thought reasoning, process reward models, search-based approaches (MCTS, beam search over reasoning traces), and models trained to "think longer." Includes OpenAI o-series, DeepSeek-R1, and the emerging o1/reasoning model paradigm.

Key questions tracked: What is the scaling law for inference-time compute? When does more thinking help vs. hurt? How does this change the economics of AI APIs?

## Key Claims

### Conceptual Foundations (Weng, May 2025)

**Test-time compute (thinking time)**: Core research area since ~2016 (Graves et al. 2016, Ling et al. 2017, Cobbe et al. 2021), formalized as using additional computation during inference rather than fixed forward passes.

**Computational perspective**: In standard Transformers, computation per generated token ≈ 2 × parameters. For MoE models: computation = 2 × parameters / sparsity (where sparsity = fraction of experts active).
- **CoT advantage**: Enables variable compute allocation based on problem difficulty, performing "far more flops of computation for each token of the answer"

**Psychology analogy (Kahneman's dual process theory)**:
- **System 1 (fast thinking)**: Quick, automatic, intuitive responses requiring little effort
- **System 2 (slow thinking)**: Deliberate, logical reasoning requiring

### Verified Generation (Axiom, Mid-2026)

**Informal vs. Formal proofs bottleneck**: Carina Hong (Axiom CEO) argues that coding ability alone is insufficient for AGI progress, identifying "informal" mathematical reasoning as a key bottleneck. While models can generate informal proofs, translating these to formally verified proofs (e.g., in [[lean-proofs]]) remains challenging.

**Axiom performance claims**:
- **Putnam exam**: 12/12 problems solved (8/12 within time limit), compared to DeepSeek's 103/120 and top human undergraduates at 110/120. Note: unclear what time constraints were for comparison systems.
- **ProofGen benchmark (Verina)**: 99% (187/189) on code generation with proof of correctness, vs. OpenAI o3's 4.9%. Benchmark requires generating both code and formal proof of correctness.

**Current frontier gap (claim, mid-2026)**: Carina Hong suggests frontier labs are still training primarily on informal proofs rather than direct Lean proof generation, potentially limiting their [[post-training-rlhf]] effectiveness.