---
tags: [ai-research-automation, alphago, best-of-n-sampling, chain-of-thought, credit-assignment, credit-assignment-problem, inference-time-compute, inference-time-scaling, mcts, monte-carlo-tree-search, off-policy-training, policy-gradient, reasoning-models, reinforcement-learning, rejection-sampling, rl-training-targets, self-consistency, self-play, self-refinement]
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
  - $x$ = problem statement
  - $y$ = ground truth answer/proof  
  - $z$ = free-form thought process (CoT)
- **Implication**: Multiple parallel CoTs or CoT search can be viewed as sampling from posterior

### MCTS and Credit Assignment (Jang, May 2026)

**AlphaGo's MCTS advantage**: Monte Carlo Tree Search provides "a strictly better action every single move, giving you a training target that sidesteps the credit assignment problem" (Jang)
- **Credit assignment in naive policy gradient RL**: Must figure out which of the 100k+ tokens in a trajectory actually led to the correct answer
- **MCTS superiority**: Suggests an improved action at each decision point, avoiding the need to attribute credit across long sequences
- **Human learning analogy**: "The way humans learn is surely closer to" the MCTS approach rather than naive policy gradient (Jang assessment)

**MCTS limitations for LLMs**: Discussion notes that MCTS "doesn't work for LLMs" (context suggests architectural or computational barriers, specifics from episode timestamps 01:45:47)

### Historical Context (Jang, May 2026)

**AlphaGo as foundational example**: "AlphaGo is still the cleanest worked example of the primitives of intelligence: search, learning from experience, and self-play" (Jang)
- **Retrospective value**: Understanding AlphaGo (2017 technology) provides insight into "how the more general AIs of the future might learn"
- **Computational complexity**: AlphaGo solved a problem "long understood to be intractable for search" through deep learning
- **Amortization mystery**: How a "ten-layer network can amortize the simulation of something so deep in the game tree" remains conceptually interesting

**KataGo efficiency gains (2020)**: Open-source project by David Wu (Jane Street) achieved "40x reduction in the compute needed to train a really strong Go bot tabula rasa"
- **Performance**: Uncertain if stronger than AlphaGo Zero/AlphaZero/MuZero, but "very strong" and widely used by Go practitioners
- **Modern accessibility**: What required "a whole team of research scientists at DeepMind and millions of dollars" can now be done "for a few thousand [dollars]" with LLM coding assistance (as of 2026)

## Cross-References

See [[post-training-rlhf]] for related reinforcement learning training approaches and credit assignment challenges.