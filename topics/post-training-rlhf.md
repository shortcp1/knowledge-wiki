---
tags: [ai-for-ai, ai-rd-automation, ai-research-automation, alphago, annotation, api-abuse, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, credit-assignment, credit-assignment-problem, crowdsourcing, data-quality, deepseek, deepseek-r1, direct-preference-optimization, distillation, dpo, emotional-stability, gemini, gemma, grpo, human-annotation, human-feedback, influence-functions, llm-capability-eval, llm-personality, mcts, mixture-of-experts, model-compression, model-distress, model-personality, model-training-pipeline, monte-carlo-tree-search, off-policy-training, open-weight-models, policy-gradient, post-training, post-training-automation, post-training-rlhf, preference-optimization, psychological-stability, rater-agreement, reasoning-models, reinforcement-learning, reinforcement-learning-verifiable-rewards, reward-hacking, rlhf-labeling, rlvr, safety-evaluation, self-play, sparse-attention, synthetic-data, teacher-student-learning, training-costs]
---

# Post-Training, RLHF & Alignment

Covers the techniques applied after pretraining to make models more useful and aligned: supervised fine-tuning (SFT), reinforcement learning from human feedback (RLHF), direct preference optimization (DPO), constitutional AI, and emerging reward modeling approaches.

Key questions tracked: Is DPO replacing RLHF in practice? How much does post-training contribute to capability vs. pretraining scale? What are the failure modes of RLHF at scale?

## Key Claims
<!-- agent-maintained -->

### Reward Hacking Definition & Scope (Nov 2024)
- **Definition**: Reward hacking occurs when an RL agent exploits flaws or ambiguities in the reward function to achieve high rewards without genuinely learning or completing the intended task
- **Fundamental challenge**: RL environments are often imperfect, and it is fundamentally challenging to accurately specify a reward function
- **Relationship to spurious correlation**: Reward hacking is closely related to spurious correlation/shortcut learning in classification tasks, where models overfit to shortcut fea

### DeepSeek R1 Post-Training Pipeline (December 2024)
- **Base model**: DeepSeek R1 built on DeepSeek V3 base model (identical architecture)
- **Training approach**: Additional post-training applied to base model to develop dedicated reasoning capability
- **Release pattern**: DeepSeek V3 released as base model, DeepSeek R1 as dedicated reasoning model
- **Industry impact**: Helped DeepSeek become "one of the most popular open-weight models" and competitive alternative to proprietary models (OpenAI, Google, xAI, Anthropic)
- **Cross-reference**: See [[model-architecture]] for details on hybrid vs. dedicated reasoning model patterns

###