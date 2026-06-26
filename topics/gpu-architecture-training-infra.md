---
tags: [3d-stacking, agentic-ai, ai-accelerator, ai-chip-design, ai-infrastructure-costs, ai-native-applications, ai-supply-chain, anthropic, anthropic-anthropic, ascend-npu, asic-design, automated-research, aws-infrastructure, blackwell-reliability, bugnemo, cache-vs-scratchpad, cerebras, chinchilla-scaling, chip-architecture, chip-design-automation, chip-to-chip-networking, chip-verification, chipnemo, clock-cycles, cloud-services, cluster-reliability, cluster-scaling, cluster-scheduling, colossus, compute-allocation, compute-capacity, compute-efficiency, compute-grid, compute-utilization, cowos, cpu-vs-gpu-cores, custom-silicon, data-center-operations, data-movement-cost, data-pipelines, data-scaling, datacenter-buildout, datacenter-capacity, disaggregated-prefill-decode, domain-adapted-llms, dram, dram-pricing, dynamic-prioritization, energy-per-token, export-controls, flops-approximation, fpga-vs-asic, frontier-labs, frontier-model-training, frontier-systems, gb200-nvl72, generalization-error, genetic-algorithms, gpu-alternatives, gpu-architecture-training-infra, gpu-cores, gpu-infrastructure, gpu-reliability, gpu-utilization, grok-5, h100, h100-benchmark, hardware-software-codesign, hbm, hbm-memory, hbm-priority, heterogeneous-compute, hifloat4, hyperscaler-capex, independent-system-operator, inference-compute-economics, inference-workloads, interposer, interruptible-demand, kaplan-scaling-laws, knowledge-worker-displacement, kv-cache-offload, latency-vs-throughput, logic-gates, low-precision-training, matrix-multiply, matx, memory-bandwidth, mfu, model-flops-utilization, model-size-optimization, multiply-accumulate, nvcell, optical-transceivers, outputmaxxing, parallelism-strategies, pipeline-registers, power-law, prefill-decode, prefixrl, reinforcement-learning, reinforcement-learning-hardware, return-on-invested-capital, roic-targets, scaling-laws, scaling-laws-compute, scheduling, semicap-equipment, semiconductor-bottlenecks, shoreline-routing, systems-optimization, systolic-arrays, tco, tpu-architecture, tpu-design, training-benchmarks, training-compute, training-infrastructure, training-tco, trainium2, tsv, weak-to-strong-supervision]
---

# GPU Architecture & Training Infrastructure

## Compute-Loss Relationships

### FLOP Approximation for Training

Training compute $C$ in FLOPs can be approximated as $C \approx 6ND$ (Kaplan et al. 2020), where:
- $2ND$ accounts for the forward pass
- $4ND$ accounts for backpropagation
- $N$ = model size (parameter count)
- $D$ = training dataset size (token count)

This approximation is useful for estimating compute requirements when planning training runs and for understanding the relationship between model scale, data scale, and compute budget.

### Optimal Compute Allocation

Scaling laws provide a framework for describing the relationship between compute, loss, model size, and data. At its core, scaling laws address how to allocate compute optimally between $N$ (model size) and $D$ (data size). This compute allocation problem is fundamental to efficient training of frontier models.

See [[scaling-laws]] for detailed power-law relationships and optimization strategies.