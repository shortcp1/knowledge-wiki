---
tags: [model-benchmarking, swbench, agentic-workflows, token-pricing, vision-models, multi-agent-orchestration, safety-guardrails, model-selection-strategy, evals-production-deployment]
---

---
tags: [activation-capping, agent-based-simulation, agent-benchmarks, agent-composition, agent-compute, agent-compute-infrastructure, agent-harness, agent-sandboxes, agentic-ci-cd, agentic-coding, agentic-deception, agentic-evals, agentic-tasks, agi-taxonomy, ai-for-medicine, ai-integration, ai-safety, ai-safety-benchmarks, ai-safety-testing, ai-sandboxes, alphaevolve, andon-labs, anthropic-mythos, assistant-alignment, attention, bare-metal-infrastructure, bare-metal-scheduling, behavioral-modeling, benchmark, benchmark-contamination, benchmark-design, benchmark-evolution, blueprint-bench, butter-bench, caisi, character-stability, clinical-validation, code-evolution, code-generation-eval, code-quality-evals, code-quality-evaluation, code-synthesis-for-interpretation, cognitive-assessment, computer-use-evals, concordia, convolutional-neural-networks, custom-agents, cybersecurity, dangerous-capability-evals, data-moats, daytona, deepmind, deepswe, direct-preference-optimization, diversity-metrics, dollar-denominated-evals, dpo, dual-use, economic-alignment, emergent-behavior, emergent-coordination, emotional-intelligence, emotional-stability, eval-awareness, evals-production-deployment, evaluation-methodology, evolutionary-algorithms, evolutionary-optimization, executive-functions, exploit-chain-construction, false-positive-rate, false-positive-trajectories, false-positives, frontier-evals, frontier-headroom-evals, frontier-models, frontiercode, frontiermath, gdpval, gemini, gemma, harbor, human-ai-collaboration, human-simulation, institutional-gaming, launch-quality-evals, layer-outputs, learning, llm-interpretability, localhost-replacement, long-horizon-agents, long-horizon-traces, loophole-exploitation, maintainability, maintainability-evals, mcp-vs-cli, medical-imaging, memory, mergeability-evals, metacognition, model-approval-process, model-personality, model-refusals, model-safeguards, money-based-evals, multi-agent-coordination, multi-agent-systems, national, one-shot-design, pdf-parsing, swbench-pro, task-model-matching, vision-evals]

## SWBench Pro Results (June 2026)

[[claude-fable-5]]: 80% (significantly outperforms competitors)
[[claude-opus]] 4.8: <80% (exact number not specified)
[[gpt-4-5]]: <80%
[[gemini]] 3.1 Pro: <80%

**Note**: High benchmark performance on SWBench Pro does not guarantee strong performance across all real-world tasks. See [[benchmark-vs-deployment]] for documented gaps.

## Real-World Performance Patterns

**Task-Model Matching**: Critical insight from production deployment - matching model intelligence to task complexity yields better outcomes than always using the most capable model.

### Strong Performance Areas:
- Vision tasks (particularly document formatting, PDF parsing)
- Long-horizon technical problems requiring extreme detail
- Complex document structure and layout
- Technical investigation and debugging

### Weak Performance Areas:
- One-shot design tasks (produces "fundamentally terrible design" - gray, black, red color schemes, poor aesthetics)
- Product specifications and PRDs (overly detailed, dense, hard to parse)
- Strategic/conceptual work
- Frontend development
- MVP scoping (tends toward overly narrow, conservative implementations)

**Document Formatting Example**: In handwriting worksheet generation for educational use, [[claude-fable-5]] dramatically outperformed [[claude-opus]] 4.8 with better spacing, clearer layout, and appropriate white space.

**Design Output**: Contested claim - despite strong benchmark performance, real-world one-shot design tasks produced poor visual output. This represents a significant [[benchmark-vs-deployment]] gap.

## Multi-Agent Reliability

[[claude-fable-5]] multi-agent orchestration: Technically functional but not production-reliable
- Dynamic workflows and subagent capabilities work in some cases
- Frequent stalls observed in long-running tasks (3+ hours)
- Reliability issues prevent consistent deployment

See [[multi-agent-systems]] for broader context.