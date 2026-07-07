---
tags: [adversarial-testing, agent-benchmarks, agent-personality-eval, agent-vulnerabilities, agentic-bug-finding, agentic-harness, agentic-workflows, agents-last-exam, ai-security, arc-agi, arc-prize, automated-red-teaming, autonomous-agents, benchmark-design, benchmark-evaluation-methodology, benchmark-methodology, benchmark-replacement, biology-benchmarks, bug-finding-evals, capture-the-flag, claude-sonnet-5, clear-pass-fail-signals, coding-agent-indices, coding-agents, coding-evals, composite-scoring, ctf-evals, custom-benchmarks, cybench, cybersecurity-agent-evaluation, cybersecurity-benchmarks, cybersecurity-evals, data-retention-constraints, deepswe, docker-sandboxing, economically-useful-tasks, evals-production-deployment, evaluation-methodology, evaluation-transparency, expert-vetted-benchmarks, exploit-generation, fallback-scoring, false-positive-detection, feature-implementation, feature-implementation-evals, first-solve-time, frozen-inputs, goal-loop-evals, goal-loop-pattern, gray-swan-arena, guardrails, gut-feel-scoring, human-in-the-loop, human-judgment, human-written-tests, humanitys-last-exam, incident-diagnosis, intelligence-indices, llm-as-judge, llm-as-judge-limitations, llm-judge, llm-judge-prioritization, long-horizon-agentic-tasks, model-benchmarking, model-evaluation, model-fallback-evaluation, model-personality, model-routing, model-selection-strategy, multi-agent-orchestration, multi-language-evals, personal-benchmarks, prd-evaluation, private-codebase-evals, production-deployment, program-replication, program-synthesis, program-synthesis-evals, prompt-filtering, prompt-injection, proprietary-benchmarks, prototype-evaluation, pure-vs-practical-evaluation, red-teaming, red-teaming-models, refusal-handling, repeatability, robustness-evaluation, safety-classifiers, safety-guardrails, sandbox-environments, sandboxed-environments, sanitizer-validation, science-benchmarks, scoring-rubric, security-bug-evals, security-evals, session-history-generation, subtask-grading, swbench, swe-bench, system-diagnosis-evals, task-specific-recommendations, token-pricing, ui-evaluation, vals-ai, verifier-subagent, vibe-checks, vision-models, visual-inspection, vulnerability-discovery, vulnerability-exploitation, weighted-indices, zero-da]
---

## How I AI Bench: Personal Benchmark Design Pattern (July 2026)

**Source**: Claire (How I AI/Lenny's Newsletter), "Sonnet 5 review: I ran 64 generations to find out if it's worth it"

### Benchmark Construction Methodology

**Claude Code for benchmark generation**: Models can read stored session history to generate eval tasks tailored to individual work patterns. Claire prompted Claude Code to brainstorm eval tasks based on previous collaboration sessions stored on desktop, allowing automatic generation of personally-relevant benchmark tasks.

**Frozen inputs requirement**: Repeatability requires frozen inputs, fixed rubric, and identical tasks across model releases. One-off vibe checks feel useful but aren't repeatable—repeatability is what makes benchmarks matter for longitudinal comparison.

**Manual HTML scoring interface**: Building an HTML scoring page for gut-feel ratings with JSON export takes ~45 minutes with [[ai-engineering-agents|Claude Code]]. Claire scored 64 generations across 5 models by hand using 1-to-5 gut scores with loose notes.

### Task Categories in How I AI Bench v1

- **PRD generation**: Product requirements document creation
- **Prototype building**: UI implementation from specifications
- **Agentic tasks**: Multi-step autonomous work
- **Agent personality**: Voice/tone evaluation (e.g., "ugh, deploys are red again" prompts)

**Task retirement criteria**: Agentic bug-hunting task proved too easy—every model aced it, providing no differentiation between good and great models. Tasks that don't differentiate get retired.

### LLM-as-Judge Limitations

**Confidence: High** - Direct empirical observation from systematic comparison

**Clustering toward middle scores**: LLM judges (GPT-5.5, Opus 4.8) are too generous and cluster toward middle of scale. They lack the "spikiness" needed to differentiate quality levels.

**Visual inspection failure**: Models miss what human eye catches immediately in first screenshot—broken prototypes, ignored wireframe constraints. Vision models cannot yet match human visual evaluation for UI quality.

**Judge-human divergence**: LLM judges ranked Gemini 3 Pro highest and Sonnet 4.6 lowest. Claire's personal ranking was almost exactly opposite. This divergence indicates rubric needs to encode more of what evaluator actually cares about before automated scores can be trusted.

### Weighted Index Approach

**70/30 human-to-LLM weighting**: When Claire applied 70% weight to her scores and 30% to LLM judge scores, Sonnet 4.6 jumped from lowest to first place. This "Claire-weighted index" produced task-by-task recommendations that aligned better with her actual preferences.

**Human signal primacy**: Manual gut-feel scoring "turned out to be the most useful part of the whole benchmark" despite being subjective and time-intensive.

### Task-Specific Model Recommendations from How I AI Bench

From Claire-weighted index results:
- **PRD generation**: GPT-5.5
- **Prototypes and conversational interaction**: [[model-architecture|Sonnet 4.6]]
- **Codebase navigation**: [[model-architecture|Opus 4.8]] or [[model-architecture|Sonnet 5]]
- **Complex, dense UI work**: Opus 4.8 (justifies price premium)

**Agent personality differentiation**: Sonnet 4.6 remains Claire's choice for daily agent work due to personality/voice, not benchmark scores. No other model in test matched it on voice evaluation.

### Cross-Model Comparison Context

Claire's benchmark compared:
- [[model-architecture|Sonnet 5]]: $2/M input, $10/M output (summer 2026 promotional pricing)
- [[model-architecture|Sonnet 4.6]]: Previous-generation pricing tier
- [[model-architecture|Opus 4.8]]: Premium tier
- [[model-architecture|GPT-5.5]]
- [[model-architecture|Gemini 3 Pro]]

**Sonnet 5 positioning**: Priced closer to previous Sonnet models than to Opus, finished near bottom of Claire's personal preference ranking. Cost argument only holds if quality argument holds for specific use case—not a universal upgrade.

### Benchmark Evolution Goals

- Encode more evaluator taste into rubric
- Run blind evaluation on every new model release
- Goal: create benchmark that labs actually care about
- Acknowledge this is "version one" requiring continued sharpening