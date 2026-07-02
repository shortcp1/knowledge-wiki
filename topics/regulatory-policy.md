---
tags: [ai-competition-policy, ai-lab-government-relations, ai-sovereignty, anthropic, chinese-ai-models, chinese-models, commerce-department, competitive-moats, congressional-regulation, cybersecurity-capabilities, cybersecurity-threat, cybersecurity-vulnerabilities, export-controls, foreign-national-access, geopolitical-ai-access, glasswing-program, government-relations, jailbreaking, jailbreaks, llm-guardrails, model-access-restrictions, model-jailbreaking, model-restrictions, model-safeguards, model-safety, national-security, nonproliferation-doctrine, open-research, open-source-models, platform-stability, pre-release-testing, regulatory-policy, safety-guardrails, white-house-ai-policy, zhipu]
---

## Export Controls

### Mythos/Fable Export Controls (June 2026)
The U.S. Commerce Department used its authority to regulate technologies that may be national security threats to restrict exports of Anthropic's Claude Mythos 5 and Claude Fable 5 models, requiring a license for use by any foreign national, whether inside or outside of the U.S., including foreign national Anthropic employees. This led Anthropic to disable access to Claude Fable 5 to all users worldwide.

**Timeline and Trigger**: 
- Mythos Preview announced with restricted access (April 2026) due to advanced cybersecurity capabilities
- Claude Fable 5 (modified safer version of Mythos) released to public (June 9, 2026)
- Amazon researchers found a jailbreak method that bypassed Fable 5's safeguards, allowing it to identify software vulnerabilities and produce exploit code for one case
- U.S. Government declared model a national security threat and placed export controls (June 12, 2026)
- Anthropic revoked access to both Claude Mythos 5 and Claude Fable 5 hours after government directive
- Amazon CEO Andy Jassy reportedly informed government officials that Fable would be dangerous (Amazon is both invested in Anthropic and building competing AI models)
- Export controls lifted (June 30, 2026)
- Fable 5 redeployed globally (July 1, 2026)
- Mythos 5 access restored to approved US organizations (June 26, 2026) with plans to expand to broader domestic and international partners in Glasswing program

**Anthropic's Position**: Company claims the identified vulnerabilities were "relatively simple" and discoverable by other publicly-available models without requiring a bypass. Anthropic argued that non-universal jailbreaks are inevitable and narrow, with no evidence of a universal jailbreak. 

**Technical Analysis**: Anthropic's testing confirmed that many less capable models (Claude Opus 4.8, GPT-5.5, Kimi K2.7) could identify the same vulnerabilities as Fable 5. All tested models (including Claude Haiku 4.5, Sonnet 4.6, Opus 4.6, Opus 4.7, Opus 4.8, GPT-5.4, GPT-5.5, Kimi K2.7) could produce the same exploit demonstration. The reported technique did not expose unique Mythos-level cyber capabilities; it was characterized as "routine defensive cybersecurity work" and a "borderline case" for Fable 5's safeguards.

**Resolution**: Anthropic trained an improved safety classifier that blocks the reported bypass technique in over 99% of cases. When requests are blocked, users are notified and requests are routed to Opus 4.8 instead.

### Shared Industry Framework for Jailbreak Assessment
In response to the Fable 5 export control incident, Anthropic, Amazon, Microsoft, Google, and other Glasswing partners began developing a shared framework for assessing and fixing potential jailbreaks. The framework aims to:
- Provide a consistent way to assess severity of jailbreaks
- Help AI developers triage new findings
- Enable launching highly capable models with greater safety
- Communicate risk levels consistently to government and industry partners

### Enhanced Government Collaboration
Following the export control incident, Anthropic strengthened collaboration with the U.S. government including:
- Pre-release testing protocols
- Information sharing agreements
- Research collaboration initiatives