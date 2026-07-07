---
tags: [agency-dexterity, ai-agents, ai-in-operations, ai-infrastructure-deployment, autonomous-agents, claude-code, code-scanning, commercial-viability, cybersecurity-automation, data-center-operations, data-center-regulation, embodied-ai, energy-constraints, general-purpose-robots, government-cybersecurity, grid-demand-management, grid-flexibility, hyperscale-operations, infrastructure-efficiency, labor-automation, legacy-code-modernization, legacy-modernization, manufacturing-automation, operational-automation, performance-optimization, physical-automation, power-flexible-data-centers, power-management, regression-detection, robotics, robotics-autonomy, technical-debt, vulnerability-remediation, workload-orchestration, workload-throttling]
---

# AI in Operations

Covers AI in internal operations: workflow automation, process mining, IT service management, supply chain optimization, document processing, and physical robotics automation. Tracks both standalone operations AI tools and AI features in ERP/BPM platforms.

Key questions tracked: Where is AI actually replacing manual processes end-to-end vs. augmenting? What is the integration cost of AI operations tools in legacy environments? How do robotics levels of autonomy map to commercial viability?

## Key Claims
<!-- agent-maintained -->

### Infrastructure & Performance Engineering

**Meta Capacity Efficiency AI Agent Platform (Meta, April 2026)**
- **Business Problem**: At hyperscale (3B+ users), even 0.1% performance regressions translate to significant power consumption. Human engineering time is bottleneck for investigating/resolving performance issues. Need both offense (proactive optimization finding) and defense (regression detection/mitigation).
- **AI Pattern**: Unified agentic platform with two layers:
  - **MCP Tools**: Standardized interfaces for LLMs to invoke code (query profiling data, fetch experiment results, retrieve config history, search code, extract docs)
  - **Skills**: Encoded domain expertise of senior efficiency engineers into reusable, composable reasoning patterns (e.g., "consult top GraphQL endpoints for endpoint latency regressions")
- **Success Factors**:
  - Rea

### Government Cybersecurity & Legacy System Modernization

**Alberta Government Code Security Review (Government of Alberta, July 2026)**
- **Business Problem**: Provincial government maintains systems for 27 ministries (1,280 applications, 3,400 code repositories) with billions in accumulated technical debt. Most code never underwent systematic security review. Systems hold highly sensitive data (tax records, procurement data, social services files) but are "old, insecure, and incompletely documented."
- **AI Pattern**: Multi-agent autonomous scanning and remediation system
  - **Stage 1 - Mass Scanning**: ~50 Claude Code agents (Opus + Sonnet) working in parallel. Two-stage routine: rules engine flags known vulnerability patterns, then LLM reviews flags and cites exact file/line.
  - **Stage 2 - Automated Remediation**: Claude Code generates fixes, writes missing tests first if needed, rebuilds legacy systems in modern languages when patching inefficient.
  - **Stage 3 - Continuous Review**: Specialized agent roles:
    - "Red team" agent: Probes application externally like attacker, maps exploit paths
    - "Blue team" agent: Assesses defenses against international security standards, writes remediation plans with exact file references
    - Additional agents: Code quality checks, public-facing writing clarity
    - Checks ~95 security controls per application per pass
  - Built on Claude Agent SDK
- **Success Factors**:
  - **Parallel autonomous execution**: 50 agents scanning simultaneously
  - **Two-stage verification**: Automated pattern matching + LLM contextual review reduces false positives
  - **Human-in-the-loop approval**: All patches reviewed by Ministry engineers before shipping
  - **Test-first approach**: Agents write automated tests before patching when missing
  - **Pragmatic modernization**: Rebuilds systems in modern languages when more efficient than patching legacy code
  - **Continuous integration**: Security agents embedded throughout development process, not just one-time scan
- **Industry**: Government / Public Sector
- **Business Function**: IT Operations, Cybersecurity, Application Security
- **Quantitative Outcomes**:
  - **466 million lines of code** scanned in **20 hours**
  - Estimated **6.5 years** for traditional approach to complete same review
  - **~330x faster** than manual review (6.5 years vs 20 hours)
  - Legacy subsidy portal (originally 5 months to build, ~25 years old Java) **rebuilt in 4-5 days**
  - **~30x faster** legacy system modernization
  - Found vulnerabilities that "traditional automated scanning tools had missed"
- **Generalizability**:
  - **High generalizability across sectors**: Pattern applies to any organization with:
    - Large legacy codebases with accumulated technical debt
    - Insufficient security review coverage
    - Limited engineering capacity for manual audits
    - Regulatory/compliance pressure for security attestation
  - **Specific applicable industries**:
    - **Financial services**: Banks, insurance with decades-old core banking systems
    - **Healthcare**: Hospital systems, health records platforms with HIPAA requirements
    - **Other government agencies**: Federal, state, local with similar technical debt challenges
    - **Education**: Universities with sprawling legacy student information systems
    - **Enterprise IT departments**: Large corporations with decades of accumulated applications
  - **Cross-functional applications**:
    - Application security teams in any industry
    - Platform engineering/DevOps teams managing large application portfolios
    - Compliance teams needing security attestation
    - Technical debt reduction initiatives
  - **Key requirement for replication**: Access to codebase, ability to run agents with appropriate permissions, engineering capacity to review/approve fixes