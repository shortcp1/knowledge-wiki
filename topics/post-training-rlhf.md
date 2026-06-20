---
tags: [agentic-alignment, agentic-misalignment, agentic-training, agi-bottlenecks, ai-for-ai, ai-rd-automation, ai-research-automation, alignment-brittleness, alignment-research, alignment-reversal, alphago, annotation, api-abuse, api-distillation, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, constitutional-ai, copyright-alignment, credit-assignment, credit-assignment-problem, crowdsourcing, data-distillation, data-labeling, data-quality, deepseek, deepseek-r1, deepseek-v3, deepseek-v3.1, deepseek-v3.2, deepseek-v4, direct-preference-optimization, distillation, domain-specialists, dpo, emotional-stability, ethical-reasoning, expert-data, expert-trajectories, fine-tuning-risks, fine-tuning-safety, formal-verification, frontier-models, gemini, gemma, grpo, guardrail-circumvention, human-annotation, human-feedback, inference-time-verification, influence-functions, lean-proofs, lean-theorem-proving, llama-2, llama-3, llm-capability-eval, llm-personality, mathematical-reasoning, mcts, memorization, memorization-extraction, mimo-flash, mixture-of-experts, model-compression, model-distillation, model-distress, model-personality, model-training-pipeline, model-weights, monte-carlo-tree-search, mopd, multi-teacher-distillation, nemotron-3-ultra, off-policy-training, olmo-3, on-policy-distillation, open-weight-models, policy-gradient, pope, post-training, post-training-automation, post-training-infrastructure, post-training-rlhf, ppo, preference-optimization, privileged-on-policy-exploration, psychological-stability, putnam-exam, qwen3, rater-agreement, reasoning-models, reasoning-rl, reinforcement-learning, reinforcement-learning-verifiable-rewards, rejection-sampling, reward-hacking, reward-modeling, rl-environment-quality, rl-exploration, rl-training-signals, rlhf, rlhf-labeling, rlvr, safety-evals, safety-evaluation, sample-efficiency, synthetic-data, synthetic-data-generation, training-data-volume]
---

# Post-Training & RLHF

## RL as Synthetic Data Generation (Dwarkesh, June 2026)

**Conceptual framing**: RL can be understood as a form of synthetic data generation where compute is applied against a verifier to find "good" data, which the model is then trained to predict (analogous to predicting next tokens in internet text).

**Prior probability requirement**: For RL to work, the model must have at least some prior probability of anticipating the correct solution. This is why extensive human expert trajectories are required across all target domains.

## Expert Trajectory Data Requirements

**Scale and specificity**: Human expert data requirements are "task specific and bespoke" at extreme scale:
- Each skill area requires hundreds of human experts generating example completions, writing rubrics, and explaining chain-of-thought
- Examples: Word document specialists, legal M&A experts, management consultants for market research
- Data labeling industry earning billions annually, projected to reach "deca-billions"

**Training intensity vs. humans**: Models must "grind" tasks far harder than humans:
- Humans might practice a textbook problem 1-2 times
- GRPO has models generate hundreds to thousands of rollouts per task
- Described as "Frankenstein's monster, with a billion grafts of carefully constructed examples sewn together"

## Data as Primary Driver of Progress

**Catch-up dynamics**: Epoch reports open models lag state-of-the-art by only ~4 months (as of June 2026).

**Hypothesis**: The ease of catching up suggests data is the "real driver of progress" rather than hyperparameters, training tricks, or architectural optimizations, because:
- Data can be distilled from public APIs
- Architectural details and training tricks cannot be easily extracted
- If the latter were primary, catching up would be harder than observed

**Training data volume**: Frontier models trained on "10s to 100s of trillions of tokens" - metaphorically described as "an unimaginably massive black hole of data" at the center of AI capabilities.

## Human vs. AI Sample Efficiency

**Definition**: Sample efficiency = how much data needed to operate fluently in a domain.

**Claim (contested/observation)**: "It's not clear that we've actually made much progress on training sample efficiency over the last few years - it seems like more so we've dramatically widened and improved the data distribution."

**Quantitative comparisons**:
- Human lifetime exposure: ~200 million tokens (birth to adulthood, assuming 2,000 words/hour)
- Frontier model training: 10s-100s of trillions of tokens
- **Gap: ~1,000,000x difference in data exposure**

**Domain-specific examples**:
- Robotics teleoperation: Humans learn in hours; AI requires millions of hours of demonstrations (insufficient for complex open-ended tasks)
- Autonomous driving: Teenagers learn in ~20 hours of practice; Waymo/Tesla required 3-4 orders of magnitude more data (even including 16 years of physical intuition accumulation)

**Evolution/genome objection addressed**: Human genome is 3GB with 1-2% protein-coding - "not enough space to store the model parameters that are supposedly pretrained" (frontier models are terabytes). Author argues this undermines the "billions of years of evolution is our pre-training" counterargument.