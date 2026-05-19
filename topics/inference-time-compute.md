---
tags: [ai-research-automation, alphago, best-of-n-sampling, chain-of-thought, credit-assignment, credit-assignment-problem, deepseek-r1, grpo, inference-time-compute, inference-time-scaling, mcts, monte-carlo-tree-search, off-policy-training, policy-gradient, post-training, reasoning-models, reinforcement-learning, rejection-sampling, rl-training-targets, rlvr, self-consistency, self-play, self-refinement, training-costs]
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
- **System 2 (slow thinking)**: Deliberate, logical reasoning requiring significant cognitive effort
- **CoT as System 2**: Extended reasoning allows models to "challenge instincts" and make more rational outputs

**Latent variable modeling perspective**: 
- Mathematical formulation: $P(y \mid x) = \sum_{z \sim p(z\mid x)} P(y \mid x, z)$

### Reasoning Model Definition (Raschka, Dec 2025)
- **Operational definition**: In LLM context, reasoning means the model explains its answer, and this explanation itself often leads to improved answer accuracy
- **Behavior characterization**: Model generates intermediate steps/traces rather than direct short responses
- **Alternative terminology**: Often called "thinking" models in industry

### OpenAI o1 and DeepSeek R1 Timeline (2024-2025)
- **OpenAI o1**: Released before January 2025, "added reasoning traces" and changed how LLMs behaved/felt in practice
- **Pre-R1 observation**: "Scaling still worked, but it didn't really change how LLMs behaved or felt in practice (the only exception to that was OpenAI's freshly released o1)" (Raschka assessment)
- **DeepSeek R1 significance**: Released January 2025, "showed that reasoning-like behavior can be developed with reinforcement learning" - described as "a really big deal"
- **Industry shift**: Following DeepSeek R1, every major open-weight and proprietary LLM developer released reasoning variant (observation through 2025)
- **Training approach**: See [[post-training-rlhf]] for RLVR/GRPO methods used to develop reasoning capabilities

##