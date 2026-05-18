# Agentic Workflows in Production

Covers real deployments of multi-step AI agent systems in production environments: human-in-the-loop designs, failure recovery, audit trails, latency management, and cost control. Distinguishes between what works in demos vs. what ships to customers.

Key questions tracked: What agent architectures are actually in production at scale? Where do agents fail in ways that matter? How are teams handling agent observability and debugging?

## Key Claims
<!-- agent-maintained -->

### Coding Agents
- **Codex Windows Deployment (OpenAI, May 2026)**: OpenAI shipped Codex on Windows with a secure sandbox implementation. Key production requirements included:
  - Controlled file system access
  - Network access restrictions
  - Safe code execution environment
  - This represents a production-grade coding agent deployment pattern addressing security constraints.

## Cross-References
- [[ai-engineering-agents]]
- [[evals-production-deployment]]
- [[ai-governance-risk-compliance]]