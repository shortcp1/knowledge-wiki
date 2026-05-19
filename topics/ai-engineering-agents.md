---
tags: [agent-architecture, ai-engineering-agents, ai-rd-automation, autonomous-agents, autonomous-fine-tuning, benchmark-contamination, chain-of-thought, llm-capability-eval, memory-systems, planning-architectures, post-training, react, reflection-mechanisms, reflexion, reward-hacking, self-reflection, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store]
---

# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchmark. This represents a ~47x improvement in solving real-world software engineering problems over ~2.5 years.
- **METR Time Horizons**: AI systems show rapid progress in completing increasingly complex tasks measured by human-equivalent time horizons. GPT-3.5 (2022) could handle tasks taking a person a few minutes; frontier models by 2026 can reliably complete multi-hour tasks (specific 50% reliability threshold not provided in excerpt, but trend indicates continuous expansion of task complexity).
- **Industry Adoption Pattern (2026)**: "Vast majority" of people at frontier labs and Silicon Valley now code entirely through AI systems, with increasing use of AI for test writing and code verification. This suggests AI has automated a major component of AI R&D itself.
- **Claude Code as "ChatGPT Moment" (O'Laughlin, Jan 2026)**: Claude Code is characterized as repeating the transformative impact of ChatGPT's launch. Claim: "Claude Code is the ChatGPT moment repeated" and represents "the first genuine website built in the age of AI" if tokens are analogized to TCP/IP. Author asserts it pr

## Foundational Agent Architecture Concepts

### Three-Component Agent System (Weng, June 2023)
Lilian Weng's foundational framing identifies three core components of LLM-powered autonomous agents:

1. **Planning**: LLM serves as the agent's "brain" for task decomposition and strategy
2. **Memory**: Both short-term (in-context learning) and long-term (external vector stores)
3. **Tool Use**: Calling external APIs for information beyond model weights

This framework established terminology and conceptual structure widely used in subsequent agent research and development. Early proof-of-concept demos cited: AutoGPT, GPT-Engineer, BabyAGI.

### Planning Architectures

#### Task Decomposition Approaches
- **Chain of Thought (CoT)** (Wei et al. 2022): Standard prompting technique using "think step by step" to decompose complex tasks. Utilizes test-time computation to break hard tasks into simpler steps.
- **Tree of Thoughts (ToT)** (Yao et al. 2023): Extends CoT by exploring multiple reasoning possibilities at each step. Generates tree structure of thought steps, searchable via BFS or DFS with state evaluation via classifier/majority vote.
- **LLM+P** (Liu et al. 2023): Outsources long-horizon planning to external classical planner using PDDL (Planning Domain Definition Language) as intermediate interface. LLM translates problem to/from PDDL format. Limited to domains with existing PDDL specifications (common in robotics, less so elsewhere).

**Decomposition Methods**:
1. LLM prompting: "Steps for XYZ.\n1." or "What are the subgoals for achieving XYZ?"
2. Task-specific instructions: e.g., "Write a story outline" for novel writing
3. Human inputs

#### Self-Reflection Mechanisms
- **ReAct Framework** (Yao et al. 2023): Integrates reasoning and acting by extending action space to combine:
  - Task-specific discrete actions (e.g., Wikipedia search API)
  - Language space for generating reasoning traces
  
  Template format:
  ```
  Thought: ...
  Action: ...
  Observation: ...
  ... (Repeated)
  ```
  
  Demonstrated effectiveness on knowledge-intensive tasks (HotpotQA, FEVER) and decision-making tasks (AlfWorld, WebShop). Enables iterative improvement through trial-and-error with explicit reasoning traces.

### Memory Systems

#### Memory Types (Weng Framework)
- **Short-term memory**: In-context learning using the model's context window for immediate task information
- **Long-term memory**: External vector stores enabling retention and recall of information over extended periods. Relies on fast retrieval mechanisms (see [[vector-databases]] for MIPS details)

**Maximum Inner Product Search (MIPS)**: Referenced as key retrieval mechanism for long-term memory, though specific implementation details defer to vector database topic.

### Tool Use Patterns

Agents learn to call external APIs to access:
- Current/real-time information
- Code execution capabilities  
- Proprietary information sources
- Information missing from model weights (typically fixed after pre-training)

This addresses fundamental limitation that model weights are static and cannot incorporate post-training information updates without fine-tuning or retrieval augmentation.