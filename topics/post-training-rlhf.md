---
tags: [agentic-alignment, agentic-misalignment, agentic-training, agi-bottlenecks, ai-for-ai, ai-rd-automation, ai-research-automation, alignment-brittleness, alignment-research, alignment-reversal, alphago, annotation, api-abuse, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, constitutional-ai, copyright-alignment, credit-assignment, credit-assignment-problem, crowdsourcing, data-labeling, data-quality, deepseek, deepseek-r1, deepseek-v3, deepseek-v3.1, deepseek-v3.2, deepseek-v4, direct-preference-optimization, distillation, domain-specialists, dpo, emotional-stability, ethical-reasoning, expert-trajectories, fine-tuning-risks, fine-tuning-safety, formal-verification, frontier-models, gemini, gemma, grpo, guardrail-circumvention, human-annotation, human-feedback, inference-time-verification, influence-functions, lean-proofs, lean-theorem-proving, llama-2, llama-3, llm-capability-eval, llm-personality, mathematical-reasoning, mcts, memorization, memorization-extraction, mimo-flash, mixture-of-experts, model-compression, model-distress, model-personality, model-training-pipeline, model-weights, monte-carlo-tree-search, mopd, multi-teacher-distillation, nemotron-3-ultra, off-policy-training, olmo-3, on-policy-distillation, open-weight-models, policy-gradient, post-training, post-training-automation, post-training-infrastructure, post-training-rlhf, ppo, preference-optimization, psychological-stability, putnam-exam, rater-agreement, reasoning-models, reasoning-rl, reinforcement-learning, reinforcement-learning-verifiable-rewards, rejection-sampling, reward-hacking, reward-modeling, rl-environment-quality, rl-training-signals, rlhf, rlhf-labeling, rlvr, safety-evals, safety-evaluation, sample-efficiency, self-play, sparse-attention, synthetic-data, synthetic-data-generation, teacher-student-learning, training-costs, training-harness, training-harness-reliability, trajectory-analysis, tulu-3, verbatim-regurgitation, verified-generation]
---

# Post-Training, RLHF & Alignment

Covers the techniques applied after pretraining to make models more useful and aligned: supervised fine-tuning (SFT), reinforcement learning from human feedback (RLHF), direct preference optimization (DPO), constitutional AI, and emerging multi-stage recipes.

## Evolution of Post-Training Recipes (2022-2026)

The shape of post-training recipes has changed dramatically:

**2022-2023 (InstructGPT era)**: Single pipeline — SFT → reward model → RL

**2024**: Open recipes formalize SFT → DPO → RL with verifiable rewards ([[reinforcement-learning-verifiable-rewards]]). Closed recipes use many stages of RLHF.

**2025 (DeepSeek R1)**: Reasoning RL makes large-scale RL the centerpiece rather than an add-on.

**2026 (MiMo Flash V2)**: Recipes fragment into many specialist models that are merged back into one via [[multi-teacher-distillation]].

## Multi-Teacher On-Policy Distillation (MOPD)

**Definition**: The dominant pattern in 2026 frontier models. Train N domain-specialist teachers (each: SFT, then RL on relevant domains), then train one general student by sampling its own trajectories and minimizing reverse-KL to the relevant teacher's output distribution, token by token.

**Lineage**: 
- Introduced in MiMo Flash V2
- Scaled to >10 teachers in DeepSeek V4 and Nemotron 3 Ultra

**Why MOPD emerged**:
1. **RL conflicts**: Mixing math, code, and agentic RL in one run trades capabilities off against each other
2. **Organizational scalability**: SFT-then-RL on a single domain is well understood and parallelizable across teams
3. **On-policy distillation maturity**: Literature and know-how emerged through the RLVR renaissance

## Historical Post-Training Recipes

### InstructGPT (March 2022)
Canonical 3-step recipe:
1. SFT on human demonstrations
2. Reward model trained on human comparisons
3. PPO against the reward model

### Llama 2 (July 2023)
Multi-stage RLHF:
- SFT, then iterative RLHF over multiple rounds
- Each round: rejection sampling → PPO
- Two reward models — separate helpfulness and safety

### Llama 3 (July 2024)
Complex multi-stage recipe with simpler optimizers:
- Per round: reward model → sample K per prompt → rejection sampling → SFT → DPO
- No online RL — the RM only filters; run over 6 rounds, best models seed the next

### Tülü 3 (November 2024)
Simple three-stage post-training:
- Curated prompts → SFT → DPO → RLVR (RL with verifiable rewards — acronym coined in this paper)

### OLMo 3 (December 2025)
Reasoning update to the Tülü 3 recipe

### DeepSeek R1 (January 2025)
**Major shift**: RL as the centerpiece, not an add-on

Recipe:
- **R1-Zero**: Pure RL (GRPO) on the base, no SFT; used to seed reasoning behaviors, not a separate product
- **R1 full**: cold-start SFT → reasoning RL → rejection-sampling SFT → final RL → distill to dense

**Paradigm change**: Large-scale RLVR as primary driver, SFT to distill and refine RL behaviors (reversal of traditional priority)

## DeepSeek Evolution Timeline

**V3** (December 2024): SFT + GRPO RL

**R1** (January 2025): Multi-stage RL; reasoning emerges

**V3.1** (August 2025): Hybrid think/non-think in one model

**V3.2** (December 2025): 6 specialists via RL → SFT distillation → one mixed GRPO

**V4** (April 2026): 10+ domain specialists using [[mopd]]

## Key Technical Patterns

### Rejection Sampling
Used extensively in [[llama-2]], [[llama-3]], and [[deepseek-r1]] to filter high-quality outputs from intermediate models.

### Multi-Stage RLHF
Iterative refinement through multiple rounds of RL training, each building on the previous stage.

### Domain Specialists
Training separate models for specific capabilities (math, code, agentic tasks) before combining them, enabling organizational parallelization and reducing capability conflicts.