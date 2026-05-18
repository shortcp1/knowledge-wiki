---
tags: [adversarial-attacks, ai-governance-risk-compliance, ai-integration, benchmark-evals, cybersecurity, dual-use, frontier-models, jailbreak-prompting, jailbreaking, model-safety, offensive-capabilities, red-teaming, rlhf, scaling-laws, startup-adoption, white-box-black-box]
---

# AI Governance, Risk & Compliance

Covers enterprise AI policy frameworks, AI risk management (model auditing, bias testing, explainability), compliance requirements (EU AI Act, state laws, sector-specific rules), and the emerging role of AI governance functions in large organizations.

Key questions tracked: What does the EU AI Act require of different risk-tier systems? How are enterprises structuring AI governance committees? What are the liability exposure points for AI-assisted decisions?

## Key Claims
<!-- agent-maintained -->

### Code Execution Security
- **Sandboxing for Code-Generating Agents (OpenAI Codex, May 2026)**: Production deployment of code-generating agents like Codex requires sandbox architectures with:
  - Controlled file access permissions
  - Network restriction capabilities
  - Isolated execution environments
  - This establishes a security baseline for agents that generate and execute code on user systems.

### Offensive Cybersecurity Capabilities and Dual-Use Concerns (April 2026)
- **Scaling law for cyberoffense**: Lyptus Research found clear trend of more advanced models achieving better cyberattack capabilities
  - Capability doubling time: 9.8 months across frontier models since 2019; 5.7 months for models since 2024
  - GPT-5.3 Codex and Opus 4.6 achieve 50% success on tasks taking human experts 3.1-3.2 hours ("roughly half a working day of professional offensive security work")
- **Open-weight diffusion risk**: GLM-5 lags closed-source frontier by only 5.7 months, suggesting "frontier offensive-cyber capability may diffuse into open-weight form on relatively short timelines"
- **Dual-use challenge**: Research highlights fundamental AI challenge as "everything machine" - capabilities that improve defensive security equally enable offensive capabilities

### Adversarial Attacks on LLMs (October 2023)
- **Threat model**: Adversarial attacks are inputs designed to trigger models to output undesired content; assumes attacks occur at inference time with fixed model weights
- **Classification attacks**: Goal is to find adversarial input $\mathbf{x}_\text{adv}$ with imperceptible difference from $\mathbf{x}$ such that $f(\mathbf{x}) \neq f(\mathbf{x}_\text{adv})$
- **Generative attacks**: Aim to trigger model to violate built-in safe behavior (e.g., output unsafe content on illegal topics, leak private information or training data)
- **Success measurement challenge**: For generative tasks, judging attack success is difficult and demands high-quality classifiers or human review
- **White-box vs. black-box**:
  - White-box: Attackers have full access to model weights, architecture, and training pipeline (only possible for open-source models)
  - Black-box: Attackers only have API-like access to provide input and receive output
- **Attack taxonomy** (October 2023):
  - **Token manipulation** (black-box): Alter small fraction of tokens to trigger failure while maintaining semantic meaning
  - **Gradient-based attacks** (white-box): Use gradient signals to learn effective attacks
  - **Jailbreak prompting** (black-box): Heuristic-based prompting to bypass built-in model safety
  - **Human red-teaming** (black-box): Human attacks model with or without assist from other models
  - **Model red-teaming** (black-box): Model attacks model, where attacker model can be fine-tuned
- **Token manipulation methods**: TextAttack framework (Morris et al. 2020) implements word/token manipulation methods including synonym replacement; most work experiments with classification and entailment prediction
- **SEARs approach**: Semantically Equivalent Adversaries Rules (Ribeiro et al. 2018) use minimal token manipulation to trigger model failures
- **Inference-time attacks scope**: This taxonomy excludes training-time attacks like data poisoning or extraction of pre-training data/private knowledge
- **Historical context**: ChatGPT launch accelerated real-world LLM use; OpenAI invested significant effort in alignment (e.g., via [[rlhf]]) to build default safe behavior
- **Cross-domain insight**: Large body of adversarial attack work exists for images in continuous high-dimensional space; text attacks more challenging due to discrete nature and lack of direct gradient signals