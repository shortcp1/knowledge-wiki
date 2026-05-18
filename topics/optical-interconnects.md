---
tags: [hbm-memory, optical-transceivers, dram-pricing, ai-supply-chain, semiconductor-bottlenecks, semicap-equipment, optical-interconnects]
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

## Cross-References
- [[semiconductor-supply-chain]]
- [[gpu-architecture-training-infra]]