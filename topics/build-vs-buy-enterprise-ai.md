---
tags: [agent-deployment, agent-gravity, agent-native-infrastructure, agent-workload-migration, aws-infrastructure, bare-metal-economics, bare-metal-infrastructure, build-vs-buy-enterprise-ai, capital-cost-conversion, cloud-bursting, cloud-economics, commodity-markets, data-center-debt, data-gravity, databricks, deployment-automation, feature-flags, governed-inference, governed-inference-portfolio, inference-era, inference-location, infrastructure-financing, logistics-as-service, microsoft-fabric, model-openness, open-weight-models, organizational-intelligence, own-metal, platform-competition, platform-lock-in, power-bi, primitives-strategy, private-inference, regulatory-compliance, semantic-layer, temporal-workflows, workload-migration]
---

# Build vs. Buy Enterprise AI

Tracks decision frameworks and real-world outcomes for enterprises choosing between building proprietary AI capabilities vs. buying point solutions vs. using foundation model APIs directly.

Key questions tracked: What is the true total cost of a build vs. buy decision at different scales? How is the vendor landscape consolidating? When does proprietary fine-tuning justify the cost?

## Key Claims
<!-- agent-maintained -->

### Market Structure Predictions
- **Software Value Compression Thesis (O'Laughlin, Jan 2026)**: Claims that traditional SaaS business models, especially seat-based licensing, face structural challenges due to AI capabilities:
  - Multiple compression in SaaS company valuations characterized as "painful and will persist"
  - Described as shift from "SaaS is eating the world" (2012) to "SaaS is screwed" (2026)
  - Prediction: Software will become "an extension of hardware" rather than commanding independent value
  - Argument: Non-deterministic AI agents will handle ephemeral computation while traditional software becomes persistent storage layer
  - *Caveat: This is a predictive framework without longitudinal validation. Actual SaaS revenue trends, retention metrics, and market consolidation patterns would need tracking to validate.*

### Cloud Infrastructure Economics in AI Era (May 2026)
- **Commodity Market Cost Structure (Thompson, May 2026)**: [Previous content retained]

### Agent Gravity and Platform Economics (Tunguz, May 2026)

**Agent Gravity as Strategic Force**: Platforms compete to retain agent compute workloads on their infrastructure, creating new lock-in dynamics beyond traditional [[data-gravity]].

**Build vs. Buy Implications**:
- **Platform dependency risk**: Building agents on a specific platform (e.g., Microsoft Fabric, Databricks) creates compute-level lock-in in addition to data lock-in
- **Agent-mediated migration**: Agents themselves can facilitate cross-platform migration by:
  - Extracting semantic layer knowledge
  - Orchestrating data movement to alternative warehouses
  - Automating integration with competing BI/analytics tools
- **Defensive platform behavior**: Major platforms actively restricting features that enable agent workload portability (see Databricks-Microsoft case, May 2026)

**Decision Framework Considerations**:
- When evaluating agent platforms, assess not just current costs but switching costs for future migration
- Agent compute requirements are substantial enough that placement decisions affect overall infrastructure economics
- "The person building agents—or the agent itself—decides where to run" introduces new decision-maker dynamics beyond traditional IT procurement
- Multi-platform agent strategies may be necessary to avoid single-platform gravity wells

See [[agentic-workflows-production]] for technical deployment patterns.