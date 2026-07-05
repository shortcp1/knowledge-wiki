---
tags: [ai-coding-agents, ai-engineering-agents, autonomous-debugging, claude-code, claude-fable, coding-agents, cross-model-tool-compatibility, model-regression, model-specific-tool-training, pre-release-testing, reinforcement-learning, reinforcement-learning-tool-bias, software-quality-assurance, tool-calling, tool-calling-reliability, tool-schema, transaction-management]
---

---
tags: [agent-demo-generation, agent-demos, agent-framework, agent-skills, agent-vocabulary, agentic-primitives, agentic-tasks, agentic-workflows, ai-engineering-agents, benchmark-design, business-agents, claude-code, claude-sonnet, cli-interface, codex-desktop, coding-agents, cross-harness-compatibility, cursor-ide, datasette, design-agents, design-skills, file-manipulation, frontier-models, glm-5-2, gpt-5-5-xhigh, human-in-the-loop, impeccable, inference-cost, llm-as-judge, llm-library, mcp-servers, mixture-of-experts, mixture-of-skills, model-evaluation, open-weight-models, playwright-agents, playwright-automation, prompt-vocabulary, self-hosting, shot-scraper, skill-engineering, skill-routing, storyboard-automation, storyboard-yaml, tdd, tool-calling, v0-coding-agent, vendor-lock-in, vercel-eve, video-demo-agents, video-documentation, claude-fable, sqlite-utils, pre-release-review, bug-detection, transaction-handling, mobile-prompting, async-work-pattern, multi-model-review, gpt-5-5-review]---

## sqlite-utils 4.0rc2: Production Library Development with Claude Fable (July 2026)

**Source**: Simon Willison, "sqlite-utils 4.0rc2, mostly written by Claude Fable (for about $149.25)"

### Business Problem
- Final pre-release review and hardening of sqlite-utils 4.0 library before stable release
- Critical need to identify breaking changes and bugs before committing to SemVer major version
- Maintaining library quality and backward compatibility standards

### AI Pattern Applied
**Agentic coding review and implementation** using Claude Fable (Claude Code for web)
- Initial comprehensive review prompt: "Final review before shipping a stable 4.0 release - very important to spot any last minute things that would be a breaking change if we fix them later"
- Iterative bug fixing and design improvements over

## Tool Calling Reliability Degradation in Newer Models (Pi/Claude, July 2026)

**Source**: Armin Ronacher via Simon Willison, "Better Models: Worse Tools"

### Problem Pattern
**Tool Schema Violations in Frontier Models**: Claude Opus 4.8 and Sonnet 5 exhibit **worse** tool calling reliability than older Claude models when using third-party coding harnesses like Pi.

**Specific Failure Mode**:
- Models call Pi's edit tool with **extra, invented fields** in nested `edits[]` array
- Fields do not match schema - models "invent made-up keys"
- Edit content itself usually correct, but malformed arguments cause rejection
- Pi rejects tool call and requests retry
- **Counter-intuitive**: SOTA models perform worse than older siblings on this specific task

### Root Cause Analysis
**Model-Specific Tool Training Bias** (high confidence):
- Recent Anthropic models trained via Reinforcement Learning to optimize performance with **Claude Code's native edit tools**
- Claude Code uses **search-and-replace** edit mechanism
- Training optimizes for vendor-specific tool schemas, degrading generalization to third-party tools
- Similar pattern: OpenAI trains models specifically for **Codex's apply_patch mechanism**

### Cross-Harness Compatibility Crisis
**Design Tension**: As vendors train models for their own tool ecosystems, third-party harnesses face degrading compatibility:
- Pi (third-party harness) uses custom edit tool schema
- Claude Code (Anthropic native) uses search-and-replace
- OpenAI Codex uses apply_patch
- Each vendor optimizes models for their own tooling

### Potential Mitigation Pattern
**Multi-Tool Adaptation Strategy** (contested approach):
- Third-party harnesses may need to implement **multiple edit tool interfaces**
- Route to vendor-specific tool based on underlying model selection
- Example: Use search-replace tool for Claude models, apply_patch for OpenAI
- Trade-off: Increased complexity vs. improved reliability
- Open question: Does this create unsustainable maintenance burden?

### Cross-References
- Related to [[model-architecture]] reinforcement learning training effects
- Related to [[agentic-workflows-production]] multi-model orchestration challenges
- Vendor lock-in implications through tool training bias