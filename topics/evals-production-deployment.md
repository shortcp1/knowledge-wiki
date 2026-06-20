---
tags: [agentic-harness, agentic-workflows, agents-last-exam, arc-agi, arc-prize, benchmark-design, benchmark-evaluation-methodology, benchmark-methodology, benchmark-replacement, biology-benchmarks, coding-agent-indices, coding-agents, composite-scoring, cybersecurity-benchmarks, data-retention-constraints, deepswe, economically-useful-tasks, evals-production-deployment, evaluation-transparency, expert-vetted-benchmarks, fallback-scoring, feature-implementation, feature-implementation-evals, human-written-tests, humanitys-last-exam, incident-diagnosis, intelligence-indices, long-horizon-agentic-tasks, model-benchmarking, model-evaluation, model-fallback-evaluation, model-routing, model-selection-strategy, multi-agent-orchestration, multi-language-evals, private-codebase-evals, program-replication, program-synthesis, program-synthesis-evals, prompt-filtering, proprietary-benchmarks, pure-vs-practical-evaluation, refusal-handling, safety-classifiers, safety-guardrails, science-benchmarks, swbench, swe-bench, system-diagnosis-evals, token-pricing, vals-ai, vision-models]
---

## Evolution Beyond SWE-bench

The SWE-bench family (SWE-bench, SWE-Bench Pro, SWE-bench Multilingual, and SWE-bench Verified) is being challenged by new benchmarks that evaluate agentic software engineering performance in more demanding ways. Three notable successors have emerged as of June 2026:

### DeepSWE

**Developer**: Datacurve

**Scope**: 113 problems across 5 programming languages

**Focus**: Feature implementation capabilities (vs. bug fixing in SWE-bench)

**Key Characteristics**:
- Problems vetted by human experts
- Uses brief prompts (in contrast to detailed prompts in SWE-Bench Pro)
- Solutions require ~5.5x more lines of code than SWE-Bench Pro
- Draws from private codebases to minimize [[benchmark-contamination]] risk
- Uses human-written problems and tests based on real repositories but not taken from existing or solved code
- Example task: "Extend indexing ranges so arrays and strings support a third slice component: value[start:end:step]" in the ABS programming language GitHub repository

**Harness**: mini-swe-agent

**Adoption**: Artificial Analysis replaced SWE-Bench Pro with DeepSWE for its Intelligence and Coding Agent indices (as of June 2026)

**Performance** (June 2026):
- GPT-5.5 (xhigh reasoning): 70% solved
- Claude Opus 4.8: 58% solved  
- Gemini 3 Flash: 5% solved
- 65 point spread across leading models indicates significant [[frontier-headroom-evals]] remain

## Evaluation Methodology Challenges with Safeguarded Models

### Claude Fable 5 Evaluation Case Study (June 2026)

**Problem**: Independent evaluators encountered systematic challenges testing Claude Fable 5 due to Anthropic's [[model-safeguards]] architecture, which routes or refuses certain prompts before they reach the primary model.

**Two Evaluation Paradigms Emerged**:

1. **"Pure" Evaluation**: Measure only Claude Fable 5's capabilities without influence from fallback model (Claude Opus 4.8)
   - Treats refusals as failures
   - Separates fallback responses from primary model responses
   - Shows true capability ceiling of primary model

2. **"Practical" Evaluation**: Measure deployed system including refusals and fallback responses
   - Reflects real-world user experience
   - Produces blended scores across multiple models
   - More relevant for production deployment decisions

### Benchmark-Specific Responses

**Artificial Analysis Intelligence Index**:
- Composite of 10 tests of economically useful tasks
- Evaluated Claude Fable 5 before launch
- Recorded ~8% fallback rate to Claude Opus 4.8
- Most fallbacks on science questions
- Published blended scores including all fallback responses
- Result: Claude Fable 5 scored 64.9 (first place), 3.5% higher than Claude Opus 4.8 alone

**Vals AI**:
- Tests public and proprietary benchmarks of economically useful tasks
- Published two score sets: one with fallbacks, one counting refusals as failures
- Reported nearly 100% refusal rate on biology and cybersecurity questions

**Agents' Last Exam** (also referenced as "Humanity's Last Exam"):
- Tests long-horizon agentic tasks with verifiable outcomes
- Claude Fable 5 refused ~35% of tasks
- Model switched to Claude Opus 4.8 mid-task on science questions flagged as "cybersecurity or biology"
- Switches recorded in separate log events, not in response text
- Published results for both "untouched" tasks (only Claude Fable 5) and composite tasks (including Claude Opus 4.8 contributions)
- Despite 9% refusal rate, Claude Fable 5 achieved competitive ranking

**ARC Prize Foundation** (ARC-AGI abstract reasoning tests):
- Declined to run verified evaluations
- Reason: Would not expose private test set to Anthropic's 30-day data retention requirement
- Stated would post results if testing possible without data retention

### Performance Pattern

Claude Fable 5 ranking varied significantly by evaluation methodology:
- **Highest**: On questions answered without fallback
- **High**: When Claude Opus 4.8 fallback responses included (blended scoring)
- **Significantly lower**: When refusals scored as failures or models measured separately

### Implications for Benchmark Design

**New Considerations for Evaluators**:
- Data retention policies may prevent testing on proprietary benchmarks
- Transparency requirements: Evaluators must determine if model switches occurred
- Logging architecture: Model fallbacks may not be visible in response text
- Scoring methodology must be explicitly stated: pure vs. practical

**Challenges for Model Comparison**:
- Different evaluation approaches produce different rankings
- "Real-world performance" may involve multiple models
- Benchmark results may not reflect which model actually answered
- Refusal rates vary dramatically by domain (near-zero on some tasks, near-100% on others)

See also: [[ai-governance-risk-compliance]] for policy implications, [[model-architecture]] for technical implementation