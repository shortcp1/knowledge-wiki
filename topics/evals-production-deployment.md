---
tags: [agent-benchmarks, agentic-harness, agentic-workflows, agents-last-exam, arc-agi, arc-prize, benchmark-design, benchmark-evaluation-methodology, benchmark-methodology, benchmark-replacement, biology-benchmarks, capture-the-flag, coding-agent-indices, coding-agents, coding-evals, composite-scoring, ctf-evals, cybench, cybersecurity-agent-evaluation, cybersecurity-benchmarks, cybersecurity-evals, data-retention-constraints, deepswe, docker-sandboxing, economically-useful-tasks, evals-production-deployment, evaluation-transparency, expert-vetted-benchmarks, exploit-generation, fallback-scoring, feature-implementation, feature-implementation-evals, first-solve-time, human-written-tests, humanitys-last-exam, incident-diagnosis, intelligence-indices, long-horizon-agentic-tasks, model-benchmarking, model-evaluation, model-fallback-evaluation, model-routing, model-selection-strategy, multi-agent-orchestration, multi-language-evals, private-codebase-evals, program-replication, program-synthesis, program-synthesis-evals, prompt-filtering, proprietary-benchmarks, pure-vs-practical-evaluation, refusal-handling, safety-classifiers, safety-guardrails, sandbox-environments, sandboxed-environments, science-benchmarks, subtask-grading, swbench, swe-bench, system-diagnosis-evals, token-pricing, vals-ai, vision-models, vulnerability-discovery, vulnerability-exploitation, zero-day-attacks, zero-day-scenarios]
---

## Evolution Beyond SWE-bench

The SWE-bench family (SWE-bench, SWE-Bench Pro, SWE-bench Multilingual, and SWE-bench Verified) is being challenged by new benchmarks that evaluate agentic software engineering performance in more demanding ways. Three notable successors have emerged as of June 2026:

### DeepSWE

**Developer**: Datacurve

**Scope**: 113 problems across 5 programming languages

**Focus**: Feature implementation capabilities (vs. bug fixing in SWE-bench)

**Key Characteristics**:
- Problems vetted by human experts
- Uses brief prompts (in contrast to detailed prompts in SWE-Bench Pro)
- Solutions require ~5.5x more lines of code than SWE-Bench Pro
- Draws from private codebases to minimize [[benchmark-contamination]] risk
- Uses human-written problems and tests based on real repositories but not taken from existing or solved code
- Example task: "Extend indexing ranges so arrays a

## Cybersecurity Evaluation Patterns

### Four Core Components of Cybersecurity Evals

**Reference**: Eugene Yan (June 2026)

Cybersecurity benchmarks share a common architecture based on four primitives:

1. **Sandboxed Target**: Vulnerable systems run within Docker containers, ranging from single containers with vulnerable codebases to multi-host networks with services, databases, and hosts

2. **Difficulty Inputs**: Task difficulty varies based on what information is provided:
   - **Hardest (Zero-Day)**: Agent only receives vulnerable code, with no knowledge of vulnerability or patch
   - **Moderate (One-Day)**: Includes vulnerability description and/or patch (attackers reverse-engineer patch to build exploit)
   - **Easier**: Additional hints like crash traces or proof-of-concept (PoC) that triggers the vulnerability

3. **Tools**: Bash shell, read/write tools, websearch, debuggers, static analyzers, or auxiliary services for state tracking in long-horizon tasks

4. **Grader**: Deterministic evaluation system where agents submit work (exploits, captured flags) for immediate feedback

### Evaluation Philosophy

**Outcome-Based Assessment**: Most cybersecurity benchmarks evaluate outcomes rather than methods used:
- For C/C++ memory bugs: Success = triggering sanitizer crash
- For unauthorized code execution: Success = retrieving hidden flag string only accessible via successful exploit
- Automated transcript audits confirm actual exploitation vs. reward hacking

**Challenge with Binary Grading**: Pass/fail grading is coarse—a model scoring zero might have found and reproduced the vulnerability but failed to build an exploit, versus one that never found the vulnerability at all.

### Progressive Subtask Grading

To provide granular assessment, cybersecurity evals award partial credit via attack chain progression:

- **Level 1**: Find the vulnerability in the codebase
- **Level 2**: Reproduce the vulnerability with a PoC that triggers it
- **Level 3**: Exploit the vulnerability via unauthorized code execution on the target
- **Level 4**: Achieve attacker's goal (data exfiltration, privilege escalation, etc.)

### Cybench: Capture The Flag Benchmark

**Source**: 40 professional-level CTF tasks from four competitions (HackTheBox, SekaiCTF, Glacier, HKCert)

**Difficulty Metric**: First Solve Time (FST)—time for first human team to solve challenge. Range: 2 minutes to 25 hours.

**Task Structure**:
- **Description**: Objective statement (e.g., "capture the flag on otp:80")
- **Starter Files**: 
  - Local files (readable, writable, executable)
  - Remote files (task servers in Docker containers)
  - Examples: encrypted secrets requiring decryption, web servers vulnerable to SQL injection
- **Evaluator**: Checks submission against actual secret key (1 for correct, 0 for incorrect); tracks efficiency metrics (token counts, wall-clock time)

**Agent Harness**:
- Operates within Docker container via act-execute-update loop
- Agent runs bash command → observes output → updates memory
- Memory contains: initial prompt + last three response-observation pairs
- Iteration limits: 15 steps for unguided mode, 5 steps per subtask in guided mode

**Note on Capture The Flag**: CTF exercises require participants to find secret "flag" strings hidden in deliberately vulnerable software. The only way to obtain the flag is to identify vulnerabilities and execute working exploits—proving the agent found the bug and exploited it.

See also: [[ai-engineering-agents]] for related agent harness patterns, [[agentic-workflows-production]] for production deployment considerations