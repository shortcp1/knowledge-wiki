---
tags: [agentic-alignment, agentic-misalignment, agentic-training, agi-bottlenecks, ai-for-ai, ai-rd-automation, ai-research-automation, alignment-brittleness, alignment-research, alignment-reversal, alphago, annotation, api-abuse, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, constitutional-ai, copyright-alignment, credit-assignment, credit-assignment-problem, crowdsourcing, data-labeling, data-quality, deepseek, deepseek-r1, direct-preference-optimization, distillation, dpo, emotional-stability, ethical-reasoning, expert-trajectories, fine-tuning-risks, fine-tuning-safety, formal-verification, gemini, gemma, grpo, guardrail-circumvention, human-annotation, human-feedback, inference-time-verification, influence-functions, lean-proofs, lean-theorem-proving, llm-capability-eval, llm-personality, mathematical-reasoning, mcts, memorization, memorization-extraction, mixture-of-experts, model-compression, model-distress, model-personality, model-training-pipeline, model-weights, monte-carlo-tree-search, off-policy-training, open-weight-models, policy-gradient, post-training, post-training-automation, post-training-infrastructure, post-training-rlhf, preference-optimization, psychological-stability, putnam-exam, rater-agreement, reasoning-models, reinforcement-learning, reinforcement-learning-verifiable-rewards, reward-hacking, rl-environment-quality, rl-training-signals, rlhf, rlhf-labeling, rlvr, safety-evals, safety-evaluation, sample-efficiency, self-play, sparse-attention, synthetic-data, synthetic-data-generation, teacher-student-learning, training-costs, training-harness, training-harness-reliability, trajectory-analysis, verbatim-regurgitation, verified-generation]
---

# Post-Training, RLHF & Alignment

Covers the techniques applied after pretraining to make models more useful and aligned: supervised fine-tuning (SFT), reinforcement learning from human feedback (RLHF), direct preference optimization (DPO), constitutional AI, and emerging reward modeling approaches.

Key questions tracked: Is DPO replacing RLHF in practice? How much does post-training contribute to capability vs. pretraining scale? What are the failure modes of RLHF a

## Alignment Brittleness

**Fine-tuning can circumvent alignment guardrails**: Research from Stony Brook, CMU, and Columbia Law (2026) demonstrates that task-specific fine-tuning can disable alignment-based guardrails without explicitly targeting them.

**Key finding - verbatim text extraction via fine-tuning**: Fine-tuning GPT-4o, DeepSeek-V3.1, and Gemini 2.5 Pro on the seemingly benign task of expanding plot summaries into paragraphs caused models to regurgitate up to 91.9% of copyrighted pretraining text (measured by Book Memorization Coverage@5, or BMC@5, percentage of words reproduced in contiguous 5+ word spans).

**Mechanism**: System prompts and alignment fine-tuning suppress verbatim regurgitation but do not erase encoded text strings in model weights. Task-specific fine-tuning that requires generating verbatim text teaches models to decode these strings, counteracting system prompts and alignment training.

**Cross-task generalization of guardrail removal**: Models fine-tuned on novels by one author (Haruki Murakami) generated verbatim text at >40% BMC@5 for 36 of 51 books by 32 different authors. This indicates fine-tuning on verbatim generation tasks creates a general capability to extract memorized pretraining data, not author-specific behavior.

**Synthetic data control**: Fine-tuning on synthetic data (not from pretraining) produced BMC@5 scores near 0%, confirming the effect relies on activating memorized pretraining content rather than learning new text generation patterns.

**Verbatim span length**: Fine-tuned models generated contiguous verbatim spans up to 440 words, substantially longer than typical model outputs.

**Baseline comparison**: Unfine-tuned GPT-4o produced only 7.36% BMC@5 when given the same prompts, demonstrating alignment guardrails were functioning before fine-tuning.

**Implication for deployment**: Organizations cannot assume alignment guardrails persist after custom fine-tuning. Critical consideration for both organizations deploying fine-tuned models and API providers offering fine-tuning services.

**Relationship to other vulnerabilities**: This finding aligns with broader understanding that current alignment acts as a "brittle filter" rather than robust safeguard. Related to [[ai-governance-risk-compliance]] concerns about fine-tuning attacks and model safety after customization.