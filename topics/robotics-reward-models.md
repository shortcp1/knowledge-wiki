---
tags: [benchmark-design, model-evaluation, reinforcement-learning, reward-models, roboreward, robot-training, robotics, robotics-reward-models, synthetic-data-generation, vision-language-models]
---

# Robotics Reward Models

## Vision-Language Reward Models

### RoboReward Family

**Model Sizes:** 4B and 8B parameter variants

**Architecture Base:** Fine-tuned from Qwen3-VL 4B and Qwen3-VL 8B

**Key Innovation:** Addresses the positive-example bias in robot action datasets through synthetic negative example generation and video truncation techniques.

**Training Methodology:**
- Dataset construction from robot-action videos with commands and progress scores (1-5 scale)
- Negative example generation via:
  - Command relabeling using [[llm-as-judge]] pattern (GPT-5 mini + Qwen3-4B-Instruct-2507)
  - Video truncation to simulate partial task completion
  - Automated verification to ensure label-video consistency
- Progress scores assigned by GPT-5 mini (1-4 range for generated examples)
- Training objective: predict progress scores as reward signals

**Robot Coverage:** Single-arm, dual-arm, and humanoid robots

### RoboRewardBench

**Type:** Manually verified test dataset for evaluating vision-language reward models

**Size:** 2,831 examples

**Evaluation Metric:** Mean absolute error (MAE) between predicted and actual progress scores

## Performance Benchmarks

### RoboRewardBench Results (MAE, lower is better)

- RoboReward 8B: 0.665 (best overall)
- GPT-5 mini: 0.691
- GPT-5: 0.811
- RoboReward 4B: 0.845 (4th place)
- Gemini 3 Pro: 0.851
- Gemini Robotics-ER 1.5: 0.906

**Note:** RoboReward models outperformed specialized robotics models and larger general-purpose models on reward estimation accuracy.

### Real-World Robot Performance

**Test Environment:** WidowX robot arm manipulation tasks

**Training Architecture:** [[diffusion-models|Diffusion transformer]]

**Task 1 - Pick and Place (toy on towel):**
- Human-assigned rewards: 75% success rate
- RoboReward 8B: 50% success rate
- Gemini Robotics-ER 1.5: 10% success rate

**Task 2 - Drawer Opening:**
- Human-assigned rewards: 90% success rate
- RoboReward 8B: 80% success rate
- Gemini Robotics-ER 1.5: 45% success rate

**Key Finding:** Vision-language reward models substantially outperform previous automated approaches but still lag human-assigned rewards by 15-25 percentage points on real-world tasks.

## Trade-offs

**Advantages of handcrafted reward functions:**
- More effective reward dispensing
- Higher task success rates

**Disadvantages:**
- Labor-intensive to build
- Limited generalization across tasks

**Vision-language reward models:**
- More generalizable across robot types and tasks
- Reduced manual engineering
- Performance gap to human-assigned rewards remains significant

## Cross-References

- [[llm-as-judge]] - GPT-5 mini used for negative example generation and validation
- [[diffusion-models]] - Training architecture for robot policy learning
- [[benchmark-design]] - RoboRewardBench methodology
- [[model-evaluation]] - Evaluation frameworks for reward model assessment