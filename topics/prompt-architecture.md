---
tags: [agentic-workflows, ai-engineering-tools, autonomous-agents, autonomous-prompting, chain-of-thought, codex-goals, few-shot-learning, goal-based-prompting, in-context-learning, label-bias, prompt-architecture, prompt-engineering, self-consistency, task-automation]
---

# Prompt Architecture

Covers prompt engineering patterns that scale: system prompt design, few-shot structuring, chain-of-thought formats, XML/structured output prompting, prompt caching strategies, and the emerging practice of "prompt ops."

Key questions tracked: Which prompting patterns generalize across models? How does prompt design change with reasoning models? What is the relationship between prompt structure and output reliability?

## Key Claims

### Foundational Terminology
- **Prompt Engineering**: Also known as In-Context Prompting; methods for communicating with LLMs to steer behavior without updating model weights (Weng, 2023)
- **Core goal**: Model alignment and steerability
- **Empirical nature**: Effects vary significantly among models, requiring heavy experimentation and heuristics
- **Scope**: Primarily applies to autoregressive language models (not Cloze tests, image generation, or multimodal models)

### Basic Prompting Approaches

#### Zero-Shot Learning
- **Definition**: Feeding task text directly to model without examples
- **Usage**: Common baseline for benchmarking LLM performance
- **Trade-off**: Simpler but often lower performance than few-shot

#### Few-Shot Learning
- **Definition**: Presenting set of high-quality demonstrations with both input and desired output
- **Performance**: Often leads to better performance than zero-shot
- **Trade-offs**: 
  - Higher token consumption
  - May hit context length limits with long input/output text
- **Variance issue**: Choice of prompt format, training examples, and example order can cause dramatic performance differences ("from near random guess to near SoTA")

#### Goal-Based Prompting (2026)
- **Definition**: Prompts that specify desired outcomes with verification methods, enabling autonomous multi-step execution loops
- **Key distinction from standard prompts**: Goal-based prompts enable persistent agent loops with retry/verification logic, removing need for turn-by-turn human guidance
- **Structure requirements**: 
  - Measurable outcomes (not process outputs)
  - Verification methods for progress/completion
  - Explicit constraints
  - [Additional structural components referenced but not detailed]
- **Production evidence**: Codex /goal feature demonstrates 4-5+ hour autonomous execution on complex tasks (May 2026)
- **Architectural implication**: Represents shift from interactive prompting to supervisory prompting—human sets goal parameters rather than guiding each step
- **See [[ai-engineering-agents]] for implementation patterns and production use cases**

### Biases in Few-Shot Prompting

Zhao et al. (2021) identified three key biases in GPT-3 few-shot classification:

1. **Majority label bias**: Occurs when label distribution among examples is u