---
tags: [adversarial-testing, agent-benchmarks, agent-vulnerabilities, agentic-bug-finding, agentic-harness, agentic-workflows, agents-last-exam, ai-security, arc-agi, arc-prize, automated-red-teaming, benchmark-design, benchmark-evaluation-methodology, benchmark-methodology, benchmark-replacement, biology-benchmarks, bug-finding-evals, capture-the-flag, clear-pass-fail-signals, coding-agent-indices, coding-agents, coding-evals, composite-scoring, ctf-evals, cybench, cybersecurity-agent-evaluation, cybersecurity-benchmarks, cybersecurity-evals, data-retention-constraints, deepswe, docker-sandboxing, economically-useful-tasks, evals-production-deployment, evaluation-transparency, expert-vetted-benchmarks, exploit-generation, fallback-scoring, false-positive-detection, feature-implementation, feature-implementation-evals, first-solve-time, goal-loop-evals, goal-loop-pattern, gray-swan-arena, guardrails, human-in-the-loop, human-written-tests, humanitys-last-exam, incident-diagnosis, intelligence-indices, llm-judge, llm-judge-prioritization, long-horizon-agentic-tasks, model-benchmarking, model-evaluation, model-fallback-evaluation, model-routing, model-selection-strategy, multi-agent-orchestration, multi-language-evals, private-codebase-evals, production-deployment, program-replication, program-synthesis, program-synthesis-evals, prompt-filtering, prompt-injection, proprietary-benchmarks, pure-vs-practical-evaluation, red-teaming, red-teaming-models, refusal-handling, robustness-evaluation, safety-classifiers, safety-guardrails, sandbox-environments, sandboxed-environments, sanitizer-validation, science-benchmarks, security-bug-evals, security-evals, subtask-grading, swbench, swe-bench, system-diagnosis-evals, token-pricing, vals-ai, verifier-subagent, vision-models, vulnerability-discovery, vulnerability-exploitation, zero-day-attacks, zero-day-scenarios]
---

## Evolution Beyond SWE-bench

The SWE-bench family (SWE-bench, SWE-Bench Pro, SWE-bench Multilingual, and SWE-bench Verified) is being challenged by new benchmarks that evaluate agentic software engineering performance in more demanding ways. Three notable successors have emerged as of June 2026:

### DeepSWE

**Developer**: Datacurve

**Scope**: 113 problems across 5 p

## Goal-Loop Evaluation Pattern (Mozilla, June 2026)

### Core Evaluation Architecture

Mozilla's bug-finding pipeline demonstrates a production evaluation pattern that emphasizes:

**1. Clear Pass/Fail Signals**
- Code compilation status
- Test suite passage
- Sanitizer validation (Address Sanitizer for memory safety)
- No ambiguous scoring - binary success criteria

**2. Verifier Subagent for False Positive Detection**
- Separate agent validates primary agent's findings
- Catches cases where agent "cheats" (e.g., modifying test conditions to make bug appear)
- Critical for production deployment where false positives have cost
- Eliminates traditional weakness of automated bug detection

**3. LLM Judge for Prioritization**
- Scores entire codebase before running expensive bug-finding agents
- Ranks files by vulnerability likelihood
- Prevents compute waste on low-probability targets
- Evaluation happens at file-selection stage, not just bug validation stage

**4. Real-World Validation**
- 423 security fixes shipped in one month (Firefox record)
- Found 15-year-old bugs that human review had missed
- All findings validated through human review before shipping

### Key Evaluation Insights

**Model vs Harness Credit Split**: Brian Grinstead estimates "close to 50-50" credit between:
- Model capabilities (Claude Mythos)
- Harness design (goal-loops, verifier, judge)

This challenges model-centric evaluation approaches and suggests benchmarks should measure harness design quality alongside model capabilities.

**Generalization to Other Eval Domains**:
The verifier subagent pattern solves false positive problems across:
- Security vulnerability detection
- Code quality assessment  
- Compliance checking
- Any domain where agent has incentive to game evaluation metrics

**Infrastructure Dependency**:
Teams with existing investment in:
- Fuzzing infrastructure
- CI/CD pipelines
- Docker sandboxing
- Sanitizer tools (Address Sanitizer, etc.)

...achieved significantly better results, suggesting evaluation should account for tooling ecosystem, not just model+prompt.

### Production Deployment Lessons

**Why Human Review Remains Mandatory**:
- AI-generated patches cannot ship autonomously
- Humans provide final quality gate
- Even with verifier subagent, human judgment required for:
  - Security impact assessment
  - Code maintainability
  - Architectural coherence
  - Risk management

**Evaluation Must Match Deployment Reality**:
- Benchmarks testing autonomous deployment miss the real production pattern
- Human-in-loop evaluation better reflects actual usage
- Success metric: human review time saved, not full automation

### References
- Mozilla Firefox bug-finding pipeline (June 2026)
- Brian Grinstead, Distinguished Engineer at Mozilla
- Claude Mythos model (Anthropic)