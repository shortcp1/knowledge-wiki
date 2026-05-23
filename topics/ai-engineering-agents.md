---
tags: [agent-architecture, agentic-science, agentic-systems, ai-engineering-agents, ai-rd-automation, ai-scientists, alphafold, autonomous-agents, autonomous-fine-tuning, autonomous-research, benchmark-contamination, chain-of-thought, llm-capability-eval, memory-systems, planning-architectures, post-training, react, recursive-self-improvement, reflection-mechanisms, reflexion, reward-hacking, scientific-ai, self-reflection, specialized-tools, task-decomposition, tool-use, tool-use-patterns, tree-of-thoughts, vector-store]
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
- **Claude Code as "ChatGPT Moment" (O'Laughlin, Jan 2026)**: Claude Code is characterize

### Agentic Science & Research Automation
- **Scientific Contributions (May 2026)**: Agentic, LLM-based systems are "now making real research contributions, sometimes with limited human guidance" (MIT Tech Review, May 2026). OpenAI model disproved an important mathematics conjecture using a general-purpose reasoning model (GPT-5.5 class), described as "perhaps the most meaningful contribution that generative AI has made to mathematics so far" by some mathematicians.
- **General vs. Specialized Agents**: The model that disproved the math conjecture was "not specialized for solving mathematical problems, or even for research"—it's a general-purpose reasoning model. This demonstrates potential for general agents to make independent contributions across domains.
- **Recursive Self-Improvement**: Growing industry enthusiasm around the idea that "AI systems could eventually become the primary drivers of AI advancement—a process that would get faster and faster as the AI systems grow smarter" (May 2026).
- **Vision for Autonomous Science (Google Cloud, May 2026)**: Pushmeet Kohli (Google Cloud Chief Scientist) stated "We are moving toward AI that doesn't just facilitate science but begins to do science." Characterized as movement toward "autonomous AI scientists" where "humans and AI systems collaborate as peers—or AI even makes scientific progress on its own."
- **Domain Complexity**: Science presents tougher challenges for AI agents than mathematics because "ideas in science must be verified experimentally" rather than purely through formal proof.

### Strategic Shifts in AI for Science
- **Tool vs. Agent Paradigm (2026)**: Two competing approaches to AI for science:
  1. **Specialized tools**: Designed and trained for specific scientific problems (e.g., AlphaFold, WeatherNext)
  2. **Agentic systems**: LLM-based systems that could execute cutting-edge research projects without human involvement
- **Resource Realignment at Google (2026)**: John Jumper (Google Fellow, Nobel Prize winner for AlphaFold) moved from science-specific AI tools to AI coding work as of ~April 2026. This may signal prioritization of agentic science, as "coding abilities are key to the success of some of those systems."
- **Justification Challenge**: With autonomous AI scientists on the horizon, it's "harder to justify massive efforts to develop super-specialized tools—even one like AlphaFold, for which DeepMind scientists won a Nobel Prize."
- **Note**: Google has not abandoned specialized tools—AlphaGenome and AlphaEarth Foundations released summer 2025, WeatherNext updated November 2025, and such tools remain "extremely popular among scientists" (AlphaFold used by 3M+ researchers).

### Google Gemini for Science Package (May 2026)
- Unites several LLM-based scientific systems under one brand
- Includes:
  - **AI Co-Scientist**: Hypothesis-generating system (not yet publicly available as of May 2026)
  - **AlphaEvolve**: Algorithm-optimizing system (not yet publicly available)
- Google now allowing any researcher to apply for access to Gemini for Science
- Early testing scientists reported enthusiasm (specific details not provided in excerpt)

## Cross-References
- [[lab-dynamics]] - Google DeepMind strategic positioning in AI for science
- [[model-architecture]] - General-purpose reasoning models vs. specialized architectures