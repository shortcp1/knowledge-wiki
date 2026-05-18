# Article Archive

All articles scanned since the wiki started. Updated nightly.

> Search this file in Obsidian to find any article by keyword, source, topic, or tag.


## Wed, 29 Ap

**✓ 8.0** — [Reiner Pope – The math behind how LLMs are trained and served](https://www.dwarkesh.com/p/reiner-pope)  
*Dwarkesh Podcast* · gpu-architecture-training-infra · model-architecture · inference-efficiency
#batch_size_optimization #mixture_of_experts #pipeline_parallelism #chinchilla_scaling
> This is a technical blackboard lecture where Reiner Pope (MatX CEO, former Google TPU architect) explains the mathematical foundations of how frontier LLMs are trained and served across GPU clusters, covering batch size economics, MoE model layouts, pipeline parallelism, and how to deduce infrastructure details from API pricing. The lecture provides concrete equations and frameworks showing how hardware constraints (memory, interconnects, parallelism strategies) drive architectural decisions, training costs, and the economics of inference, including why models may be 100x over-trained beyond Chinchilla-optimal due to RL requirements. This matters because it reveals the fundamental engineering and economic constraints shaping frontier AI development, making lab strategies and pricing structures legible through first-principles analysis.

## Wed, 25 Oc

**✓ 8.0** — [Adversarial Attacks on LLMs](https://lilianweng.github.io/posts/2023-10-25-adv-attack-llm/)  
*Lilian Weng* · model-architecture · evals-production-deployment · ai-governance-risk-compliance
#adversarial_attacks #jailbreak_prompting #red_teaming #model_safety
> This article provides a comprehensive taxonomy and technical analysis of adversarial attacks on large language models, covering token manipulation, gradient-based attacks, jailbreak prompting, and red-teaming approaches. It frames the problem mathematically for both classification and generation tasks, distinguishes white-box from black-box attacks, and discusses mitigation strategies including the saddle point optimization problem inherent in adversarial robustness. This matters because adversarial attacks remain a critical security concern for production LLM deployments, requiring systematic understanding of attack surfaces and defense mechanisms.

## Wed, 25 Fe

**✓ 7.0** — [A Dream of Spring for Open-Weight LLMs: 10 Architectures from Jan-Feb 2026](https://magazine.sebastianraschka.com/p/a-dream-of-spring-for-open-weight)  
*Ahead of AI (Raschka)* · model-architecture · lab-dynamics
#mixture_of_experts #sliding_window_attention #qk_norm #open_weight_models
> This article surveys 10 open-weight LLM releases from January-February 2026, comparing their architectural innovations including mixture-of-experts designs, sliding window attention patterns, and gating mechanisms. The author provides detailed technical comparisons focusing on architectural components like QK-Norm, multi-head latent attention, local vs global attention ratios, and parameter counts across models ranging from 3B to 400B parameters. This matters as a comprehensive reference for understanding the current state of open-weight model architecture evolution and the diverse approaches different labs are taking to improve efficiency and performance.

## Wed, 22 Ap

**✓ 8.0** — [Shopify’s AI Phase Transition: 2026 Usage Explosion, Unlimited Opus-4.6 Token Budget, Tangle, Tangent, SimGym — with Mikhail Parakhin, Shopify CTO](https://www.latent.space/p/shopify)  
*Latent Space Podcast* · ai-engineering-agents · ai-in-product-and-engineering · agentic-workflows-production
#shopify_ai_stack #tangle_ml_workflows #tangent_auto_research #simgym_customer_simulation
> Shopify's CTO Mikhail Parakhin reveals the company's comprehensive AI transformation, including unlimited Opus-4.6 token budgets, universal internal AI tool adoption after a December 2024 model-quality inflection, and three major internal platforms: Tangle (reproducible ML workflows), Tangent (auto-research optimization), and SimGym (customer behavior simulation). The key insight is that code generation is no longer the bottleneck—review, CI/CD, deployment stability, and PR volume have become the critical constraints, requiring new tooling and potentially new metaphors beyond Git/pull requests for machine-speed code generation. This matters because it provides concrete evidence of what enterprise AI adoption looks like at scale in a $200B company, reveals that AI coding can still increase production bugs despite cleaner code, and demonstrates how proprietary behavioral data creates defensible moats in customer simulation.

**✗ 4.7** — [Decoupled DiLoCo: A new frontier for resilient, distributed AI training](https://deepmind.google/blog/decoupled-diloco/)  
*Google DeepMind* · gpu-architecture-training-infra
#distributed_training #diloco #training_resilience
> The article appears to announce Decoupled DiLoCo, a distributed training approach designed for resilience and scale in AI model training. However, the provided text contains only navigation elements and page structure from Google DeepMind's website without actual article content describing the technical mechanism or evidence. Without the substantive content, it's impossible to assess the specific contributions, performance claims, or implementation details of the training methodology.

## Wed, 20 Au

**✓ 8.7** — [H100 vs GB200 NVL72 Training Benchmarks – Power, TCO, and Reliability Analysis, Software Improvement Over Time](https://semianalysis.com/2025/08/20/h100-vs-gb200-nvl72-training-benchmarks/)  
*SemiAnalysis* · gpu-architecture-training-infra · semiconductor-supply-chain
#h100_benchmark #gb200_nvl72 #model_flops_utilization #training_tco
> This article presents detailed benchmarking data comparing H100 and GB200 NVL72 GPUs for frontier model training, measuring model flops utilization (MFU), total cost of ownership (TCO), energy per token, and reliability across clusters of up to 2,048 GPUs. The analysis reveals that GB200 NVL72's performance advantages are currently undermined by significant reliability issues and immature software, with no large-scale training runs yet completed successfully, while H100/H200 and Google TPUs remain the only proven options for frontier-scale training. The findings matter because they challenge Nvidia's marketing narratives and provide operators with realistic expectations for hardware selection, showing that new architectures require substantial ecosystem maturation time before delivering on theoretical performance promises.

## Wed, 18 Ma

**✗ 5.0** — [Partnering with Edra: Context for Agents at Scale](https://sequoiacap.com/article/partnering-with-edra-context-for-agents-at-scale/)  
*Sequoia* · agentic-workflows-production · rag-over-proprietary-content · ai-in-customer-success-support
#knowledge_extraction #agentic_context #forward_deployed_engineering #enterprise_tribal_knowledge
> Edra is building a system that automatically extracts enterprise tribal knowledge from existing data streams (tickets, emails, logs) to create dynamic context for AI agents, rather than relying on manual documentation. The company's approach creates a transparent, editable knowledge base that learns from usage and enables agent automation in IT service management and technical support. Founded by former Palantir executives who created the Forward Deployed AI Engineer role, Edra represents a shift from manual enterprise AI configuration to automated knowledge extraction.

## Wed, 17 De

**✗ 5.0** — [Lessons from History: The Great Railroad Buildout](https://www.fabricatedknowledge.com/p/lessons-from-history-the-great-railroad)  
*Fabricated Knowledge* · funding-and-market-structure
#capital_cycles #infrastructure_financing #overbuilding #historical_parallels
> The article draws parallels between the 19th-century railroad capital cycle and today's AI infrastructure buildout, examining how railroads were financed through land grants, overbought during boom cycles, and eventually consolidated. It details the Pacific Railroad Act of 1862, the land grant financing mechanism where railroads received alternating sections of land in corridors to sell for capital, and how the Civil War demonstrated railroad value while post-war expansion accelerated from 1,000 to 7,000 miles per year. The historical analogy suggests today's AI infrastructure may follow a similar pattern of speculative overbuilding followed by consolidation, though the article appears incomplete and doesn't fully develop the contemporary implications.

**✗ 3.7** — [The best growth tactics of 2025](https://kylepoyar.substack.com/p/the-best-growth-tactics-of-2025)  
*Growth Unhinged (Kyle Poyar)* · ai-in-sales-gtm · ai-in-marketing-content

## Wed, 15 Ap

**✗ 4.0** — [Engels' Pause and the Permanent Underclass](https://www.fabricatedknowledge.com/p/mythos-and-engels-pause)  
*Fabricated Knowledge* · lab-dynamics · regulatory-policy

**✓ 7.0** — [My bets on open models, mid-2026](https://www.interconnects.ai/p/my-bets-on-open-models-mid-2026)  
*Interconnects (Nathan Lambert)* · model-architecture · lab-dynamics · funding-and-market-structure
#open_models #capability_gap #model_distillation #benchmark_performance
> Lambert argues that open models will not fully catch up to closed models across all dimensions, with the capability gap being driven by economic staying power, funding dynamics (especially for Chinese labs), and hard-to-measure qualities like robustness that favor closed models. He presents evidence that while open models excel at benchmark performance through fast-following and distillation, closed models maintain advantages in real-world robustness and RL-driven agent capabilities tied to actual user workflows. This matters because it suggests a bifurcated market where open models serve certain use cases but closed models dominate knowledge worker assistance and enterprise deployment requiring reliability.

**✗ 4.0** — [Gemini 3.1 Flash TTS: the next generation of expressive AI speech](https://deepmind.google/blog/gemini-3-1-flash-tts-the-next-generation-of-expressive-ai-speech/)  
*Google DeepMind* · multimodal-models
#text_to_speech #audio_generation #gemini_models #expressive_synthesis
> Google DeepMind announces Gemini 3.1 Flash TTS, a new text-to-speech model that features granular audio tags for precise control over AI-generated speech expressiveness. The key technical mechanism is the use of detailed audio tags that allow users to direct specific characteristics of the synthesized speech. This represents an incremental improvement in TTS control and expressiveness but the article provides minimal technical detail or evidence about the architecture, performance benchmarks, or real-world applications.

**✗ 4.0** — [Partnering with Auctor](https://sequoiacap.com/article/partnering-with-auctor/)  
*Sequoia* · ai-in-professional-services · ai-in-operations · build-vs-buy-enterprise-ai
#software_implementation #professional_services_automation #enterprise_deployment #consulting_automation
> Sequoia announces a Series A investment in Auctor, which automates enterprise software implementation using AI, targeting the $500B+ market of 9M consultants who implement platforms like Salesforce and ServiceNow. The article argues that implementation consultants are limited by human context windows while LLMs can track thousands of platform updates and dependencies simultaneously, reducing weeks of scoping work to a single session. This matters as a potential disruption to one of technology's largest and least-automated service markets, though the article provides no technical details or customer evidence beyond general claims.

## Wed, 13 Ma

**✗ 2.3** — [Reel Friends: Building Social Discovery that Scales to Billions](https://engineering.fb.com/2026/05/13/ml-applications/reel-friends-building-social-discovery-that-scales-to-billions/)  
*Meta AI / FB Engineering* · 
#social_recommendation #friend_discovery #reels #meta_engineering
> This is a podcast announcement about Meta's Friend Bubbles feature for Reels, which shows users which reels their friends have watched and reacted to. The episode discusses the machine learning model, platform differences between iOS and Android, and engineering challenges in scaling the feature. It provides no substantive technical details or insights, serving purely as promotional content for the podcast.

**✗ 5.7** — [[AINews] The End of Finetuning](https://www.latent.space/p/ainews-the-end-of-finetuning)  
*Latent Space* · rag-vs-finetuning-vs-wiki · model-architecture · inference-efficiency
#finetuning_deprecation #prompt_engineering #rlft #open_models
> The article reports on OpenAI's deprecation of finetuning APIs and argues this signals a broader industry shift away from finetuning for most AI engineering use cases, though top-tier applications continue to use it heavily. The key evidence includes OpenAI's API shutdown, contrasting behavior between the "bottom 99%" moving to long prompts and the "top 1%" (Cursor, Cognition) increasing finetuning usage, and historical predictions from Jeremy Howard in 2023. This matters because it reveals a bifurcation in AI engineering practices where the modal approach is diverging from cutting-edge techniques, with implications for compute allocation, product strategy, and the build-vs-buy decision in enterprise AI.

**✗ 3.0** — [The 6 Messages That Actually Matter](https://www.tomtunguz.com/the-disappearance-of-email/)  
*Tomasz Tunguz* · ai-in-product-and-engineering · ai-native-product-design

## Wed, 13 Au

**✓ 8.0** — [GPT-5 Set the Stage for Ad Monetization and the SuperApp](https://semianalysis.com/2025/08/13/gpt-5-ad-monetization-and-the-superapp/)  
*SemiAnalysis* · ai-pricing-packaging-saas · ai-native-product-design · model-architecture
#router_architecture #ad_monetization #free_user_monetization #chain_of_thought_routing
> The article argues that GPT-5's real innovation is not model capabilities but a router system designed to monetize ChatGPT's 700M+ free users through ad-based revenue, positioning ChatGPT as a SuperApp. The key evidence includes the router's ability to dynamically allocate queries between model tiers based on complexity and commercial value, plus OpenAI's hiring of Facebook monetization expert Fidji Simo as CEO of Applications. This matters because it represents a strategic shift from subscription-only to ad-supported monetization, directly challenging Google's search ad business by capturing high-intent purchasing queries.

## Wed, 10 Se

**✓ 8.7** — [Another Giant Leap: The Rubin CPX Specialized Accelerator & Rack](https://semianalysis.com/2025/09/10/another-giant-leap-the-rubin-cpx-specialized-accelerator-rack/)  
*SemiAnalysis* · gpu-architecture-training-infra · inference-efficiency · semiconductor-supply-chain

## Wed, 10 De

**✗ 4.7** — [The AI churn wave?](https://kylepoyar.substack.com/p/the-ai-churn-wave)  
*Growth Unhinged (Kyle Poyar)* · ai-in-product-and-engineering · build-vs-buy-enterprise-ai · ai-b2b-saas
#b2b_gtm #newsletter #growth
> The article appears to be a newsletter intro or header without substantive content, referencing a podcast and GTM report. No actual analysis, data, or arguments are presented in the provided text. This is merely a newsletter masthead with promotional links.

## Wed, 07 Ja

**✓ 6.3** — [2026 AI & Semiconductor Outlook](https://www.fabricatedknowledge.com/p/2026-ai-and-semiconductor-outlook)  
*Fabricated Knowledge* · semiconductor-supply-chain · gpu-architecture-training-infra · optical-interconnects
#hbm_memory #optical_transceivers #dram_pricing #ai_supply_chain
> The article reviews 2025 semiconductor performance and argues that AI spending shifted down the stack from GPUs to memory and optics, creating bottlenecks that made these components the year's winners. It provides specific stock performance data (optics companies up 100-331%, memory up 228%) and DRAM pricing charts showing historic price increases as evidence of supply constraints. This matters because it demonstrates how AI infrastructure buildout creates cascading effects through the supply chain, with bottleneck identification being key to investment and procurement strategy.

## Wed, 06 Ma

**✗ 3.0** — [AlphaEvolve: How our Gemini-powered coding agent is scaling impact across fields](https://deepmind.google/blog/alphaevolve-impact/)  
*Google DeepMind* · ai-engineering-agents

## Wed, 03 Se

**✓ 8.7** — [Amazon’s AI Resurgence: AWS & Anthropic’s Multi-Gigawatt Trainium Expansion](https://semianalysis.com/2025/09/03/amazons-ai-resurgence-aws-anthropics-multi-gigawatt-trainium-expansion/)  
*SemiAnalysis* · gpu-architecture-training-infra · semiconductor-supply-chain · lab-dynamics
#trainium2 #anthropic #aws_infrastructure #custom_silicon
> The article argues AWS is experiencing an AI resurgence through a multi-gigawatt Anthropic partnership centered on Trainium2 custom silicon, reversing earlier momentum losses to Azure and Google Cloud. Key evidence includes proprietary satellite-based datacenter tracking showing over a gigawatt of AWS capacity under construction, Anthropic's 5x revenue growth to $5B annualized, and Trainium2's memory bandwidth advantages for reinforcement learning workloads. This matters because it positions Anthropic alongside Google DeepMind as the only AI labs with tight hardware-software co-design, potentially reshaping competitive dynamics in both cloud infrastructure and frontier model development.

## Tue, 31 Ma

**✗ 4.7** — [From Hierarchy to Intelligence](https://sequoiacap.com/article/from-hierarchy-to-intelligence/)  
*Sequoia* · ai-org-design-headcount · ai-in-operations
#organizational_hierarchy #span_of_control #ai_organizational_design #enterprise_structure
> The article traces organizational hierarchy from Roman military structures through Prussian staff systems and American railroads to argue that AI enables a fundamental rethinking of corporate organization design beyond traditional span-of-control constraints. It positions Block (Jack Dorsey's company) as an example of using AI to flatten hierarchies and increase organizational speed rather than merely enhancing individual productivity. The historical context suggests AI could be as transformative to organizational structure as the telegraph or railroad were in their eras.

## Tue, 21 Ap

**✗ 2.7** — [Partnering with industry leaders to accelerate AI transformation](https://deepmind.google/blog/partnering-with-industry-leaders-to-accelerate-ai-transformation/)  
*Google DeepMind* · build-vs-buy-enterprise-ai · ai-b2b-saas
#enterprise_adoption #consulting_partnerships #google_deepmind
> Google DeepMind announces partnerships with global consultancies to help enterprises adopt AI technologies. The article provides no specific details about which consultancies, what services, deployment models, or case studies. This is a brief announcement without substance that fails to offer actionable insights or evidence about how these partnerships accelerate AI transformation.

## Tue, 16 Se

**✓ 8.0** — [xAI’s Colossus 2 – First Gigawatt Datacenter In The World, Unique RL Methodology, Capital Raise](https://semianalysis.com/2025/09/16/xais-colossus-2-first-gigawatt-datacenter/)  
*SemiAnalysis* · gpu-architecture-training-infra · lab-dynamics · funding-and-market-structure

## Tue, 12 Ma

**✗ 3.0** — [Migrating Data Ingestion Systems at Meta Scale](https://engineering.fb.com/2026/05/12/data-infrastructure/migrating-data-ingestion-systems-at-meta-scale/)  
*Meta AI / FB Engineering* · 
#data_ingestion #system_migration #mysql #data_warehouse
> Meta describes migrating their petabyte-scale data ingestion system from customer-owned pipelines to a self-managed warehouse service, processing social graph data from MySQL to power analytics and ML training. The migration used a phased approach with shadow testing, validation criteria (data quality, latency, resource utilization), and rollout controls to transition thousands of jobs. This is a large-scale infrastructure migration case study focused on data engineering practices rather than AI-specific techniques.

**✓ 7.7** — [How open model ecosystems compound](https://www.interconnects.ai/p/how-open-model-ecosystems-compound)  
*Interconnects (Nathan Lambert)* · model-architecture · lab-dynamics · funding-and-market-structure

**✓ 8.0** — [[AINews] Thinking Machines' Native Interaction Models - TML-Interaction-Small 276B-A12B - advances SOTA Realtime Voice and kills standard VAD](https://www.latent.space/p/ainews-thinking-machines-native-interaction)  
*Latent Space* · model-architecture · multimodal-models · inference-efficiency
#realtime_voice #mixture_of_experts #full_duplex_interaction #encoder_free_early_fusion
> Thinking Machines released TML-Interaction-Small, a 276B parameter MoE model with 12B active parameters that treats real-time multimodal interaction as a first-class capability rather than layering speech/vision onto turn-based LLMs. The model uses encoder-free early fusion to process audio and images in under 200ms 'microturns', introduces new benchmarks for time awareness and proactive visual responses, and demonstrates full-duplex continuous interaction that handles interruptions, simultaneous speech, and background tool use without explicit mode boundaries. This represents a fundamental architectural shift from retrofitting conversational capabilities onto text models to training interaction as the native paradigm, potentially obsoleting voice activity detection and turn-taking systems.

**✗ 4.7** — [2026 Theory GTM Survey](https://www.tomtunguz.com/2026-gtm-survey/)  
*Tomasz Tunguz* · ai-in-sales-gtm · ai-org-design-headcount · build-vs-buy-enterprise-ai
#gtm_survey #augmented_sales_teams #ai_sdr #buyer_side_ai
> This article announces a 2026 GTM survey investigating five hypotheses about AI's impact on sales and marketing teams, including whether augmented human-AI teams outperform autonomous AI or unaugmented humans. The survey focuses on measuring conversion rates, productivity gains, headcount changes, and the impact of buyer-side AI adoption on sales cycles. The research aims to determine whether AI efficiency gains manifest as headcount reduction rather than revenue growth, and whether founder expectations have recalibrated after initial over-optimism.

## Tue, 05 Ma

**✗ 4.0** — [🔬Doing Vibe Physics — Alex Lupsasca, OpenAI](https://www.latent.space/p/lupsasca)  
*Latent Space Podcast* · model-architecture

## Thu, 30 Ap

**✗ 5.3** — [Standard Intelligence: Training General Intelligence in Pixel Space](https://sequoiacap.com/article/standard-intelligence-training-general-intelligence-in-pixel-space/)  
*Sequoia* · model-architecture · ai-engineering-agents · agentic-workflows-production

**✗ 2.7** — [Enabling a new model for healthcare with AI co-clinician](https://deepmind.google/blog/ai-co-clinician/)  
*Google DeepMind* · 

## Thu, 28 No

**✓ 8.7** — [Reward Hacking in Reinforcement Learning](https://lilianweng.github.io/posts/2024-11-28-reward-hacking/)  
*Lilian Weng* · post-training-rlhf · model-architecture · evals-production-deployment

## Thu, 23 Ap

**✗ 5.7** — [AIE Europe Debrief + Agent Labs Thesis: Unsupervised Learning x Latent Space Crossover Special (2026)](https://www.latent.space/p/unsupervised-learning-2026)  
*Latent Space Podcast* · model-architecture · inference-efficiency · ai-engineering-agents
#ai_coding_assistants #domain_specific_models #agent_labs #model_distillation
> This podcast crossover discusses the state of AI engineering in 2026, covering infrastructure stabilization, the vertical vs horizontal startup debate, and the 'agent lab' playbook of starting with frontier models before training domain-specific ones. The conversation examines how coding products have become sticky despite model volatility, why domain-specific model training is becoming viable, and how companies like Cursor justify in-house models through search and specialization. It argues that AI coding represents a template for how other vertical AI markets will develop, with foundation labs colliding with application companies while leaving room for workflow-focused startups.

## Thu, 14 Ma

**✓ 7.0** — [AI-Native Healthcare: 100M Doctor Visits, 10–20 Hours Saved, Prior Auth in Minutes — Janie Lee & Chai Asawa, Abridge](https://www.latent.space/p/abridge)  
*Latent Space Podcast* · ai-in-product-and-engineering · agentic-workflows-production · evals-production-deployment

**✗ 5.3** — [[AINews] Codex Rises, Claude Meters Programmatic Usage](https://www.latent.space/p/ainews-codex-rises-claude-meters)  
*Latent Space* · ai-pricing-packaging-saas · ai-engineering-agents · agentic-workflows-production
#claude_api_pricing #codex_agent #coding_agents #api_metering
> The article reports on shifting competitive dynamics between OpenAI's Codex and Anthropic's Claude, particularly around pricing changes where Claude now meters programmatic API usage by giving subscription holders API credits equal to their subscription cost. This represents a strategic shift where Anthropic is ending its historical pricing subsidy for third-party harnesses and favoring its own Claude Code platform, while OpenAI's Codex gains developer sentiment through more generous limits. The pricing changes matter as they reflect both companies' attempts to optimize monetization while competing for developer mindshare in the coding agent market.

**✗ 4.7** — [What Would AI Email Cost?](https://www.tomtunguz.com/cost-of-ai-email/)  
*Tomasz Tunguz* · inference-efficiency · ai-pricing-packaging-saas · build-vs-buy-enterprise-ai

## Thu, 07 Ma

**✓ 7.3** — [Notes from inside China's AI labs](https://www.interconnects.ai/p/notes-from-inside-chinas-ai-labs)  
*Interconnects (Nathan Lambert)* · lab-dynamics · model-architecture · ai-org-design-headcount

## Thu, 01 Ma

**✓ 9.0** — [Why We Think](https://lilianweng.github.io/posts/2025-05-01-thinking/)  
*Lilian Weng* · model-architecture · inference-time-compute · inference-efficiency

## Sun, 22 Ma

**✓ 6.7** — [A Visual Guide to Attention Variants in Modern LLMs](https://magazine.sebastianraschka.com/p/visual-attention-variants)  
*Ahead of AI (Raschka)* · model-architecture · inference-efficiency
#multi_head_attention #grouped_query_attention #sparse_attention #attention_mechanisms
> This article provides a visual guide cataloging modern attention mechanism variants used in large language models, from multi-head attention (MHA) to grouped-query attention (GQA), multi-latent attention (MLA), and sparse attention patterns. The author presents 45 LLM architectures with visual model cards showing how each architecture implements attention, drawing from examples like GPT-2, OLMo, and anticipated DeepSeek V4. This matters as a comprehensive reference resource for understanding the architectural choices that impact inference efficiency and model performance across contemporary LLMs.

## Sun, 17 Ma

**✗ 5.0** — [Why we’re at the beginning of the AI hardware boom | Caitlin Kalinowski (ex–OpenAI, Meta, Apple)](https://www.lennysnewsletter.com/p/why-were-at-the-beginning-of-the)  
*Lenny's Newsletter* · semiconductor-supply-chain · ai-in-product-and-engineering

## Sun, 07 Ju

**✓ 8.0** — [Extrinsic Hallucinations in LLMs](https://lilianweng.github.io/posts/2024-07-07-hallucination/)  
*Lilian Weng* · model-architecture · rag-vs-finetuning-vs-wiki · evals-production-deployment

## Sat, 24 Ja

**✓ 7.3** — [Categories of Inference-Time Scaling for Improved LLM Reasoning](https://magazine.sebastianraschka.com/p/categories-of-inference-time-scaling)  
*Ahead of AI (Raschka)* · inference-time-compute · model-architecture · inference-efficiency
#inference_time_scaling #chain_of_thought #self_consistency #best_of_n_sampling
> This article categorizes inference-time scaling techniques for LLMs, covering methods like chain-of-thought prompting, self-consistency, best-of-N ranking, rejection sampling, self-refinement, and search over solution paths. The author provides practical experimental results showing accuracy improvements from ~15% to ~52% through these techniques, drawing from work developing a book chapter with thousands of experimental runs. The piece synthesizes recent academic literature and proprietary approaches into a taxonomy of inference-scaling methods that trade compute for improved reasoning accuracy.

## Sat, 18 Ap

**✗ 3.0** — [My Workflow for Understanding LLM Architectures](https://magazine.sebastianraschka.com/p/workflow-for-understanding-llms)  
*Ahead of AI (Raschka)* · model-architecture

## Sat, 16 Ma

**✗ 3.0** — [The mistake of conflating intelligence and power](https://www.dwarkesh.com/p/the-mistake-of-conflating-intelligence)  
*Dwarkesh Podcast* · ai-org-design-headcount

**✓ 7.3** — [Notes on pretraining parallelisms and failed training runs.](https://www.dwarkesh.com/p/notes-on-pretraining-parallelisms)  
*Dwarkesh Podcast* · gpu-architecture-training-infra · model-architecture

**✓ 8.0** — [RLVR might be disproportionately bad at science](https://www.dwarkesh.com/p/rlvr-might-be-disproportionately)  
*Dwarkesh Podcast* · model-architecture · post-training-rlhf · inference-time-compute

**✓ 7.3** — [Latest open artifacts (#21): Open model bonanza! Gemma 4, DeepSeek V4, Kimi K2.6, MiMo 2.5, GLM-5.1 & others. On CAISI's V4 assessment.](https://www.interconnects.ai/p/latest-open-artifacts-21-open-model)  
*Interconnects (Nathan Lambert)* · model-architecture · evals-production-deployment · lab-dynamics

**✓ 8.0** — [Recent Developments in LLM Architectures: KV Sharing, mHC, and Compressed Attention](https://magazine.sebastianraschka.com/p/recent-developments-in-llm-architectures)  
*Ahead of AI (Raschka)* · model-architecture · inference-efficiency · gpu-architecture-training-infra

**✗ 4.7** — [[AINews] Cerebras' $60B IPO: Slowly, then All at Once](https://www.latent.space/p/ainews-cerebras-60b-ipo-slowly-then)  
*Latent Space* · gpu-architecture-training-infra · inference-efficiency · funding-and-market-structure

**✗ 2.3** — [OpenAI and Malta partner to bring ChatGPT Plus to all citizens](https://openai.com/index/malta-chatgpt-plus-partnership)  
*OpenAI News* · regulatory-policy · ai-governance-risk-compliance

## Sat, 04 Ap

**✓ 7.3** — [Components of A Coding Agent](https://magazine.sebastianraschka.com/p/components-of-a-coding-agent)  
*Ahead of AI (Raschka)* · ai-engineering-agents · agentic-workflows-production · model-architecture

## Mon, 27 Ap

**✓ 7.0** — [Physical AI that Moves the World — Qasar Younis & Peter Ludwig, Applied Intuition](https://www.latent.space/p/appliedintuition)  
*Latent Space Podcast* · inference-efficiency · model-architecture · evals-production-deployment
#physical_ai #autonomy #safety_critical_systems #edge_deployment
> Applied Intuition founders explain how they built a $15B physical AI company focused on deploying AI onto safety-critical machines (vehicles, trucks, construction equipment, defense systems) rather than screen-based applications. They argue the real bottleneck is no longer model intelligence but deployment constraints—onboard models need millisecond latency, low power, and extreme reliability, requiring real operating systems, simulation infrastructure, and statistical safety validation beyond binary pass/fail tests. This matters because physical AI deployment requires fundamentally different architectures, tooling, and validation approaches than LLMs, creating a platform opportunity comparable to Android for all moving machines.

**✗ 4.3** — [Partnering with Ineffable Intelligence: A Superlearner for the Era of Experience](https://sequoiacap.com/article/partnering-with-ineffable-intelligence-a-superlearner-for-the-era-of-experience/)  
*Sequoia* · model-architecture · lab-dynamics · funding-and-market-structure

**✗ 2.0** — [Announcing our partnership with the Republic of Korea](https://deepmind.google/blog/announcing-our-partnership-with-the-republic-of-korea/)  
*Google DeepMind* · regulatory-policy · lab-dynamics

## Mon, 24 No

**✗ 1.7** — [Market Volatility: Some Thoughts](https://www.fabricatedknowledge.com/p/market-volatility-some-thoughts)  
*Fabricated Knowledge* · 
#market_volatility #market_correction #financial_markets
> The article appears to discuss market volatility and market corrections, but the full content is paywalled and not accessible. Based on the visible title and subtitle, it suggests a market correction is occurring and may be more technical in nature than anticipated. Without access to the actual analysis, evidence, or specific claims about semiconductor markets or AI infrastructure, the relevance and depth cannot be properly assessed.

## Mon, 20 Ap

**✓ 7.3** — [Reading today's open-closed performance gap](https://www.interconnects.ai/p/reading-todays-open-closed-performance)  
*Interconnects (Nathan Lambert)* · model-architecture · evals-production-deployment · lab-dynamics
#open_vs_closed_models #benchmark_evolution #rlvr #post_training
> The article argues that the open vs. closed model performance gap is more nuanced than a single benchmark number suggests, with the focus of model capabilities shifting every 12-18 months from chat/math to coding to specialized knowledge work. It provides evidence through the evolution of training paradigms (instruction tuning to RLHF to RLVR) and the observation that benchmarks like Artificial Analysis Intelligence Index mask which specific capabilities are being optimized. This matters because open models will increasingly struggle to catch up in newer specialized domains that require expensive, proprietary training data and evaluation environments, creating data moats similar to semiconductor fab dynamics.

**✓ 7.7** — [Import AI 454: Automating alignment research; safety study of a Chinese model; HiFloat4](https://importai.substack.com/p/import-ai-454-automating-alignment)  
*Import AI (Jack Clark)* · gpu-architecture-training-infra · inference-efficiency · model-architecture
#low_precision_training #hifloat4 #ascend_npu #export_controls
> The article reports on three developments: Huawei's HiFloat4 4-bit precision format outperforming Western MXFP4 on Ascend chips with ~1% vs ~1.5% relative loss, Anthropic's demonstration of automated AI safety research where Claude agents outperform human researchers on weak-to-strong supervision tasks, and a safety study of a Chinese model. The key evidence includes systematic benchmarking across OpenPangu-1B, Llama3-8B, and Qwen3-MoE-30B models showing HiFloat4's superior performance, and successful automation of research workflows from hypothesis generation through experimentation. This matters because it shows how export controls may be driving Chinese innovation in training efficiency and provides early evidence that AI research itself can be automated, potentially accelerating both capability development and safety research.

## Mon, 18 Ma

**✓ 7.3** — [🎙️ How I AI: HTML is the new Markdown: How Anthropic engineers are building with Claude Code](https://www.lennysnewsletter.com/p/how-i-ai-html-is-the-new-markdown)  
*Lenny's Newsletter* · ai-engineering-agents · agentic-workflows-production · prompt-architecture

**✗ 5.3** — [The Next War Is Already Here. The West Isn't Ready. — Yaroslav Azhnyuk, The Fourth Law & Guest Host Noah Smith, Noahpinion](https://www.latent.space/p/the-fourth-law)  
*Latent Space Podcast* · ai-in-operations · regulatory-policy

**✗ 5.7** — [Import AI 457: AI stuxnet; cursed Muon optimizer; and positive alignment](https://importai.substack.com/p/import-ai-457-ai-stuxnet-cursed-muon)  
*Import AI (Jack Clark)* · 

**✓ 7.0** — [HTML is the new Markdown: How Anthropic engineers are building with Claude Code | Thariq Shihipar](https://www.lennysnewsletter.com/p/html-is-the-new-markdown-how-anthropic)  
*Lenny's Newsletter* · ai-engineering-agents · prompt-architecture · ai-in-product-and-engineering

**✗ 4.0** — [OpenAI and Dell partner to bring Codex to hybrid and on-premise enterprise environments](https://openai.com/index/dell-codex-enterprise-partnership)  
*OpenAI News* · build-vs-buy-enterprise-ai · ai-in-product-and-engineering · ai-governance-risk-compliance

**✗ 4.3** — [Observations on Writing with AI](https://www.tomtunguz.com/observations-on-writing-with-ai/)  
*Tomasz Tunguz* · ai-in-marketing-content · prompt-architecture
#ai_writing_tools #model_voice #content_authenticity #multi_model_synthesis
> The author argues that AI writing tools fail to produce authentic content because each model (Gemini, Claude, OpenAI) has its own distinct voice, and using multiple models together creates inconsistent tone rather than improved quality. Through personal experiments fine-tuning models and testing multi-model editorial councils, the author finds that AI-generated content lacks the imperfections (analogies, punctuation quirks) that make writing authentic and memorable. The conclusion is that as AI makes perfect content ubiquitous, human imperfections become the marker of authenticity and quality in writing.

## Mon, 16 Fe

**✗ 4.7** — [Another Conversation with Val Bercovici Memory Markets](https://www.fabricatedknowledge.com/p/another-conversation-with-val-bercovici)  
*Fabricated Knowledge* · inference-efficiency · gpu-architecture-training-infra

## Mon, 13 Ap

**✗ 5.7** — [Import AI 453: Breaking AI agents; MirrorCode; and ten views on gradual disempowerment](https://importai.substack.com/p/import-ai-453-breaking-ai-agents)  
*Import AI (Jack Clark)* · ai-engineering-agents · evals-production-deployment · agentic-workflows-production
#autonomous_coding #reverse_engineering #inference_scaling #long_horizon_tasks
> The article reports on MirrorCode, a benchmark showing AI systems can autonomously reverse-engineer and reimplement complex software with thousands of lines of code, with Claude Opus 4.6 successfully reimplementing a 16,000-line bioinformatics toolkit. The key evidence is that models can achieve tasks estimated to take human engineers 2-17 weeks, with performance scaling with inference compute. This matters because it demonstrates AI systems have already reached sophistication levels comparable to full-time software engineers on certain long-horizon coding tasks, suggesting AI capabilities may be advancing faster than widely understood.

## Mon, 12 Ja

**✗ 1.0** — [Update: I've moved from Substack to beehiiv](https://kylepoyar.substack.com/p/update-ive-moved-from-substack-to)  
*Growth Unhinged (Kyle Poyar)* · 

## Mon, 11 Ma

**✗ 3.0** — [Labyrinth 1.1: Making End-to-End Encrypted Backups Even More Reliable](https://engineering.fb.com/2026/05/11/security/labyrinth-1-1-end-to-end-encrypted-e2ee-backups-more-reliable/)  
*Meta AI / FB Engineering* · 
#end_to_end_encryption #encrypted_backups #message_storage #cryptographic_protocol
> Meta announces Labyrinth 1.1, an updated end-to-end encrypted storage protocol for Messenger that improves backup reliability by allowing messages to be stored in encrypted backups immediately rather than waiting for devices to come online. The system uses a mechanism where senders directly place message encryption keys into recipients' encrypted backups, ensuring messages survive device loss or long offline periods. This represents an incremental improvement to Meta's existing E2EE messaging infrastructure deployed at scale.

**✗ 0.0** — [Import AI 456: RSI and economic growth; radical optionality for AI regulation; and a neural computer](https://importai.substack.com/p/import-ai-456-rsi-and-economic-growth)  
*Import AI (Jack Clark)* · 

**✓ 7.3** — [Localmaxxing](https://www.tomtunguz.com/localmaxxing/)  
*Tomasz Tunguz* · inference-efficiency · agentic-workflows-production · ai-in-product-and-engineering
#local_inference #latency_optimization #edge_compute #agentic_tasks
> The author reports that after five weeks of testing, approximately 50% of daily work tasks (1,400 total) can be successfully handled by local 35B parameter models instead of cloud-based trillion-parameter models, with scheduling, email, summarization, and admin tasks being most suitable. Through head-to-head benchmarking, local models (Qwen 3.6 35B) deliver significantly lower latency than cloud models (Claude Opus 4.5) despite being 20% lower on reasoning benchmarks, with both completing routine agent tasks correctly. This matters because latency—not capability, cost, or privacy—is the dominant factor driving "localmaxxing," the shift of inference workloads from cloud to edge devices, which will accelerate as local models continue closing the gap with frontier models.

## Mon, 08 Se

**✓ 7.7** — [Huawei Ascend Production Ramp: Die Banks, TSMC Continued Production, HBM is The Bottleneck](https://semianalysis.com/2025/09/08/huawei-ascend-production-ramp/)  
*SemiAnalysis* · semiconductor-supply-chain · gpu-architecture-training-infra · regulatory-policy

## Mon, 06 Ap

**✓ 7.3** — [Import AI 452: Scaling laws for cyberwar; rising tides of AI automation; and a puzzle over gDP forecasting](https://importai.substack.com/p/import-ai-452-scaling-laws-for-cyberwar)  
*Import AI (Jack Clark)* · model-architecture · evals-production-deployment · ai-governance-risk-compliance
#scaling_laws #cybersecurity #offensive_capabilities #dual_use
> The article reports on two key findings: (1) Lyptus Research demonstrates a scaling law for AI-enabled cyberattacks, showing frontier models can now complete 50% of offensive security tasks that take human experts 3.2 hours, with capability doubling every 5.7-9.8 months, and (2) a field experiment with 515 startups shows that those taught to integrate AI across business functions discovered 44% more use cases and generated 1.9x higher revenue. The evidence includes systematic benchmarking across seven cybersecurity datasets spanning models from GPT-2 to GPT-5.3 Codex, and a randomized controlled trial with startup accelerator participants. This matters because it quantifies both the dual-use risk trajectory of increasingly capable AI systems and provides empirical evidence for AI's measurable business impact when strategically adopted.

## Mon, 05 Fe

**✓ 7.0** — [Thinking about High-Quality Human Data](https://lilianweng.github.io/posts/2024-02-05-human-data-quality/)  
*Lilian Weng* · post-training-rlhf · evals-production-deployment · ai-governance-risk-compliance
#human_annotation #data_quality #rlhf_labeling #rater_agreement
> This article examines how to ensure high-quality human-generated training data for machine learning models, particularly for tasks like RLHF and classification labeling. It explores both the crowdsourcing approach (wisdom of the crowd, rater agreement metrics, handling disagreement) and technical methods to assess data quality (influence functions, prediction changes during training, noisy cross-validation). The work matters because data quality fundamentally determines model performance, yet is often undervalued compared to model architecture work.

## Mon, 04 Ma

**✓ 7.0** — [The distillation panic](https://www.interconnects.ai/p/the-distillation-panic)  
*Interconnects (Nathan Lambert)* · model-architecture · post-training-rlhf · regulatory-policy
#distillation #model_compression #synthetic_data #api_abuse
> The article argues that referring to unauthorized model training as 'distillation attacks' conflates legitimate distillation techniques (widely used for post-training and model compression) with illicit API abuse, potentially stigmatizing a core AI development method. Lambert explains that distillation encompasses multiple legitimate uses including data generation for post-training, skill transfer, and creating smaller specialized models, while actual problematic behavior involves jailbreaking or API manipulation. This framing matters because imprecise terminology could lead to policy overreach that restricts beneficial research and development techniques used throughout the industry.

**✓ 7.3** — [Import AI 455: AI systems are about to start building themselves.](https://importai.substack.com/p/import-ai-455-automating-ai-research)  
*Import AI (Jack Clark)* · model-architecture · ai-engineering-agents · lab-dynamics

## Fri, 16 Ja

**✓ 7.0** — [The Death of Software 2.0 (A Better Analogy!)](https://www.fabricatedknowledge.com/p/the-death-of-software-20-a-better)  
*Fabricated Knowledge* · ai-engineering-agents · agentic-workflows-production · build-vs-buy-enterprise-ai

## Fri, 15 Ma

**✓ 8.0** — [Eric Jang – Building AlphaGo from scratch](https://www.dwarkesh.com/p/eric-jang)  
*Dwarkesh Podcast* · model-architecture · post-training-rlhf · inference-time-compute
#alphago #monte_carlo_tree_search #reinforcement_learning #credit_assignment_problem
> The podcast explores how AlphaGo's architecture—combining Monte Carlo Tree Search with neural networks and self-play—provides fundamental insights into building more capable AI systems, particularly addressing the credit assignment problem that plagues current RL approaches in LLMs. The discussion contrasts AlphaGo's MCTS approach, which provides clear training targets at every step, with naive policy gradient methods in LLMs that struggle to attribute success across 100k+ token trajectories. The conversation extends to automated AI research capabilities, identifying that while LLMs can implement experiments and optimize hyperparameters, they still struggle with choosing research directions and escaping dead ends—insights directly relevant to intelligence explosion timelines.

**✗ 5.0** — [[AINews] Everything is Conductor](https://www.latent.space/p/ainews-everything-is-conductor)  
*Latent Space* · ai-engineering-agents · agentic-workflows-production · ai-in-product-and-engineering

**✗ 2.7** — [How business operations teams use Codex](https://openai.com/academy/codex-for-work/how-business-operations-teams-use-codex)  
*OpenAI News* · ai-in-operations
#codex #business_operations #document_generation
> The article claims business operations teams can use Codex to generate various business documents like initiative briefs and strategy updates from work inputs. No specific evidence, mechanisms, or case studies are provided beyond a general assertion of capability. The article appears to be a promotional piece without substantive detail about implementation, results, or novel applications.

**✗ 2.7** — [How sales teams use Codex](https://openai.com/academy/codex-for-work/how-sales-teams-use-codex)  
*OpenAI News* · ai-in-sales-gtm
#codex #sales_automation #document_generation #sales_enablement
> The article describes how sales teams can apply OpenAI's Codex to generate sales documents including pipeline briefs, meeting prep packets, forecast reviews, account plans, and deal diagnoses. The content appears to be a high-level overview or promotional piece without detailed implementation evidence, specific examples, or quantitative results. It offers minimal actionable insight beyond identifying potential use cases for code-generation models in sales workflows.

**✗ 3.0** — [A new personal finance experience in ChatGPT](https://openai.com/index/personal-finance-chatgpt)  
*OpenAI News* · ai-in-finance-accounting
#personal_finance #chatgpt_pro #financial_account_integration #vertical_ai_application
> OpenAI announces a personal finance experience in ChatGPT Pro for U.S. users that allows secure connection of financial accounts for AI-powered insights. The feature provides guidance based on individual financial context, goals, and priorities. This represents OpenAI's expansion into vertical-specific consumer applications beyond general-purpose chat.

**✗ 3.7** — [Databricks brings GPT-5.5 to enterprise agent workflows](https://openai.com/index/databricks)  
*OpenAI News* · agentic-workflows-production · ai-b2b-saas · model-architecture

**✗ 4.7** — [The First Derivative of Inference](https://www.tomtunguz.com/first-derivative-of-inference/)  
*Tomasz Tunguz* · inference-efficiency · ai-b2b-saas · build-vs-buy-enterprise-ai

## Fri, 12 Ap

**✓ 7.0** — [Diffusion Models for Video Generation](https://lilianweng.github.io/posts/2024-04-12-diffusion-video/)  
*Lilian Weng* · multimodal-models · model-architecture
#diffusion_models #video_generation #v_parameterization #3d_unet
> This article provides a technical deep-dive into adapting diffusion models from image generation to video generation, covering both training-from-scratch approaches and techniques for adapting pre-trained image models. It explains the mathematical foundations (v-parameterization, noise schedules), architectural choices (3D U-Net, DiT), and practical adaptation methods (fine-tuning vs training-free). The work matters because video generation represents a significant leap in complexity from images, requiring temporal consistency and world knowledge that pushes the boundaries of generative modeling.

## Fri, 08 Ma

**✗ 2.7** — [AI Ascent 2026](https://sequoiacap.com/article/ai-ascent-2026/)  
*Sequoia* · model-architecture · agentic-workflows-production · lab-dynamics

**✗ 2.7** — [David Reich – Why the Bronze Age was an inflection point in human evolution](https://www.dwarkesh.com/p/david-reich-2)  
*Dwarkesh Podcast* · 
#ancient_dna #natural_selection #bronze_age #cognitive_evolution
> This podcast announcement discusses David Reich's new research finding that natural selection has accelerated in humans over the last 10,000 years, particularly during the Bronze Age, including selection for cognitive performance. The evidence comes from scaling ancient DNA sequencing and developing new statistical methods to track gene frequency changes. Reich also proposes a heretical model that Neanderthals were genetically-swamped modern humans rather than a separate archaic lineage.

## 2026-05-18

**✗ 5.3** — [Anthropic Acquires Stainless](https://www.anthropic.com/news/anthropic-acquires-stainless)  
*Anthropic Blog* · ai-engineering-agents · agentic-workflows-production · ai-in-product-and-engineering
#sdk_generation #mcp_servers #agent_connectivity #developer_tooling
> Anthropic is acquiring Stainless, a company that generates SDKs, CLIs, and MCP servers across multiple programming languages, to enhance agent connectivity and developer experience. Stainless has been powering Anthropic's official SDKs since the company's early days and enables developers and agents to connect to APIs through auto-generated, language-native tooling. The acquisition positions Anthropic to strengthen Claude's ability to connect to external systems as AI shifts from answering questions to taking autonomous actions.

**✗ 1.3** — [The Definitive Guide: Product Analytics for Product-Led Growth](https://openviewpartners.com/blog/the-definitive-guide-product-analytics-for-product-led-growth/)  
*OpenView Partners* · 
#product_led_growth #product_analytics #freemium
> This appears to be a promotional teaser for a guide about product analytics in product-led growth strategies. The text provides no actual evidence, frameworks, or mechanisms beyond mentioning generic PLG concepts like freemium models and virality. It offers no substantive content and functions purely as marketing copy to drive clicks.

**✗ 2.3** — [What’s going on with pricing this year? A deep dive into 2023 pricing data.](https://openviewpartners.com/blog/2023-pricing-data/)  
*OpenView Partners* · ai-pricing-packaging-saas
#saas_pricing #benchmarks #pricing_trends
> This article appears to be a brief teaser for OpenView's 2023 SaaS Benchmarks report focusing on pricing trends. The actual content provided contains no substantive analysis, evidence, data points, or specific findings. The article is essentially a redirect to another resource without meaningful information in the excerpt itself.

**✗ 1.3** — [The Pre-PMF Guide to Product Management: How to Move Faster and Stop Throwing Away Your Roadmaps](https://openviewpartners.com/blog/the-pre-pmf-guide-to-product-management/)  
*OpenView Partners* · 
#product_management #product_market_fit #roadmap_planning
> This is a promotional post announcing a guide about product management before achieving product-market fit, authored by Enzo Avigo from June. The post contains no actual content, analysis, or insights—only a headline and byline directing readers to download the full guide elsewhere. It provides no actionable information or frameworks that could be evaluated for depth or novelty.

**✗ 2.3** — [Usage-based Pricing Playbook](https://openviewpartners.com/blog/usage-based-pricing-playbook-3/)  
*OpenView Partners* · ai-pricing-packaging-saas

**✗ 2.3** — [B2B Marketing in 2024: 8 Trends That Are Changing the Game and What They Mean for Your Business](https://openviewpartners.com/blog/b2b-marketing-in-2024/)  
*OpenView Partners* · ai-in-marketing-content

**✗ 2.0** — [How Youtube 5x’d our Activation Rate](https://openviewpartners.com/blog/how-youtube-5xd-our-activation-rate-2/)  
*OpenView Partners* · ai-in-marketing-content

**✗ 1.0** — [Glaucous-winged Gull, Brown Pelican, Snowy Egret, Canada Goose](https://simonwillison.net/2026/May/18/sighting-362781627/#atom-everything)  
*Simon Willison* · 

## 2026-05-17

**✗ 2.7** — [GDS weighs in on the NHS's decision to retreat from Open Source](https://simonwillison.net/2026/May/17/gds-weighs-in/#atom-everything)  
*Simon Willison* · ai-governance-risk-compliance

## 2026-05-16

**✗ 1.7** — [Warelay -> OpenClaw](https://simonwillison.net/2026/May/16/openclaw-names/#atom-everything)  
*Simon Willison* · 

**✗ 1.7** — [Quoting Julia Evans](https://simonwillison.net/2026/May/16/julia-evans/#atom-everything)  
*Simon Willison* · 
#css #web_development #frontend_engineering
> Julia Evans reflects on learning to respect CSS as a technology after initially finding it frustrating, noting that many perceived difficulties (like centering) have been solved and CSS is hard because it solves genuinely hard problems. The quote advocates for taking CSS seriously rather than dismissing it as difficult. This is a brief personal reflection on web development practices with no connection to AI, enterprise systems, or related technologies.

## 2026-05-15

**✗ 1.7** — [inaturalist-clumper 0.1](https://simonwillison.net/2026/May/15/inaturalist-clumper/#atom-everything)  
*Simon Willison* · 
#inaturalist #data_clustering #personal_tooling #open_source_release
> This is a brief release announcement for inaturalist-clumper 0.1, a tool that groups iNaturalist wildlife sightings into geographic or temporal clumps for blog publishing. The author mentions using it in production for a few weeks and provides a link to example JSON output. This is a personal infrastructure tool with no connection to AI, enterprise software, or any covered topic areas.

**✗ 1.0** — [Western Gull, Rock Pigeon](https://simonwillison.net/2026/May/15/sighting-361818285/#atom-everything)  
*Simon Willison* · 
#bird_watching #pycon #personal_blog
> This is a personal blog post about bird watching before a PyCon conference, documenting sightings of a Western Gull and Rock Pigeon. The post contains no technical content, research, or analysis—just a casual observation about seeing a seagull near a Starbucks. It has no relevance to AI, semiconductors, enterprise technology, or any of the specified topic areas.
