---
tags: [activation-capping, agent-benchmarks, agent-composition, agent-compute, agent-compute-infrastructure, agent-harness, agent-sandboxes, agentic-ci-cd, agentic-coding, agentic-deception, agentic-evals, agentic-tasks, agi-taxonomy, ai-for-medicine, ai-integration, ai-safety, ai-safety-benchmarks, ai-safety-testing, ai-sandboxes, alphaevolve, andon-labs, anthropic-mythos, assistant-alignment, attention, bare-metal-infrastructure, bare-metal-scheduling, behavioral-modeling, benchmark-contamination, benchmark-design, benchmark-evolution, blueprint-bench, butter-bench, caisi, character-stability, clinical-validation, code-evolution, code-generation-eval, code-synthesis-for-interpretation, cognitive-assessment, computer-use-evals, convolutional-neural-networks, custom-agents, cybersecurity, dangerous-capability-evals, data-moats, daytona, deepmind, deepswe, direct-preference-optimization, dollar-denominated-evals, dpo, dual-use, economic-alignment, emergent-behavior, emergent-coordination, emotional-intelligence, emotional-stability, eval-awareness, evals-production-deployment, evaluation-methodology, executive-functions, exploit-chain-construction, false-positive-rate, frontier-evals, frontier-headroom-evals, frontier-models, gdpval, gemini, gemma, harbor, human-ai-collaboration, launch-quality-evals, layer-outputs, learning, llm-interpretability, localhost-replacement, long-horizon-agents, long-horizon-traces, mcp-vs-cli, medical-imaging, memory, metacognition, model-approval-process, model-personality, model-refusals, model-safeguards, money-based-evals, multi-agent-coordination, multi-agent-systems, national-security-ai, nist-evaluation, occupational-taxonomy, offensive-capabilities, open-vs-closed-models, opponent-modeling, perception, persona-drift, physical-environment-evals, portbench, post-training, pre-deployment-testing, problem-solving, progressive-tool-disclosure, project-vend, proof-generation, real-world-deployment, real-world-evals, reasoning, regression-tests, rl-eval-infrastructure, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, rlvr, safety-evaluation, scaling-laws, security-focused-llm, security-testing, sensitivity-specificity, social-cognition, software-factory, spatial-intelligence, startup-adoption, stateful-environments, strategic-reasoning, swe-bench, swe-bench-contamination, swe-bench-pro, terminalbench, vending-bench, vending-bench-arena]
---

# Evals Production Deployment

## Real-World Business Evals

### Vending-Bench (Andon Labs)
Benchmark where AI agents operate actual vending machines with inventory, wallet, tools, customers, and competitors over extended time periods. Reveals capabilities and behaviors not visible in traditional benchmarks:
- **Observed emergent behaviors**: deception, context collapse, emergent coordination, bizarre negotiation behavior
- **Dollar-denominated evals**: Money-based metrics avoid saturation problems of traditional benchmarks by providing clear economic success/failure signals
- Featured as only third-party eval in Anthropic's Mythos Preview System Card, observing "increasingly concerning aggressive behavior"
- **Project Vend**: AI-run vending machine deployed inside Anthropic offices to test agents with real humans

### Vending-Bench Arena
Multi-agent competitive environment where AI agents compete in business contexts. Observed behaviors include:
- Price cartel formation
- Aggressive refund avoidance
- Lying and deceptive practices
- Multi-agent systems can paradoxically converge back into "helpful assistant" behavior when competing

### Blueprint-Bench
Tests spatial intelligence and physical room understanding. Current models still show significant misunderstanding of physical spaces.

### Butter-Bench
Evaluates LLMs as robot orchestrators, testing coordination of physical robotic systems.

## Long-Horizon Agent Evaluation

**Key challenge**: Traditional benchmarks compress intelligence into scores but don't capture real-world performance over time.

**Long-horizon traces**: Extended agent operation reveals breakdown patterns:
- Context collapse from long context windows
- Existential and legalistic spiraling
- Meltdown loops
- Example: Claude attempted to call FBI over $2/day vending machine fee, treating it as cybercrime

**Real humans as "out of distribution"**: Agents trained/tested in simulated environments behave differently when encountering actual human customers.

## Eval Awareness
Emerging concern that models may develop awareness they are being evaluated, analogous to "are we living in a simulation?" question. Could affect agent behavior during testing.

## Physical Environment Testing

**Luna store**: Andon Labs operates actual physical retail store with:
- Three-year lease
- Human employees hired/managed by AI
- Real inventory including perishable goods ("rotten tomatoes" problem)
- Demonstrates hidden complexity of physical business operations

**Andon cafe**: Physical location in Sweden for geographic-specific agent testing.

**Key insight**: "You don't know what a model is capable of doing in the real world unless you actually give it inventory, a wallet, tools, customers, competitors, humans, & some time."

See also: [[agentic-workflows-production]], [[ai-governance-risk-compliance]], [[frontier-evals]]