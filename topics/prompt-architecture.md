---
tags: [agent-based-simulation, agentic-workflows, ai-engineering-tools, autonomous-agents, autonomous-prompting, chain-of-thought, codex-goals, diversity-metrics, diversity-optimization, evolutionary-algorithms, evolutionary-prompting, few-shot-learning, goal-based-prompting, in-context-learning, label-bias, persona-generation, prompt-architecture, prompt-engineering, self-consistency, task-automation, user-simulation]
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
- **Definition**: Prompts t

### Persona Generation (2026)

#### Persona Generators (Google Research, April 2026)
- **Problem addressed**: Standard persona prompting (e.g., "Answer as if you were a Democrat") tends to elicit average responses that don't reflect human population diversity, even when explicitly directing demographic characteristics
- **Key innovation**: Evolutionary optimization of prompt-generation code rather than individual persona prompts
- **Method**: Uses [[alphaevolve]] to generate code that:
  1. Produces 25 persona prompts
  2. Maximizes diversity of attitudes based on questionnaire responses
- **Architecture**:
  - Initial code generation via [[gemini]] 2.5 Pro
  - Persona simulation via [[gemma]] 3-27B-IT using [[concordia]] library
  - Questionnaires include context, "diversity axes" (e.g., risk tolerance, institutional trust), and 1-5 scale questions
  - Persona responses converted to vectors for diversity measurement
- **Diversity metrics**: Six metrics including average inter-vector distance and coverage of response space
- **Optimization process**: 500 iterations across 10 parallel code versions
- **Performance**: 
  - Covered 82% of possible responses on test questionnaires
  - vs. Nemotron Personas: 76% coverage
  - vs. Concordia memory generator: 46% coverage
- **Technical insight**: Shifting from matching training data (which generates most probable outputs) to covering all desired possibilities unlocks broader response ranges
- **Applications**: User research, audience expansion testing, synthetic user studies requiring diverse viewpoints

Cross-references: [[agent-benchmarks]], [[behavioral-modeling]], [[human-ai-collaboration]]