---
tags: [adversarial-testing, agent-benchmarks, agent-personality-eval, agent-vulnerabilities, agentic-bug-finding, agentic-harness, agentic-red-teaming, agentic-workflows, agents-last-exam, ai-safety-evaluations, ai-security, arc-agi, arc-prize, automated-prompt-injection, automated-red-teaming, autonomous-agents, benchmark-design, benchmark-evaluation-methodology, benchmark-methodology, benchmark-replacement, bespoke-evaluation-interfaces, binary-reverse-engineering, biology-benchmarks, biosecurity, bug-finding-evals, capability-probing, capture-the-flag, catastrophic-risk, chain-of-thought, chain-of-thought-attacks, claude-3-7-sonnet, claude-sonnet-5, clear-pass-fail-signals, coding-agent-indices, coding-agents, coding-evals, composite-scoring, ctf-evals, custom-benchmarks, cybench, cyber-ranges, cybersecurity-agent-evaluation, cybersecurity-benchmarks, cybersecurity-capabilities, cybersecurity-evals, data-retention-constraints, deepswe, docker-sandboxing, domain-expert-red-teaming, dual-use-ai, dual-use-capabilities, economically-useful-tasks, evals-production-deployment, evaluation-methodology, evaluation-transparency, expert-vetted-benchmarks, exploit-generation, fake-chain-of-thought, fallback-scoring, false-positive-detection, feature-implementation, feature-implementation-evals, first-solve-time, frontier-red-team, frontier-red-teaming, frozen-inputs, goal-loop-evals, goal-loop-pattern, gpt-5-6, gpt-red, gray-swan-arena, guardrails, gut-feel-scoring, human-in-the-loop, human-judgment, human-written-tests, humanitys-last-exam, incalmo, incident-diagnosis, information-security-protections, intelligence-indices, intercode-ctf, jailbreak-testing, jailbreaking, lateral-movement, llm-as-judge, llm-as-judge-limitations, llm-judge, llm-judge-prioritization, llm-red-teaming, llm-security, long-horizon-agentic-tasks, model-benchmarking, model-evaluation, model-fallback-evaluation, model-personality, model-routing, model-selection-strategy, multi-agent-orchestration, multi-language-evals, multi-stage-attacks, national-security, national-security-risk, national-security-risk-assessment, network-reconnaissance, personal-benchmark, prompt-injection, prompt-injection-testing, real-world-agent-testing, red-teaming, self-play, self-play-red-teaming]
---

## GPT-Red: Automated Red-Teaming System

**Organization:** OpenAI (2026)

**Technical Approach:** Self-play training loop where an LLM trained as an attacker competes against defender models over multiple rounds. The system operates in a simulated dojo environment that mimics real-world deployment scenarios including web browsing, email/calendar access, and code editing.

**Key Capabilities:**
- More persistent than human red-teamers at drilling down into discovered attacks
- Highly effective at finding optimal attack variants for specific scenarios
- Explores multiple versions of discovered attacks to identify most efficient exploits
- Focus on [[prompt-injection]] attacks where malicious instructions are hidden in text, code, or websites

**Discovered Attack Types:**
- **Fake chain of thought attacks** (novel, not previously documented): Inserting false entries into an LLM's [[chain-of-thought]] reasoning to make it act on spoofed information (e.g., convincing a model it has already verified that 1+1=3)
- Successfully attacked Vendy vending machine agent (Andon Labs) to change prices and cancel orders

**Effectiveness Claims:**
- Outperformed human red-teamers when rerunning 2025 experiment against earlier GPT-5
- OpenAI claims >90% of GPT-Red's strongest attacks succeeded against GPT-5 (August 2025 release)
- <23% success rate against GPT-5.6 (July 2026 release), indicating significant hardening

**Known Limitations:**
- Weak at multi-turn conversational attacks that require back-and-forth interaction
- Limited capability with image-based prompt injection attacks
- Supplements but does not replace human red-teaming

**Methodology Note:** Self-play approach assessed as "promising" by Georgetown CSET AI security researchers (Jessica Ji, 2026).

See also: [[ai-governance-risk-compliance]], [[model-architecture]]