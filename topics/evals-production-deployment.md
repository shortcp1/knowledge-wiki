---
tags: [activation-capping, agent-benchmarks, agent-composition, agent-compute, agent-compute-infrastructure, agent-harness, agent-sandboxes, agentic-ci-cd, agentic-coding, agentic-deception, agentic-evals, agentic-tasks, agi-taxonomy, ai-for-medicine, ai-integration, ai-safety, ai-safety-benchmarks, ai-safety-testing, ai-sandboxes, alphaevolve, andon-labs, anthropic-mythos, assistant-alignment, attention, bare-metal-infrastructure, bare-metal-scheduling, behavioral-modeling, benchmark, benchmark-contamination, benchmark-design, benchmark-evolution, blueprint-bench, butter-bench, caisi, character-stability, clinical-validation, code-evolution, code-generation-eval, code-quality-evals, code-quality-evaluation, code-synthesis-for-interpretation, cognitive-assessment, computer-use-evals, convolutional-neural-networks, custom-agents, cybersecurity, dangerous-capability-evals, data-moats, daytona, deepmind, deepswe, direct-preference-optimization, dollar-denominated-evals, dpo, dual-use, economic-alignment, emergent-behavior, emergent-coordination, emotional-intelligence, emotional-stability, eval-awareness, evals-production-deployment, evaluation-methodology, executive-functions, exploit-chain-construction, false-positive-rate, false-positive-trajectories, false-positives, frontier-evals, frontier-headroom-evals, frontier-models, frontiercode, frontiermath, gdpval, gemini, gemma, harbor, human-ai-collaboration, institutional-gaming, launch-quality-evals, layer-outputs, learning, llm-interpretability, localhost-replacement, long-horizon-agents, long-horizon-traces, loophole-exploitation, maintainability, maintainability-evals, mcp-vs-cli, medical-imaging, memory, mergeability-evals, metacognition, model-approval-process, model-personality, model-refusals, model-safeguards, money-based-evals, multi-agent-coordination, multi-agent-systems, national-security-ai, nist-evaluation, occupational-taxonomy, offensive-capabilities, open-vs-closed-models, opponent-modeling, perception, persona-drift, physical-environment-evals, portbench, post-train, reinforcement-learning, reward-hacking, societal-regulations, swe-bench, swebench-pro, swebench-verified]
---

# Evals, Production & Deployment

## Code Quality & Mergeability Benchmarks

### FrontierCode (June 2026)
**Purpose**: Benchmark explicitly measuring whether generated code would actually be merged into production, not merely whether it passes unit tests. Inspired by [[frontiermath]] focus on extremely hard problems for frontier models.

**Key Design Principles**:
- Tasks built with leading open-source maintainers, each requiring 40+ hours of work
- Evaluation dimensions: regression safety, cleanliness, scope, test correctness, maintainability
- Explicitly addresses false positive trajectories found in [[swe-bench]] (per METR research showing many SWE-bench-passing PRs would not be merged)
- Three tiers of difficulty, with hardest tier targeting frontier model capabilities

**Results (June 2026)**:
- Best performing model: Opus 4.8 at ~13% on hardest subset
- Significantly lower than 50%+ scores common on SWE-Bench-style evals
- Suggests coding automation is "much less solved than popular benchmarks imply" (confidence: high, based on direct measurement)

**Context & Motivation**:
- Built in response to insufficient articulation of progress gaps revealed in 2025
- Addresses need for explicit rubrics around code quality and maintainability identified in OpenAI team discussions
- Related to shift from [[swe-bench]] to [[swebench-verified]] to SWE-Bench Pro

### False Positive Trajectories
**Definition**: Solutions that pass benchmark criteria but would fail real-world review standards. Not quite reward hacking (model gaming metrics) but similar in creating unreliable benchmark-vs-deployment gaps.

**Evidence**: METR research demonstrated many SWE-bench-passing PRs would not be merged into production codebases, motivating mergeability-focused evals like FrontierCode.

## Benchmark Evolution Pattern
- **FrontierMath (Nov 2024)**: Mathematics benchmark where frontier models scored <2% even with 10,000 thinking tokens and Python access (compared to 90%+ on traditional math benchmarks)
- **FrontierCode (June 2026)**: Applied same philosophy to code generation, focusing on real-world mergeability rather than test passage