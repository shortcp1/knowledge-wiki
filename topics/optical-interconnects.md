---
tags: [ai-adoption-employment, ai-supply-chain, china-ai-strategy, complementarity-effects, dram-pricing, hbm-memory, market-concentration, open-source-llm, optical-interconnects, optical-transceivers, semicap-equipment, semiconductor-bottlenecks, single-point-of-failure, tungsten-supply-chain, us-chip-controls]
---

# Optical Interconnects

Covers the shift from copper to optical for intra- and inter-datacenter bandwidth. Tracks co-packaged optics (CPO), coherent transceivers, silicon photonics, and the companies building this layer (Coherent, II-VI, Marvell, Ayar Labs).

Key questions tracked: When does CPO become cost-competitive at volume? Which hyperscalers are moving first? How does bandwidth scaling affect GPU cluster design?

## Key Claims

### Supply Constraints & Market Dynamics (2025-2026)
- **Component shortage across product lines**: "Complete shortage of EMLs, CW lasers, VCSELs, etc. It's all backordered" as of Q4 2025 (source: Fabricated Knowledge, January 2026). Shortage applies to 800G cycle components; does not yet include higher-performance 1.6T transceivers.
- **Bottleneck winners thesis**: Optics identified as primary bottleneck beneficiary in 2025 AI buildout, alongside [[semiconductor-supply-chain|memory]]. "Bottlenecks became the winners" - when systems are GPU-constrained, bottlenecks shift to "things that feed and connect them" (source: Fabricated Knowledge).
- **Market performance 2025**: Lumentum (LITE) +331%, Fabrinet (FN) +107%, Tower Semiconductor (TSEM) +128%. Optics called "most bullish for 2025" and "definitely was the best prediction" in retrospective analysis.
- **800G to 1.6T transition**: Market currently in "massive 800G cycle" with 1.6T transceivers not yet widely deployed (as of January 2026).

### Market Concentration Risk (2026)
**Single-vendor dominance claim**: "One company you likely never heard of controls a large share of the optical transceivers that make every major AI data center work" (source: Exponential View, July 2026). Company name not disclosed in excerpt; suggests significant supply chain single-point-of-failure risk. Unknown whether this refers to component-level (e.g., laser suppliers) or module-level (transceiver assembly) concentration.

**Implication**: If one unnamed vendor has dominant market share in AI datacenter optical transceivers, supply chain fragility may be higher than publicly understood. Relevant to [[ai-org-design-headcount|organizational planning]] and geopolitical [[semiconductor-supply-chain|supply resilience]].

## Cross-References
- [[semiconductor-supply-chain]]
- [[gpu-architecture-training-infra]]
- [[ai-org-design-headcount]]