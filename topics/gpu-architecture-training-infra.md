---
tags: [3d-stacking, agentic-ai, ai-accelerator, ai-chip-design, ai-infrastructure-costs, ai-native-applications, ai-supply-chain, anthropic, anthropic-anthropic, ascend-npu, asic-design, automated-research, aws-infrastructure, blackwell-reliability, bugnemo, cache-vs-scratchpad, cerebras, chip-architecture, chip-design-automation, chip-to-chip-networking, chip-verification, chipnemo, clock-cycles, cloud-services, cluster-reliability, cluster-scaling, cluster-scheduling, colossus, compute-capacity, compute-efficiency, compute-grid, compute-utilization, cowos, cpu-vs-gpu-cores, custom-silicon, data-center-operations, data-movement-cost, data-pipelines, datacenter-buildout, datacenter-capacity, disaggregated-prefill-decode, domain-adapted-llms, dram, dram-pricing, dynamic-prioritization, energy-per-token, export-controls, fpga-vs-asic, frontier-labs, frontier-model-training, frontier-systems, gb200-nvl72, genetic-algorithms, gpu-alternatives, gpu-architecture-training-infra, gpu-cores, gpu-infrastructure, gpu-reliability, gpu-utilization, grok-5, h100, h100-benchmark, hardware-software-codesign, hbm, hbm-memory, hbm-priority, heterogeneous-compute, hifloat4, hyperscaler-capex, independent-system-operator, inference-compute-economics, inference-workloads, interposer, interruptible-demand, knowledge-worker-displacement, kv-cache-offload, latency-vs-throughput, logic-gates, low-precision-training, matrix-multiply, matx, memory-bandwidth, mfu, model-flops-utilization, multiply-accumulate, nvcell, optical-transceivers, outputmaxxing, parallelism-strategies, pipeline-registers, prefill-decode, prefixrl, reinforcement-learning, reinforcement-learning-hardware, return-on-invested-capital, roic-targets, scheduling, semicap-equipment, semiconductor-bottlenecks, shoreline-routing, systems-optimization, systolic-arrays, tco, tpu-architecture, tpu-design, training-benchmarks, training-infrastructure, training-tco, trainium2, tsv, weak-to-strong-supervision]
---

# GPU Architecture & Training Infrastructure

Covers NVIDIA GPU architecture, training infrastructure systems, and the operational challenges of running frontier-scale AI training.

## Model FLOPs Utilization (MFU)

**Historical MFU benchmarks for frontier training runs:**
- GPT-3: ~21% MFU
- Gopher: ~32% MFU
- Megatron-Turing NLG: ~30% MFU
- PaLM: ~46% MFU
- **Best-in-class today (2025)**: 60-70% MFU (source: Anjney Midha, AMP)

**Recent MFU challenges:**
- xAI reported running at sub-10% MFU (as of 2025), indicating frontier labs can face severe utilization challenges despite access to large clusters
- **Key insight**: Increasing CapEx and GPU count does not automatically translate to better models; frontier AI is "increasingly a systems problem" involving scheduling, utilization, networking, kernels, frameworks, data pipelines, parallelism, and cluster reliability

**Google's utilization standards:**
- At Google, 95% utilization was "considered an outage" - indicating expectation of near-perfect utilization in well-run infrastructure
- Google used interruptible demand and dynamic prioritization internally to maintain high utilization

**Bottleneck hierarchy**: The constraint on frontier training has shifted from pure GPU availability to systems integration: "the thousand small decisions that determine whether your theoretical FLOPs become real training progress"

## Outputmaxxing

**Emerging discipline**: "Output maxing" identified as potential new discipline for frontier systems - optimizing end-to-end throughput rather than focusing solely on individual component metrics.

## Infrastructure Waste

AI infrastructure waste "compounds at frontier-lab scale" - suggesting non-linear scaling challenges as cluster size increases. "Move fast and break things" philosophy identified as incompatible with AI data center operations.

## Data Center Operations

See also: [[build-vs-buy-enterprise-ai]] for compute grid economics, [[semiconductor-supply-chain]] for hardware constraints.

**Community and grid integration challenges:**
- Data center backlash, power grid constraints, and community incentives identified as practical bottlenecks to AI scaling
- Need for community buy-in increasingly important for large-scale deployments

**Independent System Operator model**: Proposed model where compute markets evolve to resemble ISOs that manage electrical grids - making "FLOPs flow like megawatts" with dynamic prioritization across different workloads and customers.

**AMP's scale ambitions**: 1.2GW base-load capacity target with need for 6GW spike capacity - indicating frontier compute planning at unprecedented scale.

## Non-NVIDIA Chip Integration

**Reference architecture value**: Non-NVIDIA chips can benefit from NVIDIA's reference architecture as a starting point, but require "visibility into future model architectures" to establish proper trust boundaries between chip startups and model developers.