---
tags: [agent-demo-generation, agent-demos, agentic-tasks, ai-engineering-agents, benchmark-design, claude-code, claude-sonnet, codex-desktop, coding-agents, cursor-ide, datasette, frontier-models, glm-5-2, gpt-5-5-xhigh, inference-cost, llm-as-judge, model-evaluation, open-weight-models, playwright-agents, playwright-automation, self-hosting, shot-scraper, storyboard-automation, storyboard-yaml, vendor-lock-in, video-demo-agents, video-documentation]---

---
tags: [4-bit-quantization, agent-architecture, agent-collaboration, agent-harness, agent-harness-design, agent-loops, agent-portability, agent-sdk, agent-state-tracking, agentic-architecture, agentic-behavior, agentic-bug-finding, agentic-coding, agentic-coding-tools, agentic-reasoning, agentic-science, agentic-systems, agentic-tasks, agentic-workflows, ai-coding-agents, ai-coding-productivity, ai-engineering-agents, ai-engineering-tools, ai-rd-automation, ai-scientists, aisuite, alphafold, always-on-agents, anthropic, antigravity-cli, auto-dream, autonomous-agents, autonomous-coding, autonomous-debugging, autonomous-experimentation, autonomous-fine-tuning, autonomous-research, autonomous-workflows, backend-development, background-processes, benchmark-contamination, benchmark-design, benchmark-vs-deployment, browser-automation, bug-finding-agents, capybara, chain-of-thought, change-data-capture, claude-code, claude-fable, claude-fable-5, claude-mythos, claude-opus-4, cli-agents, client-side-inference, cloud-offloading, code-quality-evaluation, codex, codex-cli, codex-desktop, codex-goals, coding-agents, coding-models, composer, context-caching, context-window-management, controller-agents, cors-debugging, cost-efficiency, creative-agents, cron-loops, cursor, cursor-cli, cursorbench, data-retention-privacy, datasette-agent, deepswe, desktop-agent-harness, desktop-agents, developer-feedback-loop, diffusion-transformers, enpire, eval-driven-development, external-feedback-loop, false-positives, feature-implementation, feature-implementation-agents, firefox, frontend-code, frontend-coding, frontier-model-competition, frontiercode, function-calling, fuzzing, git-stealth, glm-5.2, goal-based-agents, goal-based-automation]

## Agent Demo Generation

### shot-scraper video (June 2026)
Tool for having coding agents automatically generate video demonstrations of their work:
- Built on [[playwright-agents]] automation
- Accepts YAML storyboard files defining browser interaction routines
- Records video (WebM/MP4) of agent-produced features
- Uses Playwright to control browser and capture sessions

**Technical approach:**
- Command: `shot-scraper video storyboard.yml --auth auth.json --mp4`
- Storyboard YAML specifies: server startup, viewport dimensions, wait conditions, scenes with actions (click, fill, pause, wait_for)
- Supports cursor recording in video (`cursor: true`)
- Can inject JavaScript for environment setup (e.g., clipboard API mocking)
- Authentication via JSON cookie files

**Agent integration pattern:**
- Agent reads `--help` output to learn tool usage ("SKILL.md bundled inside the tool")
- Example prompt pattern: "Review branch changes, run shot-scraper video --help, use it to record demo of new features"
- GPT-5.5 xhigh in [[codex-desktop]] successfully generated complete storyboard YAML from this pattern
- Tool designed for agent self-documentation via comprehensive CLI help

**Implementation details:**
- Earlier Playwright versions included unwanted chrome in videos for debugging
- Fixed in recent Playwright releases for cleaner demo videos
- Enables [[developer-feedback-loop]] improvements by providing visual artifact of agent work

**Related tools using same help-as-skill pattern:**
- showboat
- rodney

### Rationale
Importance of coding agents producing demos of their work highlighted as key workflow pattern. Enables human reviewers to quickly understand agent-implemented features without manual testing.