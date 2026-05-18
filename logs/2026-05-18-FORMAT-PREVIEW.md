# Link Log — 2026-05-18-FORMAT-PREVIEW

## Integrated (score ≥ 6.0)

### [xAI Colossus 2: Inside the Gigawatt Datacenter](https://semianalysis.com/p/xai-colossus-2-gigawatt-datacenter)
**SemiAnalysis** · score 8.4 · gpu-architecture-training-infra · semiconductor-supply-chain

SemiAnalysis documents xAI's Colossus 2 facility targeting 1GW of compute capacity — an order-of-magnitude jump from typical hyperscaler deployments — with detailed analysis of the power, cooling, and networking infrastructure required. The report reveals that at gigawatt scale, energy sourcing and grid interconnect become the primary constraints, not chip availability or networking topology. This establishes a new class of AI infrastructure where energy politics and geography matter as much as silicon.

### [Huawei Ascend 910C: What the Production Numbers Actually Mean](https://semianalysis.com/p/huawei-ascend-910c-production-ramp)
**SemiAnalysis** · score 7.9 · semiconductor-supply-chain · gpu-architecture-training-infra

SemiAnalysis reports verified production shipment data for Huawei's Ascend 910C, moving it from 'prototype' to 'deployed at scale' status in the Chinese AI market. The chip's performance-per-watt on transformer inference workloads is within striking distance of H100 for specific model architectures, particularly when coupled with Huawei's CANN software stack. This bifurcates the global AI hardware ecosystem in a durable way: Chinese AI development will run on a distinct silicon and software stack, creating long-term tooling and optimization divergence.

### [MoE Expert Routing Failures and What They Mean for Llama 4](https://www.interconnects.ai/p/moe-expert-routing-failures)
**Interconnects** · score 7.8 · model-architecture · post-training-rlhf

Lambert explains how both token routing and expert choice routing in MoE models introduce subtle causality violations that create training-inference mismatch, with claimed connections to Llama 4 and Gemini 2 Pro underperformance. The mechanism is clear: when expert allocation for a token depends on information about later tokens, the model trains on signals unavailable at inference time. The practical implication is that MoE routing is harder to get right than its apparent simplicity suggests, and current frontier models may be leaving significant capability on the table.

### [Latest open artifacts (#21): Open model bonanza! Gemma 4, DeepSeek V4, Kimi K2.6](https://www.interconnects.ai/p/latest-open-artifacts-21-open-model)
**Interconnects** · score 7.3 · model-architecture · lab-dynamics · inference-efficiency

Nathan Lambert catalogues the May 2026 open model release wave, covering Gemma 4, DeepSeek V4 Pro/Flash, Kimi K2.6, MiMo 2.5, and GLM-5.1 with architectural and benchmark comparisons. The key finding is that DeepSeek V4 Flash — the smaller MoE variant — outperforms V4 Pro relative to its size, suggesting diminishing returns at the very largest MoE scales. This matters because it shifts the optimal deployment point toward mid-sized MoE models and weakens the case for pure parameter scaling.

## Skipped (score < 6.0)

| Score | Source | Title | Reason |
|-------|--------|-------|--------|
| 4.0 | OpenAI News | [ChatGPT now recognizes context in sensitive conversations](https://openai.com/index/sensitive-context) | Product feature announcement without technical depth, mechanism explanation, or  |
| 3.5 | OpenAI News | [OpenAI and Dell partner to bring Codex to enterprise environments](https://openai.com/index/dell-codex) | Distribution partnership announcement; no new technical capability or deployment |
| 2.3 | OpenAI News | [OpenAI and Malta partner to bring ChatGPT Plus to all citizens](https://openai.com/index/malta-partnership) | Government partnership press release with no technical content, analysis, or nov |
