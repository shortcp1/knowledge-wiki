---
tags: [agency-dexterity, ai-agents, ai-in-operations, commercial-viability, embodied-ai, general-purpose-robots, hyperscale-operations, infrastructure-efficiency, labor-automation, manufacturing-automation, operational-automation, performance-optimization, physical-automation, regression-detection, robotics, robotics-autonomy]
---

# AI in Operations

Covers AI in internal operations: workflow automation, process mining, IT service management, supply chain optimization, document processing, and physical robotics automation. Tracks both standalone operations AI tools and AI features in ERP/BPM platforms.

Key questions tracked: Where is AI actually replacing manual processes end-to-end vs. augmenting? What is the integration cost of AI operations tools in legacy environments? How do robotics levels of autonomy map to commercial viability?

## Key Claims
<!-- agent-maintained -->

### Infrastructure & Performance Engineering

**Meta Capacity Efficiency AI Agent Platform (Meta, April 2026)**
- **Business Problem**: At hyperscale (3B+ users), even 0.1% performance regressions translate to significant power consumption. Human engineering time is bottleneck for investigating/resolving performance issues. Need both offense (proactive optimization finding) and defense (regression detection/mitigation).
- **AI Pattern**: Unified agentic platform with two layers:
  - **MCP Tools**: Standardized interfaces for LLMs to invoke code (query profiling data, fetch experiment results, retrieve config history, search code, extract docs)
  - **Skills**: Encoded domain expertise of senior efficiency engineers into reusable, composable reasoning patterns (e.g., "consult top GraphQL endpoints for endpoint latency regressions")
- **Success Factors**:
  - Realized offense and defense share same underlying structure, enabling single unified platform
  - Separation of tools (what to invoke) from skills (domain expertise/reasoning patterns)
  - Composability and reusability of encoded expertise
  - Standardized tool interfaces allowing generalized LLM to apply senior engineer domain knowledge
- **Outcomes**:
  - Recovered hundreds of megawatts (MW) of power
  - Compressed ~10 hours of manual investigation into ~30 minutes for diagnoses
  - AI agents

### Physical Robotics Automation

**Robotics Levels of Autonomy Framework (SemiAnalysis, March 2025)**

A classification system for general-purpose robotics capabilities, organized around commercial viability rather than mere technical possibility. Each level builds sequentially on prior capabilities.

- **Framework Axes**:
  - **Agency**: Planning and decision-making capabilities
  - **Dexterity**: Physical manipulation and interaction skills
- **Core Principle**: "Robot autonomy is inherently linked to applications: creating value only through actions often irrecoverable. Therefore, capabilities are derived from reliability and capability. Once reliability is proven, the robot must deliver sufficient throughput to justify its cost."
- **Historical Context**: Previous intelligent robotics attempts "overpromised and underdelivered" but "were too early." Modern AI paradigms convert robot roadblocks into data problems.

**Level 0: Scripted Motion**
- **Unlock**: High Accuracy, High Repeatability
- **Capabilities**: 24/7 Automation, High Throughput
- **Requirements**: Pre-programmed entirely, static environments and tasks
- **2025 Deployment**: Industry standard in automotive and electronics factories
- **Note**: Not general-purpose; single-purpose systems that dominated manufacturing for decades

**Level 1: Intelligent Pick and Place**
- **Unlock**: Generalizable Perception, Generalizable Grasping
- **Capabilities**: Stationary Pick and Place
- **2025 Deployment**: Adopted in parcel logistics centers for pick and place sorting, increasing penetration in additional warehousing markets as capabilities and integrations improve
- **Example**: Covariant systems in warehouse environments

**Level 2: Autonomous Mobility**
- **Unlock**: High-level Planning, Spatial Reasoning, Robust Locomotion
- **Capabilities**: Open world Navigation and Traversal
- **2025 Deployment**: Early production phases for inspection and data collection roles (construction sites, oil & gas refineries, critical infrastructure)
- **Status**: General-purpose robots already working in early production phases

**Level 3: Low-skill Manipulation**
- **Unlock**: Generalizable Manipulation
- **Capabilities**: Advanced Pick and Place, Mobile Manipulation
- **2025 Deployment**: Early pilot stages automating low-skill jobs
- **Status**: Demonstrating viability in early trials
- **Note**: Requires performing basic, noncritical, low-skill tasks

**Level 4 & 5**: Not detailed in article (content truncated)

**Progression Outlook**: "This evolution will accelerate faster than most realize" with mass labor replacement "on the horizon" as general-purpose robots "slowly add more capabilities until all tasks are feasible."

See also: [[foundation-models]] for AI paradigms enabling robotics progress