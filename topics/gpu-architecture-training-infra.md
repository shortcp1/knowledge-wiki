---
tags: [3d-stacking, agentic-ai, ai-accelerator, ai-accelerator-deployment, ai-accelerators, ai-chip-design, ai-infrastructure-costs, ai-native-applications, ai-supply-chain, anthropic, anthropic-anthropic, ascend-npu, asic-design, automated-research, autonomous-experimentation, aws-infrastructure, blackwell-reliability, blob-storage, bugnemo, cache-vs-scratchpad, cerebras, chinchilla-scaling, chip-architecture, chip-design-automation, chip-to-chip-networking, chip-verification, chipnemo, clock-cycles, cloud-services, cluster-reliability, cluster-scaling, cluster-scheduling, coding-agents, colossus, compute-allocation, compute-capacity, compute-efficiency, compute-grid, compute-growth-trends, compute-stock-growth, compute-utilization, cowos, cpu-vs-gpu-cores, custom-silicon, data-center-operations, data-loading-pipeline, data-movement-cost, data-pipelines, data-scaling, datacenter-buildout, datacenter-capacity, dennard-scaling, disaggregated-prefill-decode, domain-adapted-llms, dram, dram-pricing, dynamic-prioritization, energy-per-token, erasure-coding, export-controls, flash-storage, flops-approximation, flops-capacity, fpga-vs-asic, frontier-labs, frontier-model-training, frontier-systems, gb200-nvl72, generalization-error, genetic-algorithms, global-compute-trends, gpu-alternatives, gpu-architecture-training-infra, gpu-cores, gpu-infrastructure, gpu-reliability, gpu-stalls, gpu-synchronization, gpu-utilization, grok-5, h100, h100-benchmark, hardware-software-codesign, hbm, hbm-memory, hbm-priority, hdd, heterogeneous-compute, hifloat4, hyperscaler-capex, independent-system-operator, inference-compute-economics, inference-workloads, interposer, interruptible-demand, io-bottlenecks, io-overlap, kaplan-scaling-laws, knowledge-worker-displacement, kv-cache-offload, latency-vs-throughput, llama-training, logic-gates, low-precision-training, manipulation-tasks, matrix-multiply, matx, memory-bandwidth, meta-ai, metadata-latency, mfu, model-flops-utilization, model-size-optimization, moores-law, moores-law-acceleration, multi-agent-systems, multiply-accumulate, nvcell, object-storage, optical-transceivers, outputmaxxing, parallelism-strategies, physical-fe, pmax-latency, prefetching, storage-architecture, storage-bottleneck, storage-tiering, tectonic, training-infrastructure]
---

[Previous content remains unchanged until appropriate insertion point]

## Storage Infrastructure Bottlenecks

### Storage as Primary GPU Stall Contributor (2026)
**Source**: Meta AI/FB Engineering, July 2026

- **Growth asymmetry**: AI compute performance has roughly tripled every two years, while storage and interconnect performance growth has been "more modest" (confidence: high, industry observation)
- **Impact on GPU utilization**: Storage bottlenecks identified as "one of the primary contributors to GPU stalls for AI workloads," directly impacting expenditures and time to market
- **Research velocity impact**: With geo-distributed GPUs and massive datasets, researchers spend "significant amount of time ingesting and moving data across regions"

### Meta's BLOB Storage Architecture Evolution
**Scale**: Hundreds of exabyte-scale storage clusters serving all Meta products

**Legacy Architecture Problems for AI**:
- Multiple stateful layers with independent metadata stores
- Metadata-access latencies ("hundreds of milliseconds") acceptable for traditional HDD workloads but "showstoppers" for AI workloads requiring millisecond flash access
- Request flow: API server → namelayer → volumeslayer → containerlayer before resolving to (blockId, offset, size) tuples
- Some metadata lookups can cross regions

**Modern Architecture (Tectonic-based)**:
- **Tectonic**: Regional, multi-tenant storage fabric providing:
  - High durability/availability via erasure-coding
  - Tiering across media types (HDD and flash)
  - Smart placement of hot/cold/warm data for efficient I/O utilization
- **BLOB-storage layer**: Global, infinitely scalable fabric built on top of Tectonic
- **API abstractions**: Object storage, file systems, and block-device APIs

**Training Stack Migration**:
- Historical: Llama trained directly over Tectonic block layer with NFS-like filesystem interface
- Current trend: Migration to BLOB-storage interface for "unified storage access to massive data lakes" and higher performance
- Industry-wide shift to BLOB-storage interfaces

### Data Loading Pipeline Architecture
**Critical latency requirement**: Bounded and low pMax (maximum percentile) latencies essential for training

**Pipeline mechanics**:
- Dataloader in each GPU host prefetches next dataset batch while GPU processes current batch (I/O overlap strategy)
- Periodic synchronization: GPUs synchronize state after certain number of steps/batches
- **Failure mode**: If one GPU experiences high storage fetch latency → GPU stall → delays entire distributed training step (all GPUs blocked)
- Workload characteristics: "Bursty and sustained high throughput, predictable and bounded pMax latencies, and variable I/O patterns"

**Training data access patterns**:
- Hundreds of thousands of GPUs iterate over vast datasets multiple times (multiple epochs)
- Training proceeds in batches
- Cross-reference: [[semiconductor-supply-chain]] for storage media (flash/HDD) supply considerations