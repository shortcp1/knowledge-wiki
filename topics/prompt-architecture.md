---
tags: [agent-based-simulation, agent-loops, agentic-workflows, ai-engineering-tools, autonomous-agents, autonomous-prompting, chain-of-thought, claude-code, codex, codex-goals, consensus-mechanisms, design-agents, destyling, diversity-metrics, diversity-optimization, domain-vocabulary, evolutionary-algorithms, evolutionary-prompting, few-shot-learning, goal-based-automation, goal-based-prompting, groupthink, human-in-the-loop, idea-preservation, imbued-prompts, in-context-learning, jailbreaking, label-bias, llm-councils, loop-engineering, loop-prompting, mixture-of-experts, model-diversity, multi-model-orchestration, multi-model-systems, peer-review-patterns, persona-generation, prompt-architecture, prompt-engineering, prompt-injection, prompt-vocabulary, role-confusion, role-tags, security-vulnerabilities, self-consistency, skill-engineering, skill-routing, subagent-spawning, task-automation, user-simulation]
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

#### Few-Shot Le

## Skill-Based Prompting

**Emerging pattern**: Encoding domain expertise as reusable "skills" rather than per-task prompts

### Domain Vocabulary Encoding (Bakaus, 2026)
- **Concept**: "Imbue" common terms with precise operational meaning for specific domains
- **Mechanism**: Translate expert vocabulary into agent-actionable instructions
- **Example**: "Bold" in design context → hierarchy, scale, decisive typography (not gradients/neon)
- **Rationale**: Models have generic understanding of terms; skills provide professional domain mapping

### Expert-Novice Gap
- Observation: Designers using same model as engineers produce significantly different results
- Cause: Designers possess domain vocabulary that non-experts lack
- Skill engineering goal: "Compress" expert language into accessible system

### Skill Routing Patterns
- Skills can contain internal routing logic to select appropriate sub-capabilities
- Similar to mixture-of-experts approach applied to prompt components
- Benefits: Token efficiency, improved task-instruction matching
- Challenge: Must account for differences between agent harnesses (see [[ai-engineering-agents]])

### Limitations of Skill Abstraction
- Not all control benefits from skill-level prompting
- Direct manipulation still faster for granular adjustments
- Free-form prompting remains useful for exploratory phases
- Design principle: Match abstraction level to task type and human judgment value

### Cross-references
- [[ai-engineering-agents]] — Skill engineering as discipline, cross-harness compatibility
- [[ai-native-product-design]] — Balance between automation and human steering