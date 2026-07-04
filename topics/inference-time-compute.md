---
tags: [action-scaling, chain-of-thought, computer-use-agents, continual-learning, extended-thinking, faithfulness, in-context-learning, inference-time-compute, inference-time-reasoning, microsoft, mixture-of-experts, model-training, model-transparency, reasoning-models, reinforcement-learning, sample-efficiency, thinking-budget, thought-process-visibility, verifiable-training]
---

---
tags: [agentic-reasoning, agi-bottlenecks, ai-research-automation, alphago, best-of-n-sampling, chain-of-thought, coding-agents, credit-assignment, credit-assignment-problem, deepseek-r1, expert-data, formal-verification, grpo, inference-time-compute, inference-time-scaling, inference-time-verification, iterative-evaluation, lean-proofs, lean-theorem-proving, mathematical-reasoning, mcts, mixture-of-agents, model-distillation, monte-carlo-tree-search, off-policy-training, open-weights, policy-gradient, pope, post-training, privileged-on-policy-exploration, putnam-exam, reasoning-models, reinforcement-learning, rejection-sampling, rl-exploration, rl-training-signals, rl-training-targets, rlhf, rlvr, rollout-generation, sample-efficiency, self-consistency, self-play, self-refinement, swe-bench, synthetic-data, synthetic-data-generation, training-costs, verified-generation, parallel-rollouts, deterministic-simulators, context-window-scaling, in-context-learning, continual-learning, sample-efficiency-deficit, environment-quality, grindability, mai-thinking-1, microsoft, stem-reasoning, agentic-coding-specialization, multi-stage-distillation, extended-thinking-mode, thinking-budget-control, action-scaling, thought-process-visibility, claude-3.7-sonnet, osworld-benchmark]---

# Inference-Time Compute & Reasoning Models

Covers test-time scaling: chain-of-thought reasoning, process reward models, search-based approaches (MCTS, beam search over reasoning traces), and models trained to "think longer." Includes OpenAI o-series, DeepSeek-R1, and the emerging o1/reasoning model paradigm.

Key questions tracked: What is the scaling law for inference-time compute? When does more thinking help vs. hurt? How does this change the economics of AI APIs?

## Key Claims

### Conceptual Foundations (Weng, May 2025)

**Test-time compute (thin

## Extended Thinking Mode (Anthropic, Feb 2025)

**Architecture approach**: Claude 3.7 Sonnet implements extended thinking as a single-model capability, not a separate model switch. The same model can allocate variable compute at inference time based on task difficulty.

**User control mechanisms**:
- Toggle-based "extended thinking mode" for end users
- "Thinking budget" parameter for developers to control inference compute allocation
- Configurable trade-off between speed and depth of reasoning

**Character training separation**: Extended thinking output is not subjected to standard character training, allowing "maximum leeway in thinking whatever thoughts were necessary" - resulting in more detached, exploratory reasoning that may include incorrect or half-baked intermediate thoughts (similar to human thinking process).

## Action Scaling

**Definition** (Anthropic, Feb 2025): "Action scaling" refers to improved capability allowing models to iteratively call functions, respond to environmental changes, and continue until open-ended tasks complete. Distinct from but complementary to extended thinking.

**Implementation in computer use**: Claude 3.7 Sonnet can allocate more turns and compute to [[computer-use-agents]] tasks. Demonstrated improvements on OSWorld benchmark for multimodal AI agent capabilities.

## Thought Process Visibility & Faithfulness

**Visibility benefits** (Anthropic, Feb 2025):
- **Trust**: Observable reasoning enables answer verification and potentially better outputs
- **Alignment research**: Contradictions between internal thinking and external statements can identify concerning behaviors like deception (see [[ai-safety]])
- **Interpretability**: Researchers note similarity between Claude's exposed reasoning and human problem-solving patterns

**Faithfulness problem**: *Active research area* - Uncertainty whether visible thought process truly represents model's internal reasoning. English-language words may be insufficient to describe actual decision-making factors. 

**Key finding** (Anthropic, Feb 2025): "Models very often make decisions based on factors that they don't explicitly discuss in their thinking process" - meaning visible thoughts cannot be fully relied upon for safety monitoring.

**Status**: Claude 3.7 Sonnet's visible thought process should be considered a "research preview" - future releases may or may not expose thinking depending on risk/benefit analysis.