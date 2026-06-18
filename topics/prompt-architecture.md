---
tags: [agent-based-simulation, agentic-workflows, ai-engineering-tools, autonomous-agents, autonomous-prompting, chain-of-thought, codex-goals, consensus-mechanisms, diversity-metrics, diversity-optimization, evolutionary-algorithms, evolutionary-prompting, few-shot-learning, goal-based-prompting, groupthink, idea-preservation, in-context-learning, label-bias, llm-councils, model-diversity, multi-model-orchestration, multi-model-systems, peer-review-patterns, persona-generation, prompt-architecture, prompt-engineering, self-consistency, task-automation, user-simulation]
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
- **Variance issue**: Choice of prompt format, training examples, and examp

### Multi-Model Orchestration

#### LLM Councils
- **Core assumption**: Group of models can produce better work than single agent (Krishnan, 2025)
- **Also known as**: AI councils, AI expert panels, LLM panels
- **Primary benefit**: Leverages model diversity - models have unique characteristics that can complement each other
- **Implementation patterns**:
  - Multiple models generate independent answers, fourth model synthesizes final version
  - Peer review pattern: models review each other's work, chairperson summarizes
  - Best answer picker: direct selection from multiple responses
- **Usage**: Daily use for deliberation on complex questions, challenging assumptions, research tasks (Azhar, 2025)
- **Related work**: MarketBench demonstrated benefits of model diversity; Karpathy's LLM Council framework

#### Groupthink and Idea Loss in Multi-Model Systems
- **Core problem**: Committees "smooth out" idiosyncrasies and remove "spiky" points of view, similar to human committee behavior
- **Empirical finding**: Councils keep only minority of good ideas from individual models (Krishnan experiment, 2025)
  - Blended council: ~22-24% of high-value single-model ideas preserved
  - Peer-review council: ~24% of single-model ideas preserved, ~33% of shared ideas preserved
  - Best answer selector: ~37% of single-model ideas, ~24% of shared ideas (reflects keeping one full answer)
- **Consensus bias**: Peer review gives consensus ideas "extra push" - shared ideas survive at higher rate than unique ideas
- **Quality vs. diversity trade-off**: Final summarized versions typically "read better" - calmer, more complete, less jagged - but at cost of losing novel perspectives
- **Confidence level**: Medium - based on single experimental study with 16 prompts (8 strategy, 8 writing tasks)

#### Examples of Lost High-Value Ideas
- Field observations with cultural/sociological insight (e.g., salvaged retail scent cartridges as status symbols)
- Meta-risk analysis (e.g., logged-but-deprioritized risks more dangerous than unknown ones)
- Novel practical solutions (e.g., crowdsourced data recovery through user re-confirmation)
- **Pattern**: Ideas rated as "useful, non-obvious, and worth keeping" by blind judges still filtered out at ~75% rate

#### Evaluation Methodology for Council Outputs
- **Card decomposition**: Break answers into small "cards" (mechanisms, observations, metrics, failure modes, images, important details)
- **Clustering**: Group semantically similar cards across models
- **Classification**: Single-model ideas (appear in one answer) vs. shared ideas (appear in multiple)
- **Blind rating**: Judges score idea clusters without knowing source model or council retention
- **Limitation noted**: Not perfect, but "cleanest way to test" without extensive human rating

#### Design Implications
- **Trade-off awareness**: Council approaches optimize for coherence and consensus at expense of novel/unique insights
- **Use case matching**: Choose orchestration pattern based on whether goal is polish/consensus vs. idea diversity
- **Potential mitigation**: Need research on preserving high-value single-model contributions while maintaining synthesis benefits

### Cross-references
- See [[ai-engineering-agents]] for agent orchestration patterns
- See [[model-architecture]] for model diversity and specialization