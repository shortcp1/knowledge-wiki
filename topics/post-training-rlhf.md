---
tags: [agentic-alignment, agentic-misalignment, agi-bottlenecks, ai-for-ai, ai-rd-automation, ai-research-automation, alignment-research, alphago, annotation, api-abuse, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, constitutional-ai, credit-assignment, credit-assignment-problem, crowdsourcing, data-quality, deepseek, deepseek-r1, direct-preference-optimization, distillation, dpo, emotional-stability, ethical-reasoning, formal-verification, gemini, gemma, grpo, human-annotation, human-feedback, inference-time-verification, influence-functions, lean-proofs, lean-theorem-proving, llm-capability-eval, llm-personality, mathematical-reasoning, mcts, mixture-of-experts, model-compression, model-distress, model-personality, model-training-pipeline, monte-carlo-tree-search, off-policy-training, open-weight-models, policy-gradient, post-training, post-training-automation, post-training-rlhf, preference-optimization, psychological-stability, putnam-exam, rater-agreement, reasoning-models, reinforcement-learning, reinforcement-learning-verifiable-rewards, reward-hacking, rl-training-signals, rlhf, rlhf-labeling, rlvr, safety-evals, safety-evaluation, self-play, sparse-attention, synthetic-data, teacher-student-learning, training-costs, verified-generation]
---

# Post-Training, RLHF & Alignment

Covers the techniques applied after pretraining to make models more useful and aligned: supervised fine-tuning (SFT), reinforcement learning from human feedback (RLHF), direct preference optimization (DPO), constitutional AI, and emerging reward modeling approaches.

Key questions tracked: Is DPO replacing RLHF in practice? How much does post-training contribute to capability vs. pretraining scale? What are the failure modes of RLHF at scale?

## Key Claims
<!-- agent-maintained -->

### Reward Hacking Definition & Scope (Nov 2024)
- **Definition**: Reward hacking occurs when an RL agent exploits flaws or ambiguities in the reward function to achieve high rewards without genuinely learning or completing the intended ta

### Verified Rewards via Formal Verification (Axiom, Mid-2026)

**Formal verification as superior reward signal**: Using Lean theorem provers to verify mathematical proofs provides a "much stronger reward signal" than statistical methods (GRPO, RLHF) during [[reinforcement-learning]]. This is analogous to compiling and testing code in coding RL, providing binary correctness verification rather than probabilistic assessments.

**Ramanujan analogy (scaling and compounding brilliance)**: Formal proofs serve dual purposes:
1. **Compounding**: Forces articulation of details that opens new lines of thinking and improves the prover's own capabilities
2. **Scaling**: Creates communicable artifacts that others can verify, learn from, and build upon

**Training loop advantage**: Better formal proofs → better Lean generation → better RL signal → higher sample efficiency and maximum performance. This creates a compounding effect distinct from informal proof training.

**Current limitation**: LLMs are not currently very good at generating Lean proofs directly, which limits the applicability of verified generation approaches. Most formalization of informal proofs remains extremely labor-intensive.

**Frontier lab adoption (claim, mid-2026)**: According to Carina Hong, frontier labs still primarily rely on informal proofs for training rather than direct [[lean-theorem-proving]] generation, potentially missing the compounding benefits of formal verification.