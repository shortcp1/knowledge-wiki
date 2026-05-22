---
tags: [agent-composition, agent-compute, agent-compute-infrastructure, agent-harness, agent-sandboxes, agentic-ci-cd, agentic-evals, agentic-tasks, agi-taxonomy, ai-for-medicine, ai-integration, ai-safety-benchmarks, ai-sandboxes, anthropic-mythos, attention, bare-metal-infrastructure, bare-metal-scheduling, benchmark-evals, benchmark-evolution, caisi, clinical-validation, cognitive-assessment, computer-use-evals, convolutional-neural-networks, custom-agents, cybersecurity, data-moats, daytona, deepmind, direct-preference-optimization, dpo, dual-use, emotional-intelligence, emotional-stability, evals-production-deployment, executive-functions, exploit-chain-construction, frontier-evals, frontier-headroom-evals, frontier-models, gdpval, gemini, gemma, harbor, human-ai-collaboration, launch-quality-evals, learning, localhost-replacement, mcp-vs-cli, medical-imaging, memory, metacognition, model-approval-process, model-personality, model-refusals, model-safeguards, national-security-ai, nist-evaluation, offensive-capabilities, open-vs-closed-models, perception, portbench, post-training, pre-deployment-testing, problem-solving, progressive-tool-disclosure, proof-generation, real-world-deployment, reasoning, regression-tests, rl-eval-infrastructure, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, rlvr, safety-evaluation, scaling-laws, security-focused-llm, security-testing, sensitivity-specificity, social-cognition, software-factory, startup-adoption, stateful-environments, terminalbench, trains, trains-task-force, vulnerability-research]
---

# Evals & Production Deployment

Covers how teams measure model quality in production: evaluation frameworks, benchmark design, human eval vs. LLM-as-judge, A/B testing for AI, red-teaming, and monitoring for drift and hallucination.

Key questions tracked: What evals actually predict real-world performance? How are teams doing continuous eval in production? What is the state of AI observability tooling?

## Key Claims

### CAISI Evaluation Methodology

#### V4 Assessment (May 2026)
- **Evaluation framework**: Center for

### RL/Eval Infrastructure Requirements (2026)

**Shift in Eval Workload Patterns**: RL and evaluation workloads have become dominant infrastructure consumers, growing from 0% to ~50% of compute usage at companies like Daytona within months (2025-2026).

**Infrastructure Characteristics**:
- **Extreme spikiness**: Workloads go from zero to 100,000 CPUs for single eval or RL training runs
- **Stateful requirements**: Evals need persistent environments that maintain state across multi-step agent interactions
- **Speed requirements**: Need ~60ms sandbox startup for real-time eval workflows
- **Scale requirements**: Production eval systems running ~850,000 sandboxes per day (Daytona's largest customer)
- **Cross-platform needs**: Agentic evals increasingly require Windows and macOS environments, not just Linux

**Benchmark Evolution - Computer Use Assumption**:
- **Research side**: Agentic evals like TerminalBench, GDPVal, and Harbor now assume agents have access to full computer environments
- **Product side**: Major AI products (Perplexity, Manus, Cursor) shipping with "Computer" capability
- **Infrastructure implication**: Eval infrastructure must provide API-accessible, stateful computers rather than simple code execution sandboxes

**Technical Infrastructure Patterns**:
- **Bare metal preference**: Traditional Kubernetes/EKS/GKS infrastructure "painful" for eval workloads due to slow startup and poor spike handling
- **Stateful snapshots**: Critical for multi-session eval scenarios where agent state must persist
- **Dynamic resource scaling**: Must handle orders-of-magnitude changes in compute demand within minutes
- **Batch capability**: Must spin up 50,000+ sandboxes in ~75 seconds for large eval runs

**Generalizability**:
- Any frontier lab doing continuous model evaluation
- Companies running large-scale RL experiments
- Automated red-teaming and safety evaluation systems
- Regression testing for model updates
- Benchmark contamination detection (requires running models in clean environments)
- Multi-agent evaluation scenarios where each agent needs isolated environment