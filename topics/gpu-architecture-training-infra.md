---
tags: [3d-stacking, agentic-ai, ai-accelerator, ai-accelerator-deployment, ai-accelerators, ai-chip-design, ai-infrastructure-costs, ai-native-applications, ai-supply-chain, anthropic, anthropic-anthropic, ascend-npu, asic-design, automated-research, autonomous-experimentation, aws-infrastructure, blackwell-reliability, bugnemo, cache-vs-scratchpad, cerebras, chinchilla-scaling, chip-architecture, chip-design-automation, chip-to-chip-networking, chip-verification, chipnemo, clock-cycles, cloud-services, cluster-reliability, cluster-scaling, cluster-scheduling, coding-agents, colossus, compute-allocation, compute-capacity, compute-efficiency, compute-grid, compute-growth-trends, compute-stock-growth, compute-utilization, cowos, cpu-vs-gpu-cores, custom-silicon, data-center-operations, data-movement-cost, data-pipelines, data-scaling, datacenter-buildout, datacenter-capacity, dennard-scaling, disaggregated-prefill-decode, domain-adapted-llms, dram, dram-pricing, dynamic-prioritization, energy-per-token, export-controls, flops-approximation, flops-capacity, fpga-vs-asic, frontier-labs, frontier-model-training, frontier-systems, gb200-nvl72, generalization-error, genetic-algorithms, global-compute-trends, gpu-alternatives, gpu-architecture-training-infra, gpu-cores, gpu-infrastructure, gpu-reliability, gpu-utilization, grok-5, h100, h100-benchmark, hardware-software-codesign, hbm, hbm-memory, hbm-priority, heterogeneous-compute, hifloat4, hyperscaler-capex, independent-system-operator, inference-compute-economics, inference-workloads, interposer, interruptible-demand, kaplan-scaling-laws, knowledge-worker-displacement, kv-cache-offload, latency-vs-throughput, logic-gates, low-precision-training, manipulation-tasks, matrix-multiply, matx, memory-bandwidth, mfu, model-flops-utilization, model-size-optimization, moores-law, moores-law-acceleration, multi-agent-systems, multiply-accumulate, nvcell, optical-transceivers, outputmaxxing, parallelism-strategies, physical-feedback-loop, pipeline-registers, platform-shifts, power-law, prefill-decode, prefixrl, reinforce, reinforcem, robot-fleet-utilization, rtx-5090, self-improving-robots, yam-manipulator]
---

[Existing content remains unchanged...]

## Edge/Workstation Hardware

### NVIDIA RTX 5090

**Robotics Deployment**: Used in NVIDIA's ENPIRE physical robot self-improvement framework
- Single RTX 5090 per workstation handles: FastAPI server, policy inference, agent execution
- Deployed with YAM (Yet Another Manipulator) bimanual robot arms
- **Fleet utilization challenge**: As robot fleets scale, GPU active utilization increases while robot utilization (MRU) decreases - agents spend significant time on non-compute tasks (reading logs, code generation, debugging, LLM API waits)

See also: [[ai-engineering-agents]] for physical robotics agent architectures