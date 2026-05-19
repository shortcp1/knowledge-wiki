---
tags: [agent-composition, agent-harness, agentic-tasks, agi-taxonomy, ai-integration, anthropic-mythos, attention, benchmark-evals, benchmark-evolution, cognitive-assessment, custom-agents, cybersecurity, data-moats, deepmind, direct-preference-optimization, dpo, dual-use, emotional-intelligence, emotional-stability, evals-production-deployment, executive-functions, exploit-chain-construction, frontier-evals, frontier-headroom-evals, frontier-models, gemini, gemma, launch-quality-evals, learning, mcp-vs-cli, memory, metacognition, model-behavior-engineer, model-personality, model-refusals, model-safeguards, offensive-capabilities, open-vs-closed-models, perception, post-training, problem-solving, progressive-tool-disclosure, proof-generation, reasoning, regression-tests, rlvr, safety-evaluation, scaling-laws, security-focused-llm, security-testing, social-cognition, software-factory, startup-adoption, vulnerability-research]
---

# Evals & Production Deployment

Covers how teams measure model quality in production: evaluation frameworks, benchmark design, human eval vs. LLM-as-judge, A/B testing for AI, red-teaming, and monitoring for drift and hallucination.

Key questions tracked: What evals actually predict real-world performance? How are teams doing continuous eval in production? What is the state of AI observability tooling?

## Key Claims

### CAISI V4 Assessment Methodology (May 2026)
- **Evaluation framework**: Center for AI Standards and Innovation (CAISI) uses Item Response Theory (IRT) to calculate Elo scores for model comparison across different benchmark sets
- **V4 benchmark suite**: Nine different benchmarks used, including:
  - CTF-Archive-Diamond (subset run, extrapolated via IRT)
  - PortBench (CAISI-private benchmark)
  - ARC-AGI-2 (using different scoring method than public leaderboards)
  - Six additional benchmarks (not specified in excerpt)
- **Findings on open vs. closed gap**: CAISI assessment claims gap between open and closed models is "becoming wider over time"
- **Benchmark design critique**: Large Elo differences attributed to specific benchmark performance and IRT extrapolation methodology, particularly CTF-Archive-Diamond, PortBench, and AR

### Notion's Three-Tier Eval Philosophy (April 2026)
- **Industry/Function**: Knowledge Management / Productivity Software (SaaS)
- **Eval Architecture**: Three distinct types of evaluations serving different purposes:
  1. **Regression Tests**: Ensure existing functionality doesn't break with updates
  2. **Launch-Quality Evals**: Determine if features are ready for production release
  3. **Frontier/Headroom Evals**: Intentionally calibrated to ~30% pass rate to track where model capabilities are heading; used for roadmap planning rather than launch decisions
- **Key Insight**: Headroom evals that fail 70% of the time provide forward-looking signal about what will become possible as models improve
- **Model Behavior Engineer Role**: Distinct function from software engineering, focused on:
  - Eval writing
  - Failure analysis
  - Model understanding
  - Treating model behavior understanding as a specialized discipline
- **Production Philosophy**: Building product systems that are ready when models become capable, informed by frontier evals showing future direction
- **Generalizability**: Three-tier eval pattern applicable to any AI product company:
  - Regression layer: Prevent degradation
  - Launch layer: Quality gates for shipping
  - Frontier layer: Strategic planning for model capability evolution
  - Especially valuable for products with long development cycles that need to anticipate model improvements