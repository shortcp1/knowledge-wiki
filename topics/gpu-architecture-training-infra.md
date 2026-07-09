---
tags: [agent-experience, bursty-workloads, elastic-inference, gpu-architecture-training-infra, gpu-snapshotting, multi-cloud-capacity, programmatic-infrastructure, rl-rollouts, sandbox-environments, serverless-functions, serverless-gpu]
---

---
tags: [3d-stacking, agentic-ai, ai-accelerator, ai-accelerator-deployment, ai-accelerators, ai-infrastructure-costs, ai-native-applications, ai-supply-chain, anthropic, anthropic-anthropic, ascend-npu, asic-design, automated-research, autonomous-experimentation, aws-infrastructure, blackwell-reliability, blob-storage, bugnemo, cache-vs-scratchpad, cerebras, chinchilla-scaling, chip-architecture, chip-design-automation, chip-to-chip-networking, chip-verification, chipnemo, clock-cycles, cloud-services, cluster-reliability, cluster-scaling, cluster-scheduling, coding-agents, colossus, compute-allocation, compute-capacity, compute-capacity-utilization, compute-efficiency, compute-grid, compute-growth-trends, compute-rental-markets, compute-scarcity, compute-stock-growth, compute-utilization, cowos, cpu-vs-gpu-cores, custom-silicon, data-center-operations, data-loading-pipeline, data-movement-cost, data-pipelines, data-scaling, datacenter-buildout, datacenter-capacity, dennard-scaling, disaggregated-prefill-decode, domain-adapted-llms, dram, dram-pricing, dynamic-prioritization, energy-per-token, erasure-coding, export-controls, flash-storage, flops-approximation, flops-capacity, fpga-vs-asic, frontier-labs, frontier-model-training, frontier-systems, gb200-nvl72, generalization-error, genetic-algorithms, global-compute-trends, gpu-alternatives, gpu-architecture-training-infra, gpu-cores, gpu-infrastructure, gpu-reliability, gpu-rental-economics, gpu-stalls, gpu-synchronization, gpu-utilization, grok-5, h100, h100-benchmark, hardware-software-codesign, hbm, hbm-memory, hbm-priority, hdd, heterogeneous-compute, hifloat4, hyperscaler-capex, independent-system-operator, inference-compute-economics, inference-workloads, interposer, interruptible-demand, io-bottlenecks, io-overlap, kap]

## Agent-Era Infrastructure Requirements

**Source**: Modal CTO Akshat Bubna (Latent Space Podcast, July 2026)

### Developer Experience → Agent Experience Shift

**Core Thesis**: Traditional cloud infrastructure was designed for human developers who could read documentation, reason through YAML configuration, and understand dashboards when debugging. Agents lack this capability and require fundamentally different infrastructure patterns.

**Key Requirements for Agent-Operated Infrastructure**:
- Programmatic control without human context-filling
- Fast iteration and feedback loops with complete context embedded
- Isolated environments agents can spin up and tear down autonomously
- Observability that matters more than reading code (since agents write the code)

### Bursty Compute Workloads

**Infrastructure Mismatch**: Kubernetes was not designed for bursty, compute-heavy AI workloads that characterize modern agent systems.

**RL Rollout Scale**: Production RL rollouts can require **100,000 sandboxes** simultaneously - fundamentally different from traditional web application scaling patterns.

**GPU Snapshotting**: Critical capability for managing inference workload burstiness and cold start optimization.

### Modal's Supercloud Strategy

**Multi-Cloud Capacity Pool**: Modal operates across **17 cloud providers** to aggregate compute capacity and handle burst workloads.

**Compute Strategy Components**:
- Batch tiers for cost optimization
- Capacity planning across heterogeneous providers
- Dynamic allocation based on workload characteristics

### Programmatic Research Infrastructure

**Auto-Research Capabilities**:
- Model-guided hyperparameter sweeps
- Agents autonomously launching GPU experiments
- Serverless multi-node training for post-training and research workloads

**Networked Infrastructure**:
- Networked containers with private IPv6
- RDMA support for high-performance inter-node communication
- Sidecar patterns for agent coordination