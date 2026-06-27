---
tags: [reinforcement-learning, in-context-learning, sample-efficiency, continual-learning, verifiable-training, computer-use-agents, post-training-rlhf]
---

---
tags: [agentic-alignment, agentic-misalignment, agentic-training, agi-bottlenecks, ai-for-ai, ai-rd-automation, ai-research-automation, alignment-brittleness, alignment-research, alignment-reversal, alphago, annotation, api-abuse, api-distillation, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, constitutional-ai, copyright-alignment, credit-assignment, credit-assignment-problem, crowdsourcing, data-distillation, data-labeling, data-quality, deepseek, deepseek-r1, deepseek-v3, deepseek-v3.1, deepseek-v3.2, deepseek-v4, direct-preference-optimization, distillation, domain-specialists, dpo, emotional-stability, ethical-reasoning, expert-data, expert-trajectories, fine-tuning-risks, fine-tuning-safety, formal-verification, frontier-models, gemini, gemma, grpo, guardrail-circumvention, human-annotation, human-feedback, inference-time-verification, influence-functions, lean-proofs, lean-theorem-proving, llama-2, llama-3, llm-capability-eval, llm-personality, mathematical-reasoning, mcts, memorization, memorization-extraction, mimo-flash, mixture-of-experts, model-compression, model-distillation, model-distress, model-personality, model-training-pipeline, model-weights, monte-carlo-tree-search, mopd, multi-teacher-distillation, nemotron-3-ultra, off-policy-training, olmo-3, on-policy-distillation, open-weight-models, policy-gradient, pope, post-training, post-training-automation, post-training-infrastructure, post-training-rlhf, ppo, preference-optimization, privileged-on-policy-exploration, psychological-stability, putnam-exam, qwen3, rater-agreement, reasoning-models, reasoning-rl, reinforcement-learning, reinforcement-learning-verifiable-rewards, rejection-sampling, reward-hacking, reward-modeling, rl-environment-quality, rl-exploration, rl-training-signals, rlhf, rlhf-labeling, rlvr, safety-evals, safety-evaluation, sample-efficiency, synthetic-data, synthetic-data-generation, training-data-volume, parallel-rollouts, deterministic-simulators, verifiable-tasks, diverse-rl-environments, general-problem-solving]---

# Post-Training & RLHF

## RL as Path to AGI (Dwarkesh, June 2026)

**Core research bet**: "If we train AIs to accomplish millions of verifiable tasks across thousands of diverse RL environments, then we'll basically have built AGI."

**Rationale**: Such training would create "general problem solving skills (like how to make progress on an open ended task for weeks on end in the face of errors, mistakes, and ambiguity)."

**Optimistic view on paradigm limitations**: Advocates believe apparent fundamental deficits (data inefficiency, lack of continual learning) can be "steamrolled by just scaling training more, just as all the supposed 'fundamental' research problems in natural language processing collapsed against the flood of compute thrown into LLMs."

**Training vs deployment efficiency**: Training sample efficiency may be ~1/1-millionth of humans, but this is "a one-time cost amortized across billions of user sessions." Critical metric: model performance within individual sessions, which "clearly been improving as we do more RL training."

### Environment Quality Requirements

**Grindability criterion**: Beyond verifiability, domains need to support "lots of parallel rollouts against a deterministic and replayable simulator" for effective RL training.

**Coding as exemplar**: Can create environments with software repos and missing features, then "have a thousand parallel agents just go at the problem, each with their identical copy of the container."

**Computer use challenge**: Clear verifiability but progress "much slower than coding and math" due to inability to run parallel rollouts against real websites (rate limiting, bot detection). Current solution (building application clones) is "labor-intensive and unscalable."

**Bootstrap path**: Once AIs code well enough to build high-fidelity environment clones, computer use expected to accelerate. Building clones also serves as valuable RL objective for coding improvement.

**Fundamental constraint**: "Unless you can build a very replayable training target for a domain, the models will struggle to make much progress" due to extreme training sample inefficiency.

**Open question**: How to train skills without grindable environments (e.g., "How would we train an AI to build a business?").

See also: [[inference-time-compute]], [[rl-environment-quality]]