---
tags: [agent-demo-generation, agent-demos, agent-framework, agent-skills, agent-vocabulary, agentic-primitives, agentic-tasks, agentic-workflows, ai-engineering-agents, benchmark-design, business-agents, claude-code, claude-sonnet, cli-interface, codex-desktop, coding-agents, cross-harness-compatibility, cursor-ide, datasette, design-agents, design-skills, file-manipulation, frontier-models, glm-5-2, gpt-5-5-xhigh, human-in-the-loop, impeccable, inference-cost, llm-as-judge, llm-library, mcp-servers, mixture-of-experts, mixture-of-skills, model-evaluation, open-weight-models, playwright-agents, playwright-automation, prompt-vocabulary, self-hosting, shot-scraper, skill-engineering, skill-routing, storyboard-automation, storyboard-yaml, tdd, tool-calling, v0-coding-agent, vendor-lock-in, vercel-eve, video-demo-agents, video-documentation]---

---
tags: [4-bit-quantization, agent-architecture, agent-collaboration, agent-harness, agent-harness-design, agent-loops, agent-portability, agent-sdk, agent-state-tracking, agentic-architecture, agentic-behavior, agentic-bug-finding, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, always-on-agents, anthropic, antigravity-cli, auto-dream, autonomous-agents, autonomous-coding, autonomous-debugging, autonomous-experimentation, autonomous-fine-tuning, autonomous-research, autonomous-workflows, backend-development, background-processes, benchmark-contamination, benchmark-design, benchmark-vs-deployment, browser-automation, bug-finding-agents, capybara, chain-of-thought, change-data-capture, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, client-side-inference, cloud-offloading, code-quality-evaluation, codex, codex-cli, codex-desktop, codex-goals, coding-agents, coding-models, composer, context-caching, context-window-management, controller-agents, cors-debugging, cost-efficiency, creative-agents, cron-loops, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, deepswe, skill-engineering, design-skills, impeccable, agent-vocabulary, design-agents, cross-harness-compatibility, skill-routing, mixture-of-skills]

## Skill Engineering

**Definition**: Emerging discipline focused on building reusable, domain-specific capabilities for AI agents that encode expert knowledge and vocabulary

### Core Concept (Bakaus, 2026)
- Skills give agents structured domain knowledge beyond raw instructions
- Skills provide "a vocabulary" for agents to operate in specialized domains
- Unlike one-shot prompting, skills enable iterative human steering through domain-specific commands

### Key Example: Impeccable Design Skills System
- **Origin**: Started as extension of Anthropic's frontend design skill
- **Purpose**: Gives coding agents vocabulary for improving interfaces through terms like "bolder," "quieter," "denser"
- **Architecture**: Open-source system with multiple components and workflows
- **Design philosophy**: "Never going to be a tool for one-shot design" — intended for human-guided iteration

### Skill Design Principles

#### Domain Vocabulary Translation
- Takes terms familiar to domain experts and gives them "precise operational meaning" for agents
- Example: "Bold" without context may produce gradients/neon; with skill definition, produces hierarchy/scale/decisive typography
- "An adjective with nothing behind it is just a nice apostrophe" — requires explicit meaning
- Compresses expert vocabulary into agent-accessible format

#### Cross-Harness Compatibility Challenge
- Different agent harnesses (Codex, Claude Code, Cursor, GitHub Copilot) handle subagents and permissions differently
- Skills intended for multiple platforms cannot assume identical capabilities
- Requires careful design to work across heterogeneous environments

#### Skill Routing and Mixture-of-Skills
- Skills can include internal routing to combine multiple capabilities
- Routes tasks toward relevant instructions within the skill
- Analogous to mixture-of-experts models
- Benefits: token conservation and improved effectiveness

### Known Limitations

#### Creativity Convergence Problem
- "Most skills — [and] most models — are not very creative"
- Tendency to "converge in one direction"
- Risk: If everyone uses same skill, "everything ends up looking the same"
- Open challenge for skill engineering discipline

#### Appropriate Level of Abstraction
- Not all tasks benefit from skill-level control
- Direct manipulation (e.g., spacing adjustments) may be faster for small changes
- Open-ended prompting still useful for initial exploration
- Goal: Determine "exact level of control" and insert human judgment where most valuable

### Cross-references
- [[prompt-architecture]] — Skills as structured prompt knowledge
- [[ai-native-product-design]] — Human steering vs. full automation philosophy