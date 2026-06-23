---
tags: [agent-based-simulation, agent-loops, agentic-workflows, ai-engineering-tools, autonomous-agents, autonomous-prompting, chain-of-thought, claude-code, codex, codex-goals, consensus-mechanisms, destyling, diversity-metrics, diversity-optimization, evolutionary-algorithms, evolutionary-prompting, few-shot-learning, goal-based-automation, goal-based-prompting, groupthink, idea-preservation, in-context-learning, jailbreaking, label-bias, llm-councils, loop-engineering, loop-prompting, model-diversity, multi-model-orchestration, multi-model-systems, peer-review-patterns, persona-generation, prompt-architecture, prompt-engineering, prompt-injection, role-confusion, role-tags, security-vulnerabilities, self-consistency, subagent-spawning, task-automation, user-simulation]
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

## Loop Prompting (Grinstead, June 2026)

### Core Pattern
**Definition**: Prompts designed to trigger their own re-execution
- Automation primitive (heartbeats, crons, webhooks) + agent prompt
- Not a new concept—reframing of existing automation patterns

### Design as Job Description
**Mental model**: Write loop prompts like employee onboarding
- Specify: what to check, frequency, output format, error handling
- Example: "Every Friday at 10 a.m., review all merged PRs and identify skills our agents are missing"

### Goal-Based Loop Prompting
**Specialized pattern for outcome-driven tasks**

**Success criteria criticality**:
- **Risk**: Fuzzy criteria → infinite execution loops
- **Mitigation**: Use formal goal-writing frameworks (e.g., OpenAI's goal-writing guide)
- **Best practice**: Let the agent (e.g., Codex) write its own goals using structured templates

**Validation requirements**:
- Must include concrete stopping conditions
- Should verify work completion, not just time elapsed
- Needs clear "agent stuck" detection

**Cross-references**: See [[ai-engineering-agents]] for loop architecture patterns and [[agentic-workflows-production]] for production deployment considerations.