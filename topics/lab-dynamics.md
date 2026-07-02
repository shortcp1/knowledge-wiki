---
tags: [ai-competition-policy, ai-sovereignty, anthropic, chinese-ai-models, chinese-models, competitive-moats, competitive-restrictions, cybersecurity-capabilities, cybersecurity-threat, cybersecurity-vulnerabilities, data-retention-policy, export-controls, geopolitical-ai-access, glasswing-program, government-relations, jailbreaking, jailbreaks, lab-dynamics, llm-guardrails, model-access-restrictions, model-restrictions, model-safeguards, model-safety, national-security, open-research, open-source-models, platform-stability, pre-release-testing, terms-of-service, zhipu]
---

## Anthropic

### Mythos Model Development (April 2026)
Anthropic built an AI model called Mythos described as "so good at working with code it could pose a global cybersecurity threat." Company provided restricted access to small group of cybersecurity experts to evaluate the threat landscape.

### Claude Fable 5 Release & Controversy (June 2026)
Anthropic released Claude Fable 5, a version of its Mythos model with additional guardrails including:
- **Safety-justified restrictions**: limitations on hacking, bioweapons development
- **Competitive restrictions**: restrictions on developers' ability to use it to build competing LLM technology

**Silent Performance Degradation**: Initially, Anthropic silently degraded Claude Fable 5's performance for users detected to be working on LLM research through invisible interventions that weakened the model's outputs without notifying users. After significant backlash, Anthropic walked back this decision and committed to transparency when degrading performance, but Claude Fable 5 still refuses to use its latest capabilities to help AI researchers.

**Data Retention Policy**: Anthropic implemented a mandatory 30-day data retention policy for Claude Fable 5 usage, representing a sudden rule change that concerned developers.

**Platform Stability Concerns**: These moves demonstrated "raw power" by Anthropic and made developers question the stability of building on any one proprietary LLM provider. The sudden rule changes undermined the perception of Anthropic as a stable platform partner.

### Fable 5 and Mythos 5 Export Control Response (June 2026)

**Deployment Timeline**:
- Both models released June 9, 2026 (shared underlying model, Fable 5 with strong safeguards for general use, Mythos 5 with fewer safeguards limited to Project Glasswing partners)
- Export controls applied June 12, 2026 requiring real-time nationality verification
- Access suspended to all users (no reliable way to verify nationality in real-time)
- Export controls lifted June 30, 2026
- Fable 5 redeployed globally July 1, 2026
- Mythos 5 access restored to approved US organizations June 26, 2026

**Availability Post-Redeployment**:
- Fable 5 available on Claude Platform, Claude.ai, Claude Code, and Claude Cowork
- For Pro, Max, Team, and select Enterprise plans: included for up to 50% of weekly usage limits through July 7, after which available via usage credits
- Plans to re-enable on AWS, Google Cloud, and Microsoft Foundry

**Safety Response**: Anthropic trained improved safety classifier targeting the Amazon-reported bypass, blocking the technique in over 99% of cases. Blocked requests are now:
- Notified to users (shift from silent degradation approach)
- Routed to Opus 4.8 instead

**Project Glasswing**: Partnership program for trusted organizations with access to Mythos 5 for defensive cybersecurity work. Anthropic coordinating with government to expand access to broader domestic and international partners.

### Government Collaboration Expansion (June-July 2026)
Following export control incident, Anthropic established deeper collaboration with US government including pre-release testing, information sharing, and research collaboration protocols. See [[regulatory-policy]] for details.