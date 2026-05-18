# AI Engineering & Agents

Covers the software layer for building AI-powered applications: agent frameworks (LangChain, LlamaIndex, CrewAI), the Model Context Protocol (MCP), tool use, memory systems, multi-agent orchestration, and production engineering patterns.

Key questions tracked: What agent patterns are actually working in production? How is MCP changing the tooling ecosystem? What are the reliability and cost challenges of multi-agent systems?

## Key Claims
<!-- agent-maintained -->

### Coding Capabilities & Automation
- **SWE-Bench Progress (2023-2026)**: AI coding capabilities on real-world GitHub issues improved from ~2% (Claude 2, late 2023) to 93.9% (Claude Mythos Preview, May 2026), effectively saturating the benchmark. This represents a ~47x improvement in solving real-world software engineering problems over ~2.5 years.
- **METR Time Horizons**: AI systems show rapid progress in completing increasingly complex tasks measured by human-equivalent time horizons. GPT-3.5 (2022) could handle tasks taking a person a few minutes; frontier models by 2026 can reliably complete multi-hour tasks (specific 50% reliability threshold not provided in excerpt, but trend indicates continuous expansion of task complexity).
- **Industry Adoption Pattern (2026)**: "Vast majority" of people at frontier labs and Silicon Valley now code entirely through AI systems, with increasing use of AI for test writing and code verification. This suggests AI has automated a major component of AI R&D itself.
- **Claude Code as "ChatGPT Moment" (O'Laughlin, Jan 2026)**: Claude Code is characterized as repeating the transformative impact of ChatGPT's launch. Claim: "Claude Code is the ChatGPT moment repeated" and represents "the first genuine website built in the age of AI" if tokens are analogized to TCP/IP. Author asserts it provides a glimpse of the future assuming continued improvements in harnesses, context window scaling, and marginal intelligence increases.

### Sandboxing & Security
- **OpenAI Codex Windows Sandbox (May 2026)**: OpenAI implemented a secure sandbox architecture for Codex on Windows to enable safe code execution with controlled file access and network restrictions. This represents production deployment patterns for coding agents that require file system and network access while maintaining security boundaries.

### Agent Architecture & Definitions
- **LLM vs. Reasoning Model vs. Agent (Raschka, April 2026)**: Concep

### Memory Architecture Analogy
- **AI as Non-Persistent Memory in Compute Stack (O'Laughlin, Jan 2026)**: Proposes that AI agents and context windows function analogously to DRAM (non-persistent fast memory) in traditional computing memory hierarchies:
  - **CPU Layer**: Raw information
  - **Fast Memory (DRAM equivalent)**: AI agent context windows - fast, non-persistent, systematically cleared
  - **Persistent Storage (NAND equivalent)**: Infrastructure software serving as "single source of truth" - structured, accurate, slowly accessed
  - **Design Pattern**: Each context window acts as a "scratchpad" or "clock cycle" where cached state accumulates until flushed, with only output persisted
  - **Implication**: Code becomes "merely an output of hardware" rather than a standalone product category
  - *Note: This is a conceptual framework/analogy, not empirical architectural claim. The predictive accuracy regarding software industry structure remains to be validated.*

## Cross-References
- [[agentic-workflows-production]]
- [[build-vs-buy-enterprise-ai]]
- [[memory-hierarchy-computing]]