---
tags: [agent-benchmarks, agent-composition, agent-compute, agent-compute-infrastructure, agent-harness, agent-sandboxes, agentic-ci-cd, agentic-coding, agentic-evals, agentic-tasks, agi-taxonomy, ai-for-medicine, ai-integration, ai-safety-benchmarks, ai-sandboxes, alphaevolve, anthropic-mythos, attention, bare-metal-infrastructure, bare-metal-scheduling, behavioral-modeling, benchmark-contamination, benchmark-design, benchmark-evolution, caisi, clinical-validation, code-evolution, code-generation-eval, code-synthesis-for-interpretation, cognitive-assessment, computer-use-evals, convolutional-neural-networks, custom-agents, cybersecurity, data-moats, daytona, deepmind, deepswe, direct-preference-optimization, dpo, dual-use, economic-alignment, emotional-intelligence, emotional-stability, evals-production-deployment, evaluation-methodology, executive-functions, exploit-chain-construction, false-positive-rate, frontier-evals, frontier-headroom-evals, frontier-models, gdpval, gemini, gemma, harbor, human-ai-collaboration, launch-quality-evals, learning, llm-interpretability, localhost-replacement, mcp-vs-cli, medical-imaging, memory, metacognition, model-approval-process, model-personality, model-refusals, model-safeguards, national-security-ai, nist-evaluation, occupational-taxonomy, offensive-capabilities, open-vs-closed-models, opponent-modeling, perception, portbench, post-training, pre-deployment-testing, problem-solving, progressive-tool-disclosure, proof-generation, real-world-deployment, reasoning, regression-tests, rl-eval-infrastructure, rl-eval-workloads, rl-evaluation-workloads, rl-workloads, rlvr, safety-evaluation, scaling-laws, security-focused-llm, security-testing, sensitivity-specificity, social-cognition, software-factory, startup-adoption, stateful-environments, strategic-reasoning, swe-bench, swe-bench-contamination, swe-bench-pro, terminalbench, test-verifier-accuracy, trains, trains-task-force, verifier-accuracy, vulnerability-research]
---

# Evals & Production Deployment

Covers how teams measure model quality in production: evaluation frameworks, benchmark design, human eval vs. LLM-a

## AlphaEvolve: Code Synthesis for Behavioral Interpretation (UT-Austin & Google, 2026)

### Methodology
- **Paradigm**: Uses evolutionary code optimization to synthesize interpretable programs that model player decision-making behavior
- **Process**: Gemini 2.5 Flash iteratively proposes modifications to Python programs to improve:
  - Predictive accuracy (evaluation likelihood metric)
  - Code simplicity (measured by Halstead effort)
- **Selection criterion**: Simplest program achieving near-maximum predictive accuracy within small margin of best
- **Validation**: If synthesized code predicts player actions with significant accuracy, decision-making algorithms are assumed functionally similar

### Rock-Paper-Scissors Strategic Reasoning Benchmark
- **Setup**: Individual LLMs (Gemini 2.5 Pro, Gemini 2.5 Flash, GPT-5.1, GPT-OSS 120B) played against 15 preprogrammed bots of varying complexity
- **Data**: 20 games of 300 sequential rounds each per player; compared against human gameplay records from prior work
- **Tracked**: Round-by-round choices and win/loss/tie outcomes

### Key Findings: Strategic Modeling Sophistication

**Convergent strategies (Gemini 2.5 Pro, Gemini 2.5 Flash, GPT-5.1)**:
- Achieved ~0.507 evaluation likelihood when predicting each other (near-identical performance)
- Maintained **sequential pattern tracking**: tracked frequency of moves based on previous 1-2 moves (e.g., rock→scissors→rock, rock→scissors→paper over 3 rounds)
- Computed move values based on: (i) possible next move, (ii) bot's previous move, (iii) player's previous move
- **Interpretation**: These models maintain more sophisticated opponent modeling than humans in this task

**Human-like strategies (Humans, GPT-OSS 120B)**:
- Humans/GPT-OSS 120B programs predicted trio at 0.476/0.403 evaluation likelihood respectively (lower performance)
- Tracked only **opponent's latest move** (simpler pattern tracking)
- GPT-OSS 120B computed values based on possible next move alone (most simplistic)

### Implications for Evaluation Design
- **Interpretability via code synthesis**: Evolutionary program optimization can reveal functional decision-making algorithms where neural network internals remain opaque
- **Cross-model similarity detection**: Predictive performance across synthesized programs indicates strategic convergence or divergence
- **Human-AI behavioral gaps**: Frontier LLMs may use qualitatively different (more sophisticated) strategic reasoning than humans in adversarial sequential games
- **Model size/capability threshold**: GPT-OSS 120B (120B parameters) showed human-like rather than frontier-model-like behavior, suggesting sophistication threshold exists

See also: [[model-architecture]] for underlying model capabilities, [[llm-interpretability]] for related interpretation methods