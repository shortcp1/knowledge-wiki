---
tags: [agent-benchmarks, agent-composition, agent-compute, agent-compute-infrastructure, agent-harness, agent-sandboxes, agentic-ci-cd, agentic-evals, agentic-tasks, agi-taxonomy, ai-for-medicine, ai-integration, ai-safety-benchmarks, ai-sandboxes, anthropic-mythos, attention, bare-metal-infrastructure, bare-metal-scheduling, benchmark-design, benchmark-evals, benchmark-evolution, caisi, clinical-validation, cognitive-assessment, computer-use-evals, convolutional-neural-networks, custom-agents, cybersecurity, data-moats, daytona, deepmind, direct-preference-optimization, dpo, dual-use, economic-alignment, emotional-intelligence, emotional-stability, evals-production-deployment, evaluation-methodology, executive-functions, exploit-chain-construction, frontier-evals, frontier-headroom-evals, frontier-models, gdpval, gemini, gemma, harbor, human-ai-collaboration, launch-quality-evals, learning, localhost-replacement, mcp-vs-cli, medical-imaging, memory, metacognition, model-approval-process, model-personality, model-refusals, model-safeguards, national-security-ai, nist-evaluation, occupational-taxonomy, offensive-capabilities, open-vs-closed-models, perception, portbench, post-training, pre-deployment-testing, problem-solving, progressive-tool-disclosure, proof-generation, real-world-deployment, reasoning, regression-tests, rl-eval-infrastructure, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, rlvr, safety-evaluation, scaling-laws, security-focused-llm, security-testing, sensitivity-specificity, social-cognition, software-factory, startup-adoption, stateful-environments, swe-bench, terminalbench, trains, trains-task-force, vulnerability-research]
---

# Evals & Production Deployment

Covers how teams measure model quality in production: evaluation frameworks, benchmark design, human eval vs. LLM-as-judge, A/B testing for AI, red-teaming, and monitoring for drift and hallucination.

Key questions tracked: What evals actually predict real-world performance? How are teams doing continuous eval in production? What is the state of AI observability tooling?

## Key Claims

### Benchmark Coverage Gaps (CMU/Stanford, May 2026)

**Agent Benchmarks vs. Economic Labor Distribution Mismatch**: Analysis of 10,000+ examples from 43 agent benchmarks reveals systematic bias toward software engineering tasks, misaligned with broader U.S. labor distribution and economic value:

- **Occupational Coverage Bias**: Benchmarks heavily emphasize "computer and mathematical" occupations (8,622 examples) over "office and administrative support" (3,186 examples) and "management" (676 examples). This is inverted relative to U.S. employment: 5.2M in computer/math vs. 18.2M in office/admin and 11M in management.

- **Economic Value Misalignment**: Total U.S. wages for computer/math roles ($563.6B/year) are significantly lower than office/admin ($869.8B) and management ($1,326.3B), suggesting benchmarks under-represent higher-value occupational categories.

- **Coverage Limitations**: Individual benchmarks cover <50% of work activities and <60% of skills. [[gdpval]] achieves best coverage at 47.8% of work activities and 58.5% of skills. All benchmarks combined cover only 56.5% of work activities, though 85.4% of the 41 skill categories tracked.

- **Methodology**: Used Claude 3.5 Sonnet to map benchmark examples to O*NET taxonomy (5,806 computer-based work activities and 41 skills). Employed adaptive sampling strategy: randomly sampled batches of 5 examples until coverage increase <0.1% (typically ~300 examples per benchmark, or all examples if <300 total).

**Implication**: Current agent benchmarks may overstate progress on economically valuable labor automation. Agents showing rapid improvement on benchmarks like [[swe-bench]] may not translate to similar gains in administrative, financial, or managerial domains that represent larger shares of employment and economic output.