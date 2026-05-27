---
tags: [compute-costs, transformer-architecture, training-cost, inference-cost, flops-calculation, model-parameters, token-length, gpu-architecture-training-infra]
---

=== gpu-architecture-training-infra ===
---
tags: [3d-stacking, agentic-ai, ai-accelerator, ai-infrastructure-costs, ai-native-applications, ai-supply-chain, anthropic, anthropic-anthropic, ascend-npu, asic-design, automated-research, aws-infrastructure, blackwell-reliability, cache-vs-scratchpad, cerebras, chip-architecture, chip-to-chip-networking, clock-cycles, cloud-services, cluster-scaling, colossus, compute-capacity, cowos, cpu-vs-gpu-cores, custom-silicon, data-movement-cost, datacenter-buildout, datacenter-capacity, disaggregated-prefill-decode, dram, dram-pricing, energy-per-token, export-controls, fpga-vs-asic, frontier-model-training, gb200-nvl72, gpu-alternatives, gpu-architecture-training-infra, gpu-cores, gpu-infrastructure, gpu-reliability, grok-5, h100, h100-benchmark, hardware-software-codesign, hbm, hbm-memory, hbm-priority, heterogeneous-compute, hifloat4, hyperscaler-capex, inference-compute-economics, inference-workloads, interposer, knowledge-worker-displacement, kv-cache-offload, latency-vs-throughput, logic-gates, low-precision-training, matrix-multiply, matx, memory-bandwidth, mfu, model-flops-utilization, multiply-accumulate, optical-transceivers, pipeline-registers, prefill-decode, reinforcement-learning, return-on-invested-capital, roic-targets, semicap-equipment, semiconductor-bottlenecks, shoreline-routing, systolic-arrays, tco, tpu-architecture, tpu-design, training-benchmarks, training-tco, trainium2, tsv, weak-to-strong-supervision]
---

# GPU Architecture & Training Infrastructure

Covers NVIDIA GPU generations (Hopper, Blackwell, Rubin), custom AI accelerators (Google TPUs, AWS Trainium, Microsoft Maia), and how training clusters are designed and operated. Includes networking topology (InfiniBand vs. Ethernet), power constraints, and cooling.

Key questions tracked: What is the real utilization of large training clusters? How are custom ASICs closing the gap on NVIDIA? What limits the next 10x in training compute?

## Key Claims

### Compute Supply-Demand Dynamics (April 2023)
- **Demand exceeds supply by 10x**: Industry sources report compute demand outstrips available supply by a factor of 10 (a16z, April 2023)
  - **Confidence**: Medium (based on industry sources, not public data)
- **Compute as determining success factor**: Access to compute resources at lowest total cost has become primary determining factor for AI company success
- **Capital allocation**: Many AI companies spending >80% of total capital raised on compute resources (a16z observation, April 2023)

### Training Cluster Scale (as of Q3 202