---
tags: [model-evaluation, llm-as-judge, benchmark-design, frontier-models, claude-sonnet, agentic-tasks, evals-production-deployment]
---

---
tags: [adversarial-testing, agent-benchmarks, agent-vulnerabilities, agentic-bug-finding, agentic-harness, agentic-workflows, agents-last-exam, ai-security, arc-agi, arc-prize, automated-red-teaming, benchmark-design, benchmark-evaluation-methodology, benchmark-methodology, benchmark-replacement, biology-benchmarks, bug-finding-evals, capture-the-flag, clear-pass-fail-signals, coding-agent-indices, coding-agents, coding-evals, composite-scoring, ctf-evals, cybench, cybersecurity-agent-evaluation, cybersecurity-benchmarks, cybersecurity-evals, data-retention-constraints, deepswe, docker-sandboxing, economically-useful-tasks, evals-production-deployment, evaluation-transparency, expert-vetted-benchmarks, exploit-generation, fallback-scoring, false-positive-detection, feature-implementation, feature-implementation-evals, first-solve-time, goal-loop-evals, goal-loop-pattern, gray-swan-arena, guardrails, human-in-the-loop, human-written-tests, humanitys-last-exam, incident-diagnosis, intelligence-indices, llm-judge, llm-judge-prioritization, long-horizon-agentic-tasks, model-benchmarking, model-evaluation, model-fallback-evaluation, model-routing, model-selection-strategy, multi-agent-orchestration, multi-language-evals, private-codebase-evals, production-deployment, program-replication, program-synthesis, program-synthesis-evals, prompt-filtering, prompt-injection, proprietary-benchmarks, pure-vs-practical-evaluation, red-teaming, red-teaming-models, refusal-handling, robustness-evaluation, safety-classifiers, safety-guardrails, sandbox-environments, sandboxed-environments, sanitizer-validation, science-benchmarks, security-bug-evals, security-evals, subtask-grading, swbench, swe-bench, system-diagnosis-evals, token-pricing, vals-ai, verifier-subagent, vision-models, vulnerability-discovery, vulnerability-exploitation, zero-day-attacks, zero-day-scenarios, hybrid-scoring, human-gut-scoring, repeatable-eval-harness, multi-task-benchmarking, agent-personality-eval, prd-quality-eval, prototype-generation-eval]---

## Evolution Beyond SWE-bench

The SWE-bench family (SWE-bench, SWE-Bench Pro, SWE-bench Multilingual, and

## Hybrid Human-LLM Scoring Systems

### How I AI Bench Methodology

A repeatable evaluation harness designed for practical AI assessment combining:
- **Human vibe scoring (70% weight)**: Subjective quality assessment based on user gut feel, delivered through local HTML scoring interfaces with JSON export
- **LLM-as-judge scoring (30% weight)**: Automated evaluation component
- Rationale: Neither human nor LLM scoring alone provides reliable assessment; hybrid approach balances subjective quality with objective metrics

### Multi-Task Evaluation Dimensions

Comprehensive benchmark across four evaluation categories:
1. **PRD quality**: Ability to generate product requirement documents
2. **Prototype generation**: Code generation for working prototypes  
3. **Agentic task completion**: Multi-step autonomous task execution
4. **Agent personality/voice**: Conversational quality and interaction style

Note: Built in under 45 minutes using [[ai-engineering-agents|Claude Code]], constructed from stored session history

### Blind Testing Protocol

Frontier model comparison (June 2026) across Claude Sonnet 5, Claude Sonnet 4.6, Claude Opus 4.8, GPT-5.5, and Gemini 3 Pro using 64 blind generations to prevent bias in evaluation.