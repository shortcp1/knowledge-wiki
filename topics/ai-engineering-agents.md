---
tags: [agentic-ai, ai-coding-agents, ai-engineering-agents, autonomous-debugging, claude-code, claude-fable, coding-agents, cross-model-tool-compatibility, cuda-programming, economic-automation, gpu-kernel-optimization, model-regression, model-specific-tool-training, pre-release-testing, recursive-self-improvement, reinforcement-learning, reinforcement-learning-tool-bias, remote-labor-index, software-quality-assurance, tool-calling, tool-calling-reliability, tool-schema, transaction-management]
---

---
tags: [agent-demo-generation, agent-demos, agent-framework, agent-skills, agent-vocabulary, agentic-primitives, agentic-tasks, agentic-workflows, ai-engineering-agents, benchmark-design, business-agents, claude-code, claude-sonnet, cli-interface, codex-desktop, coding-agents, cross-harness-compatibility, cursor-ide, datasette, design-agents, design-skills, file-manipulation, frontier-models, glm-5-2, gpt-5-5-xhigh, human-in-the-loop, impeccable, inference-cost, llm-as-judge, llm-library, mcp-servers, mixture-of-experts, mixture-of-skills, model-evaluation, open-weight-models, playwright-agents, playwright-automation, prompt-vocabulary, self-hosting, shot-scraper, skill-engineering, skill-routing, storyboard-automation, storyboard-yaml, tdd, tool-calling, v0-coding-agent, vendor-lock-in, vercel-eve, video-demo-agents, video-documentation, claude-fable, sqlite-utils, pre-release-review, bug-detection, transaction-handling, mobile-prompting, async-work-pattern, multi-model-review, gpt-5-5-review, kernel-development, cuda-programming, gpu-kernel-optimization, kernelbench-mega]---

## sqlite-utils 4.0rc2: Production Library Development with Claude Fable (July 2026)

**Source**: Simon Willison, "sqlite-utils 4.0rc2, mostly written by Claude Fable (for about $149.25)"

### Business Problem
- Final pre-release review and hardening of sqlite-utils 4.0 library before stable release
- Critical need to identify breaking changes and bugs before committing to SemVer major version
- Maintaining library quality and backward compatibility standards

### AI Pattern Applied
**Agentic coding review and implementation** using Claude Fable (Claude Code for web)
- Initial comprehensive

## GPU Kernel Development with Claude Fable (July 2026)

**Source**: Import AI 464 (Jack Clark)

### Technical Achievement: KernelBench-Mega Performance
**Fable's GPU Kernel Performance**:
- **Result**: 18.71X speedup on RTX PRO 6000 Blackwell vs optimized PyTorch baseline
- **Significance**: "First genuine (and fastest) megakernel ever submitted to KernelBench-Mega" (per benchmark maintainer)
- **Architecture**: Single cooperative kernel launch per decoded token
- **Language**: CUDA code (native, not Triton)

**Comparative Performance** (all on same benchmark):
- Claude Opus 4.8 (Triton): 14.4X
- GLM-5.2 (Triton): 11.14X  
- GPT 5.5 (Triton): 4.34X

**Technical Distinction**: 
- Fable: 1 kernel launch per token
- All other high-scoring entries: 4-14 separate kernel launches per token
- Single megakernel approach represents superior fusion optimization

### Implication for AI R&D Automation
**Recursive Self-Improvement Signal**:
- Kernel development is "fundamental input task for AI research and development"
- AI systems now capable of autonomously developing and improving the compute primitives that underlie AI training/inference
- Creates potential feedback loop: better kernels → faster AI development → better AI systems → better kernel development
- KernelBench-Mega serves as "meaningful signal on how effective AI systems are becoming at building themselves"

**Cross-reference**: See [[gpu-architecture-training-infra]] for kernel optimization's role in AI infrastructure