---
tags: [4-bit-quantization, agent-architecture, agent-harness, agent-harness-design, agent-loops, agent-state-tracking, agentic-architecture, agentic-behavior, agentic-bug-finding, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, always-on-agents, anthropic, antigravity-cli, auto-dream, autonomous-agents, autonomous-debugging, autonomous-fine-tuning, autonomous-research, autonomous-workflows, backend-development, background-processes, benchmark-contamination, benchmark-design, benchmark-vs-deployment, browser-automation, bug-finding-agents, capybara, chain-of-thought, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, client-side-inference, cloud-offloading, code-quality-evaluation, codex, codex-cli, codex-desktop, codex-goals, coding-agents, coding-models, composer, context-caching, context-window-management, controller-agents, cors-debugging, creative-agents, cron-loops, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, deepswe, desktop-agent-harness, desktop-agents, diffusion-transformers, false-positives, feature-implementation, feature-implementation-agents, firefox, frontend-code, frontend-coding, frontier-model-competition, frontiercode, function-calling, fuzzing, git-stealth, glm-5.2, goal-based-agents, goal-based-automation, goal-driven-agents, goal-loop-pattern, goal-loops, grok-imagine, heartbeat-loops, hermes-agent, hook-loops, html-injection, human-in-the-loop, hybrid-transformer-mamba, image-inpainting, indexshare, infrastructure-engineering, internal-benchmarks, iteration-speed, iterative-composition, iterative-evaluation, javascript-injection, kairos, keyboard-simulation, llm-capability-eval, llm-driven-loops, llm-judge, llm-judge-prioritization, local-server-debugging, long-context, long-horizon-coding, long-running-tasks, loop-design, loop-engineering, low-precision-training, mac-automation, maintainability, model-vs-harness, mozilla, production-deployment, sanitizer-tools, security-bug-fixes, subagent-verification, verifier-agents, verifier-subagent]
---

# AI Engineering Agents

## Mozilla Firefox Bug-Finding Pipeline (Grinstead, June 2026)

### Core Implementation
**Business Problem**: Finding security vulnerabilities in massive legacy codebases (Firefox: tens of thousands of files, tens of millions of lines of code). Traditional approaches scale poorly, and human review is time-intensive.

**AI Pattern Applied**: Goal-Loop Architecture with Verifier Subagent
- **Goal-loop pattern**: Give agent a tightly scoped problem, clear pass/fail signal, and let it retry far past the point a human would quit
- **LLM judge**: Scores and ranks files before spending compute on bug-finding
- **Verifier subagent**: Kills false positives by catching when the agent "cheats" or hallucinates bugs
- **Minimal harness**: Built with Claude Code/Codex using `-p` flag, no SDK required initially

### Architecture Components

**1. File Prioritization**
- LLM judge evaluates entire codebase before agent runs
- Scores and ranks files by likelihood of containing vulnerabilities
- Prevents wasted compute on low-value files

**2. Goal-Loop Execution**
- Tightly scoped problem per iteration
- Clear pass/fail signal (code compiles, tests pass, sanitizers pass)
- Retry logic exceeds human patience thresholds
- Agent given specific goal, not open-ended exploration

**3. Verification Layer**
- Separate verifier subagent validates findings
- Catches false positives where agent manipulates test conditions
- Ensures bugs are real before human review

**4. Human-in-the-Loop**
- Every AI-generated patch reviewed by humans before shipping
- Humans remain final decision makers
- Agent accelerates discovery, humans maintain quality

### Implementation Details
- Built on top of Claude Code and Codex CLI tools
- Docker sandboxing for safe execution
- Integration with Address Sanitizer for memory safety validation
- Works with existing CI/CD and fuzzing infrastructure
- Teams with prior investment in tooling and testing infrastructure have significant advantage

### Outcomes & Impact

**Quantitative Results**:
- **423 security fixes shipped in one month** (record-breaking for Firefox)
- Found bugs that had existed for 15+ years
- Viral chart showed dramatic spike in "Firefox Security Bug Fixes by Month"

**Key Success Factors**:
1. **Model-harness split**: Brian estimates "close to 50-50" credit between Mythos model capabilities and harness design
2. **Existing infrastructure**: Mozilla's prior investment in fuzzing, CI, and dev tooling provided foundation
3. **Verifier subagent**: Eliminated false positive problem that plagued earlier approaches
4. **Goal-loop discipline**: Tight scoping prevented agent wandering and maintained focus
5. **File prioritization**: LLM judge prevented wasted effort on low-value targets

**What Made It Succeed**:
- Clear pass/fail signals (compilation, tests, sanitizers)
- Verifier subagent to validate findings
- Human review gate before shipping
- Building on mature tooling ecosystem (Docker, sanitizers, CI)
- Tight scoping via goal-loops vs open-ended exploration
- Pre-filtering codebase with LLM judge

### Industry Context
**Industry**: Software / Web Browsers
**Function**: Security Engineering, Software Quality
**Organization**: Mozilla (Firefox)
**Team**: Brian Grinstead (Distinguished Engineer) and team
**Model Used**: Claude Mythos (Anthropic)

### Generalizability

The goal-loop + verifier pattern applies broadly beyond security:

**Direct Applications**:
- Security vulnerability detection in any large codebase
- Performance optimization hunting
- Memory leak detection
- Code quality improvements
- Tech debt reduction

**Analogous Patterns for Non-Engineering**:
- **Design quality**: Score designs, generate improvements, verify against brand guidelines
- **Conversion optimization**: Identify friction points, propose fixes, verify against user behavior data
- **Content quality**: Find outdated docs, generate updates, verify accuracy
- **Compliance checking**: Score risk areas, find violations, verify against regulations

**Key Transferable Insights**:
1. Verifier subagents solve false positive problem across domains
2. LLM judges for prioritization work whenever search space is large
3. Goal-loops with clear success metrics outperform open-ended agent exploration
4. Model capabilities ≈ harness design in determining outcomes
5. Existing tooling/infrastructure provides force multiplier

### Open Source
Mozilla open-sourced the harness design and approach for community reuse.

### References
- Podcast: "How I AI" hosted by Claire Vo, June 22, 2026
- Guest: Brian Grinstead, Distinguished Engineer at Mozilla
- GitHub: https://github.com/mozilla
- Bug Bounty: https://www.mozilla.org/security/bug-bounty/