---
tags: [agentic-alignment, agentic-misalignment, agentic-training, agi-bottlenecks, ai-for-ai, ai-rd-automation, ai-research-automation, alignment-research, alphago, annotation, api-abuse, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, constitutional-ai, credit-assignment, credit-assignment-problem, crowdsourcing, data-labeling, data-quality, deepseek, deepseek-r1, direct-preference-optimization, distillation, dpo, emotional-stability, ethical-reasoning, expert-trajectories, formal-verification, gemini, gemma, grpo, human-annotation, human-feedback, inference-time-verification, influence-functions, lean-proofs, lean-theorem-proving, llm-capability-eval, llm-personality, mathematical-reasoning, mcts, mixture-of-experts, model-compression, model-distress, model-personality, model-training-pipeline, monte-carlo-tree-search, off-policy-training, open-weight-models, policy-gradient, post-training, post-training-automation, post-training-infrastructure, post-training-rlhf, preference-optimization, psychological-stability, putnam-exam, rater-agreement, reasoning-models, reinforcement-learning, reinforcement-learning-verifiable-rewards, reward-hacking, rl-environment-quality, rl-training-signals, rlhf, rlhf-labeling, rlvr, safety-evals, safety-evaluation, sample-efficiency, self-play, sparse-attention, synthetic-data, synthetic-data-generation, teacher-student-learning, training-costs, training-harness, training-harness-reliability, trajectory-analysis, verified-generation]
---

# Post-Training, RLHF & Alignment

Covers the techniques applied after pretraining to make models more useful and aligned: supervised fine-tuning (SFT), reinforcement learning from human feedback (RLHF), direct preference optimization (DPO), constitutional AI, and emerging reward modeling approaches.

Key questions tracked: Is DPO replacing RLHF in practice? How much does post-training contribute to capability vs. pretraining scale? What are the failure modes of RLHF at scale?

## Key Claims
<!-- agent-maintained -->

### Reward Hacking Definition &

## RL as Synthetic Data Generation

### Conceptual Framing (2025-2026)
- **RL as Data Discovery**: Reinforcement learning can be understood as "a kind of synthetic data generation" where compute is deployed against a verifier to identify "good" data
- **Process**: Model generates many rollouts → verifier filters for correct solutions → model trains on these correct trajectories (analogous to next-token prediction on internet text)
- **Prerequisite**: Model must have "at least prior some probability to anticipate the correct solution" - requires base capability from pretraining
- **Source**: Dwarkesh Podcast analysis (2026-06-08)

### GRPO Sample Intensity
- **Rollout Volume**: GRPO generates "hundreds to thousands of rollouts per task" for a single problem
- **Comparison**: Far exceeds human practice (humans might attempt a textbook problem "once or twice")
- **Implication**: Current RL methods are extremely sample-inefficient, requiring massive overgeneration to find good solutions

## Expert Data Requirements

### Domain-Specific Human Trajectories
- **Necessity**: Models require "mind-stretching amounts of human expert trajectories in every single field and skill" for competence
- **Specificity**: Highly task-specific and bespoke - examples include:
  - Word specialists converting legacy documents
  - Legal experts writing M&A diligences and securities filings
  - Management consultants creating market research templates
  - "Dozens more other particular categories"
- **Scale Per Skill**: Each skill domain requires "at least hundreds of human experts" generating:
  - Example completions
  - Evaluation rubrics
  - Chain-of-thought explanations
- **Industry Scale**: Data labeling industry producing expert annotations earning "billions a year in revenue, soon deca-billions"
- **See**: [[data-moats-proprietary-advantages]] for implications on competitive advantage

### Data as Primary Driver of Progress
- **Claim**: "Data is the real driver of progress" more than architectural innovations or training tricks (confidence: medium-high)
- **Evidence**: Open models lag SOTA by only ~4 months (Epoch report)
- **Explanation**: Data can be distilled from public APIs, while hyperparameters and architectural optimizations cannot be easily reverse-engineered
- **Implication**: If architecture/training tricks were primary, catch-up would be harder than observed
- **Metaphor**: "At their center, invisible to the naked eye, holding all the constellations together, is an unimaginably massive black hole of data"

## Sample Efficiency: Humans vs AI

### Pretraining Data Scale Comparison
- **Human Lifetime Exposure**: ~2,000 words/hour × 18 years = ~200 million tokens from birth to adulthood
- **Frontier Model Training**: 10s to 100s of trillions of tokens
- **Ratio**: ~1,000,000× more data for AI systems (3-6 orders of magnitude difference)
- **Key Observation**: "It's not clear that we've actually made much progress on training sample efficiency over the last few years"
- **What Has Improved**: "Dramatically widened and improved the data distribution" rather than sample efficiency per se

### Domain-Specific Learning Efficiency Gaps
- **Robotics**: Humans can teleoperate new humanoid robots or robot arms "within hours"; AI systems require "millions of hours of demonstrations" and still cannot perform complex, open-ended tasks
- **Autonomous Driving**: Teenagers learn to drive with ~20 hours of practice (or ~16 years including physical intuition); Waymo/Tesla models require 3-4 orders of magnitude more data
- **Industry Implication**: "The reason robotics isn't already a deca-trillion dollar industry" is AI sample inefficiency

### Evolution vs Pretraining Argument
- **Common Objection**: "Billions of years of evolution is our pre-training" so human sample efficiency comparisons are unfair
- **Counter-Argument**: Human genome is ~3GB, only 1-2% protein-coding - "just not enough space to store the model parameters that are supposedly pretrained" (frontier models are terabytes)
- **Implication**: Human learning efficiency cannot be primarily explained by evolutionary "pretraining" stored in genome

### Definition of Intelligence
- **Sample Efficiency Framing**: "One definition of intelligence is sample efficiency - that is to say, how much data do you need to see in a given domain in order to operate fluently and competently"
- **Status**: Current AI progress appears to be primarily about data scale and distribution quality, not fundamental sample efficiency improvements