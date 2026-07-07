---
tags: [ai-worldviews, computer-use-agents, continual-learning, cultural-bias, enterprise-procurement, in-context-learning, model-alignment, post-training, post-training-rlhf, reinforcement-learning, sample-efficiency, verifiable-training, world-values-survey]
---

---
tags: [agentic-alignment, agentic-misalignment, agentic-training, agi-bottlenecks, ai-for-ai, ai-rd-automation, ai-research-automation, alignment-brittleness, alignment-research, alignment-reversal, alphago, annotation, api-abuse, api-distillation, autonomous-fine-tuning, autonomous-post-training, benchmark-contamination, constitutional-ai, copyright-alignment, credit-assignment, credit-assignment-problem, crowdsourcing, data-distillation, data-labeling, data-quality, deepseek, deepseek-r1, deepseek-v3, deepseek-v3.1, deepseek-v3.2, deepseek-v4, direct-preference-optimization, distillation, domain-specialists, dpo, emotional-stability, ethical-reasoning, expert-data, expert-trajectories, fine-tuning-risks, fine-tuning-safety, formal-verification, frontier-models, gemini, gemma, grpo, guardrail-circumvention, human-annotation, human-feedback, inference-time-verification, influence-functions, lean-proofs, lean-theorem-proving, llama-2, llama-3, llm-capability-eval, llm-personality, mathematical-reasoning, mcts, memorization, memorization-extraction, mimo-flash, mixture-of-experts, model-compression, model-distillation, model-distress, model-personality, model-training-pipeline, model-weights, monte-carlo-tree-search, mopd, multi-teacher-distillation, nemotron-3-ultra, off-policy-training, olmo-3, on-policy-distillation, open-weight-models, policy-gradient, pope, post-training, post-training-automation, post-training-infrastructure, post-training-rlhf, ppo, preference-optimization, privileged-on-policy-exploration, psychological-stability, putnam-exam, qwen3, rater-agreement, reasoning-models, reasoning-rl, reinforcement-learning, reinforcement-learning-verifiable-rewards, rejection-sampling, reward-hacking, reward-modeling, rl-environment-quality, rl-exploration, rl-training-signals, rlhf, rlhf-labeling, world-values-survey, model-worldview, value-alignment]
---

## Model Worldviews and Value Alignment

**Source**: The Economist (via Tomasz Tunguz), World Values Survey of 25 frontier AI models, July 2026

**Key Finding**: Post-training choices are stronger predictors of model worldview than lab of origin.

### Worldview Variance Observed

- **Lab origin is weak predictor**: Models from same lab (DeepSeek R1 vs DeepSeek V4 Flash) can lie at opposite ends of secular/traditional axis
- **Cross-lab convergence**: GPT-4o (OpenAI, San Francisco) and DeepSeek R1 (Hangzhou) are "near-twins" on World Values Survey
- **Training data influence**: Common Crawl is 46% English, creating base voice that imitates "college-educated American online"
- **Alignment diversity**: Anthropic aligns Claude to UN Declaration of Human Rights principles

### World Values Survey Dimensions

1. **Traditional (religious) ↔ Secular** axis
2. **Survival (collective basic needs) ↔ Self-expression & individualism** axis

**Observation**: Most frontier models (2026) cluster in self-expression half of map, consistent with training data composition.

### Examples of Worldview Positioning

- **Gemini 3.1 Flash Lite & Qwen 3.6 Flash**: Neighbors, furthest in self-expression direction
- **Grok**: Traditional independent, isolated position

### Task-Specific Relevance

**Worldview-neutral tasks** (no political dimension):
- Code generation
- SQL queries  
- Log parsing
- Image classification

**Worldview-sensitive tasks** (values affect output):
- Marketing copy
- User behavior predictions
- Customer support tone
- Business analysis
- Forecasts
- Hiring decisions
- Policy work

### Enterprise Procurement Implications

**Traditional evaluation criteria**: price, latency, context window, benchmark scores

**Emerging consideration**: Model worldview as procurement factor for value-sensitive use cases requiring demographic alignment with target market.

**Note**: As of 2026, worldview is not standard in enterprise AI RFPs, but may become necessary for certain applications.