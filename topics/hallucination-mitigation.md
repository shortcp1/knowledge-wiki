# Hallucination Mitigation

Tracks methods for reducing and preventing fabricated, unfaithful, or ungrounded outputs from large language models. Covers detection techniques, prevention strategies, and architectural approaches to improve factuality.

Key questions tracked: What causes hallucinations at different training stages? Which mitigation techniques are most effective? How do we balance knowledge updating with hallucination risk?

## Definitions

### Types of Hallucination
- **In-context hallucination**: Model output inconsistent with provided source content in context
- **Extrinsic hallucination**: Model output not grounded by pre-training dataset or verifiable world knowledge; includes cases where model should acknowledge not knowing the answer

## Root Causes

### Pre-training Data Issues (July 2024)
- **Data quality problems**: Crawled Internet data contains out-of-date, missing, or incorrect information
- **Memorization risk**: Models may incorrectly memorize flawed information through log-likelihood maximization during pre-training
- **Scale challenge**: Pre-training corpus too large to verify or retrieve per generation for conflict identification

### Fine-tuning New Knowledge (Gekhman et al. 2024)
- **Knowledge learning asymmetry**: LLMs learn fine-tuning examples with new knowledge slower than examples consistent with pre-existing knowledge
- **Hallucination amplification**: Once new knowledge examples are eventually learned, they increase the model's tendency to hallucinate
- **Compute constraint**: Fine-tuning uses much less compute than pre-training, making reliable new knowledge acquisition questionable

#### Knowledge Categories in Fine-tuning
Based on $P_{\text{Correct}}(q, a; M, T)$ - likelihood of accurate answer generation:
- **Known group** (3 subgroups):
  - HighlyKnown: Model consistently produces correct answers
  - MaybeKnown: Model sometimes produces correct answers  
  - WeaklyKnown: Model rarely produces correct answers
- **Unknown group**: Model does not know the answer

#### Fine-tuning Observations (EntityQuestions benchmark)
- **Learning speed**: Unknown examples fitted substantially slower than Known examples
- **Optimal performance point**: Best dev performance achieved when model learns majority of Known training examples but only few Unknown ones
- **Hallucination onset**: Model begins hallucinating when it learns most Unknown examples
- **MaybeKnown importance**: Among Known examples, MaybeKnown cases result in better overall performance than HighlyKnown
- **Risk assessment**: Supervised fine-tuning for knowledge updates carries significant hallucination risk

## Detection Methods

### Retrieval-Augmented Evaluation (Lee et al. 2022)
- **Benchmark**: FactualityPrompts dataset for quantifying model hallucinations
- **Approach**: Use retrieval to verify model outputs against external knowledge sources

### Sampling-Based Detection (July 2024)
- **Method**: Identify hallucinations through patterns in multiple generation samples
- **Application**: Detect inconsistencies or fabrications across different model outputs for same prompt

### Calibration of Unknown Knowledge (July 2024)
- **Goal**: Ensure models acknowledge uncertainty when they lack knowledge
- **Importance**: Avoiding fabrication requires both factuality AND willingness to say "I don't know"

### Indirect Query (July 2024)
- **Technique**: Probe model knowledge indirectly to detect fabricated content
- **Use case**: Identify when model is generating plausible-sounding but ungrounded information

## Mitigation Strategies

### RAG with Edits and Attribution (July 2024)
- **Approach**: Use retrieval-augmented generation with explicit attribution to sources
- **Benefit**: Ground outputs in verifiable external content rather than relying on potentially flawed memorization

### Chain of Actions (July 2024)
- **Method**: Structure model reasoning as explicit action sequences
- **Goal**: Make reasoning process transparent and verifiable at each step

### Sampling Methods (July 2024)
- **Technique**: Use multiple samples to identify and filter hallucinated content
- **Application**: Detect inconsistencies that suggest fabrication

### Fine-tuning for Factuality (July 2024)
- **Approach**: Specialized fine-tuning focused on improving factual accuracy
- **Note**: Must be balanced against fine-tuning hallucination risks identified by Gekhman et al.

### Fine-tuning for Attribution (July 2024)
- **Goal**: Train models to cite sources and ground claims
- **Benefit**: Make verification easier and reduce unfounded assertions

## Cross-References
- [[rag-vs-finetuning-vs-wiki]]
- [[evals-production-deployment]]
- [[model-training-dynamics]]