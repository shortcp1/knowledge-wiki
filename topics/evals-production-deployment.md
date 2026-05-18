---
tags: [agentic-tasks, ai-integration, benchmark-evals, benchmark-evolution, cybersecurity, data-moats, dual-use, evals-production-deployment, frontier-models, offensive-capabilities, open-vs-closed-models, post-training, rlvr, scaling-laws, startup-adoption]
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
- **Benchmark design critique**: Large Elo differences attributed to specific benchmark performance and IRT extrapolation methodology, particularly CTF-Archive-Diamond, PortBench, and ARC-AGI-2 scoring

### Limitations of Current Evaluation Methods (May 2026)
- **Setup constraints criticized**: Both CAISI and Epoch AI's ECI use "standardized (and simple) setups" that may underestimate true capabilities
  - Coding tasks evaluated with basic bash access and fixed token budgets
  - Does not use production harnesses like Claude Code or OpenCode that models are trained for
  - Does not use model-specific prompting strategies
- **Real-world vs. benchmark gap**: Benchmarks claim tasks "currently not possible" while real deployments succeed

### Artificial Analysis Intelligence Index (April 2026)
- **Composite structure**: ~10 sub-evaluations maintained over time to capture "frontier" of language model capabilities
- **Usage**: Most popular benchmark for tracking open vs. closed model performance gap
- **Industry perception**: Index represents gap as single "distance" number, which obscures nuanced capability differences across domains

### Benchmark Evolution Dynamics (April 2026)
- **Correlation decay**: Benchmarks becoming "no longer as trusted as a correlate to real-world performance" (April 2026)
- **Case study - Gemini 3**: "Incredible benchmarks and remarkable irrelevance in where AI tools currently are being tested and deployed (agents)" illustrates gap between benchmark scores and deployment success
- **Confidence assessment**: Industry at "relative minimum" in confidence in benchmarks during era of rapid post-training improvements (April 2026)
- **Temporal dynamics**: Benchmark focus shifts every 12-18 months as model capabilities and training paradigms evolve
- **Environment acquisition economics**: Leading U.S. labs pay "astronomical sums" for new evaluation environments and datasets; Chinese labs purchase same environments later "at steep discount" to maintain benchmark competitiveness
- **Distillation misconception**: Focus on distillation as key lever for Chinese model progress represents "blind-spot to the importance of RL environments to current training regimes"

### Task Focus Evolution Across LLM Eras (2023-2026)
- **Post-ChatGPT era (~2023)**: Focus on chat, math, and simple code; instruction tuning and RLHF dominated training
- **Chat saturation**: Chat capabilities "saturated and faded quickly"
- **Mid-2025 to present**: Shift to complex coding and "simpler agentic tasks" as reasoning models became default; RLVR (reinforcement learning with verifiable rewards) dominated training
  - Domains shifted from "basic question-answer checking to complex environments"
  - Terminal tasks and code became primary focus
- **Emerging focus (2026)**: Transition to "more diverse knowledge work tasks" including specialized domains:
  - Accounting, law, healthcare
  - Still agentic but require domain expertise
  - Require integrations with existing software or domain-specific tools
- **Data privacy challenge**: Newer domains require training data that is "more private (relative to code, which has swaths of code on GitHub)"
- **Evaluation challenge**: "Evaluating complex language model workflows is also a challenging research problem in itself" with "very limited evidence on the true balance of capabilities" in newer domains

### Cross-reference
See [[lab-dynamics]] for competitive implications of benchmark dynamics on open vs. closed model positioning