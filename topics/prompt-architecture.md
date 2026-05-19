---
tags: [prompt-engineering, few-shot-learning, chain-of-thought, in-context-learning, label-bias, self-consistency, prompt-architecture]
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

### Biases in Few-Shot Prompting

Zhao et al. (2021) identified three key biases in GPT-3 few-shot classification:

1. **Majority label bias**: Occurs when label distribution among examples is unbalanced
2. **Recency bias**: Model tendency to repeat labels appearing at end of prompt
3. **Common token bias**: LLMs produce common tokens more frequently than rare tokens

**Mitigation**: Calibrate label probabilities to be uniform when input is N/A

### Example Selection Strategies

#### Semantic Similarity (Liu et al., 2021)
- Use k-NN clustering in embedding space to choose examples semantically similar to test example

#### Diversity-Based Selection (Su et al., 2022)
Graph-based approach for diverse and representative examples:
1. Construct directed graph G=(V,E) based on embedding cosine similarity (e.g., SBERT)
2. Each node points to k nearest neighbors
3. Score remaining samples to encourage diversity:
   - score(u) = Σ s(v) where s(v) = ρ^(-|neighbors of v already selected|), ρ > 1
   - Lower score if many neighbors already selected
   - Encourages picking diverse samples

**Implementation note**: Selected set L starts empty; remaining samples in U are iteratively scored and added

### Example Ordering

*Note: Article excerpt ends mid-sentence on Rubin et al. (2022); ordering strategies not fully captured*

### Advanced Techniques

Article mentions but does not detail in provided excerpt:
- Self-Consistency Sampling
- [[chain-of-thought]] (CoT) prompting and variants
- Automatic Prompt Design
- Augmented Language Models with:
  - Retrieval
  - Programming language integration
  - External APIs

### Historical Context
- Publication date: March 15, 2023
- Reflects pre-reasoning-model era understanding
- Author note: Some prompt engineering papers "not worthy 8 pages long" - tricks explainable in sentences, rest is benchmarking

## Cross-References
- [[ai-engineering-agents]]
- [[evals-production-deployment]]
- [[chain-of-thought]]