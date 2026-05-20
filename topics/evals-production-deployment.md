---
tags: [agent-composition, agent-harness, agentic-tasks, agi-taxonomy, ai-for-medicine, ai-integration, ai-safety-benchmarks, anthropic-mythos, attention, benchmark-evals, benchmark-evolution, caisi, clinical-validation, cognitive-assessment, convolutional-neural-networks, custom-agents, cybersecurity, data-moats, deepmind, direct-preference-optimization, dpo, dual-use, emotional-intelligence, emotional-stability, evals-production-deployment, executive-functions, exploit-chain-construction, frontier-evals, frontier-headroom-evals, frontier-models, gemini, gemma, human-ai-collaboration, launch-quality-evals, learning, mcp-vs-cli, medical-imaging, memory, metacognition, model-approval-process, model-behavior-engineer, model-personality, model-refusals, model-safeguards, national-security-ai, nist-evaluation, offensive-capabilities, open-vs-closed-models, perception, portbench, post-training, pre-deployment-testing, problem-solving, progressive-tool-disclosure, proof-generation, real-world-deployment, reasoning, regression-tests, rlvr, safety-evaluation, scaling-laws, security-focused-llm, security-testing, sensitivity-specificity, social-cognition, software-factory, startup-adoption, trains, trains-task-force, vulnerability-research]
---

# Evals & Production Deployment

Covers how teams measure model quality in production: evaluation frameworks, benchmark design, human eval vs. LLM-as-judge, A/B testing for AI, red-teaming, and monitoring for drift and hallucination.

Key questions tracked: What evals actually predict real-world performance? How are teams doing continuous eval in production? What is the state of AI observability tooling?

## Key Claims

### CAISI Evaluation Methodology

#### V4 Assessment (May 2026)
- **Evaluation framework**: Center for AI Standards and Innovation (CAISI) uses Item Response Theory (IRT) to calculate Elo scores for model comparison across different benchmark sets
- **V4 benchmark suite**: Nine different benchmarks used, including:
  - CTF-Archive-Diamond (subset run, extrapolated via IRT)
  - PortBench (CAISI-private benchmark)
  - ARC-AGI-2 (using different scoring method than public leaderboards)

#### DeepSeek V4 Pro Comparison (May 2026)
- **CAISI benchmark aggregate**: NIST shared CAISI's comparison of DeepSeek V4 Pro with other large language models
- **Benchmark composition**: Nine widely used public benchmarks spanning:
  - Cybersecurity
  - Coding
  - Mathematics
  - Natural sciences
  - Abstract reasoning
  - Plus PortBench (internal test: porting command-line interface tools between different programming languages)
- **Model ranking**: Capabilities ranked according to aggregate score across all benchmarks
- **Context**: This benchmark suite was disclosed as example of CAISI methodology; not confirmed whether [[regulatory-policy]] TRAINS program will use same benchmarks for pre-release evaluation