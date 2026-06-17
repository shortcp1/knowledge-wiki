---
tags: [agency-dexterity, ai-agents, ai-in-operations, ai-infrastructure-deployment, commercial-viability, data-center-operations, data-center-regulation, embodied-ai, energy-constraints, general-purpose-robots, grid-demand-management, grid-flexibility, hyperscale-operations, infrastructure-efficiency, labor-automation, manufacturing-automation, operational-automation, performance-optimization, physical-automation, power-flexible-data-centers, power-management, regression-detection, robotics, robotics-autonomy, workload-orchestration, workload-throttling]
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

### Data Center Power Management

**Emerald AI Conductor Platform (Emerald AI, December 2025 simulation, 2026 live deployment)**
- **Business Problem**: Data centers face 8-year lead times for new power plant approvals (PJM region), public opposition ($150B+ projects stalled in 2025), and regulatory constraints (state bans, local moratoriums, federal GRID Act proposing to sever data centers from public grids). Infrastructure bottleneck is primary constraint on data center deployment.
- **AI Pattern**: Real-time workload orchestration and power management. AI system ("Conductor") dynamically adjusts data center power consumption during grid stress events while prioritizing time-sensitive computational workloads.
- **Success Factors** (December 2025 simulation):
  - Successfully managed simulated UK grid stress event (Euro 2020 match halftime tea-making surge)
  - Reduced data center power draw during peak demand while maintaining critical operations
  - Demonstrated feasibility of "power-flexible AI factories"
- **Industry & Function**: Data center operations / infrastructure management
- **Quantitative Outcomes**:
  - Duke University research: US grid could offer additional 76 GW capacity (5% of total, enough for projected US data center growth through 2030) to facilities willing to reduce usage just 0.25% of time (~22 hours/year)
  - Princeton/Google research: 500 MW flexible facility in PJM region could reach full operation 3-5 years faster than inflexible facility by flexing <1% of year
  - 2026 live deployment planned in Data Center Alley, Virginia with Nvidia and Digital Realty
- **Generalizability**: 
  - **High generalizability**: Any power-intensive industrial operation facing grid constraints or demand charges (manufacturing, chemical processing, cryptocurrency mining, steel production)
  - **Adjacent industries**: EV charging networks, cold storage facilities, industrial heating/cooling systems
  - **Core pattern**: Real-time workload prioritization + demand response = faster infrastructure deployment and regulatory approval
  - **Regulatory arbitrage**: Flexible power use may avoid proposed regulations targeting inflexible data centers