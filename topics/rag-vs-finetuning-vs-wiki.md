---
tags: [agent-architecture, embedding-based-retrieval, fine-tuning, frontier-models, knowledge-distillation, knowledge-graphs, local-models, markdown-workflows, procedural-knowledge, rag, rag-vs-finetuning-vs-wiki, retrieval, skill-distillation, structured-knowledge, wikis]
---

# RAG vs. Fine-Tuning vs. Wiki/KG

Tracks the trade-offs between retrieval-augmented generation (RAG), fine-tuning, and structured knowledge representations for grounding LLMs in specific knowledge. Includes hybrid approaches and the emerging pattern of compounding wikis (Karpathy pattern).

Key questions tracked: When does fine-tuning actually beat RAG? What are the maintenance costs of each approach at scale? Where does structured knowledge (wikis, KGs) win over embedding-based retrieval?

## Key Claims

### Procedural Knowledge Retrieval vs. Factual RAG

**Skill Distillation Pattern** (Tunguz, 2026): Distinguishes procedural retrieval from traditional RAG:

- **Traditional RAG**: Retrieves facts from documents
- **Procedural Retrieval**: Retrieves step-by-step workflows/procedures for execution
- **Implementation**: Markdown skill files (`SKILL.md`) authored by frontier models, executed by smaller local models
- **Key difference**: Model doesn't need to learn the capability, only follow the steps

**Comparison to other approaches**:
- **vs. Fine-tuning**: Doesn't bake behavior into weights; procedures remain external and modifiable
- **vs. Instruction tuning**: Not prompt-response pairs compressed into weights; explicit procedural steps
- **vs. Classical knowledge distillation**: Doesn't compress probability distributions; transfers procedures through readable markdown

**Properties**:
- Inspectable: procedures are human-readable markdown
- Versionable: standard git workflows apply
- Hot-swappable: can update procedures without retraining
- Model-agnostic: student model can be swapped based on cost/performance

### Layered Knowledge Architecture

Emerging pattern combines multiple knowledge representations:
1. Local markdown knowledge base (workflow documentation)
2. Skill files (atomic procedural units)
3. Execution layer (smaller models following procedures)

Frontier model serves as "teacher" authoring skills; execution model serves as "student" following them. Library becomes institutional knowledge independent of model weights.

## Cross-References
- [[ai-engineering-agents]]
- [[rag-over-proprietary-content]]
- [[evals-production-deployment]]
- [[agentic-workflows-production]]