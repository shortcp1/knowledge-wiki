---
tags: [adaptive-attention-span, adaptive-modeling, attention-mechanisms, attention-optimization, content-based-attention, context-length, context-memory, depth-adaptive-transformer, distance-enhanced-attention, efficient-attention, external-memory, fixed-local-context, global-context, local-context, low-rank-attention, model-efficiency, positional-encoding, recurrent-attention, relative-position-encoding, rotary-embeddings, rotary-position-embedding, scaled-dot-product-attention, self-attention, sparse-attention, sparse-attention-patterns, strided-context, transformer-architecture]
---

# Attention Mechanisms

Covers attention mechanism variants and optimizations in transformer architectures. Includes efficient attention patterns, positional encoding methods, adaptive mechanisms, and memory extensions.

Key questions tracked: What attention optimizations reduce computational cost without sacrificing quality? How do different positional encoding schemes affect long-context performance? What are the tradeoffs between different sparse attention patterns?

## Core Attention Concepts

### Attention Definition
- **General mechanism**: Neural network mechanism where model learns to make predictions by selectively attending to given set of data
- **Quantification**: Attention amount quantified by learned weights
- **Output form**: Weighted average of attended values

### Self-Attention Properties (2017)
- **Definition**: Attention mechanism where model predicts for one part of data sample using other parts of same sample
- **Permutation invariance**: Operation on sets (order-independent without positional encoding)
- **Conceptual similarity**: Related to non-local means in signal processing

### Scaled Dot-Product Attention (2017)
- **Formula**: $\text{attn}(\mathbf{Q}, \mathbf{K}, \mathbf{V}) = \text{softmax}(\frac{\mathbf{Q} {\mathbf{K}}^\top}{\sqrt{d_k}})\mathbf{V}$
- **Scalar score**: $a_{ij} = \text{softmax}(\frac{\mathbf{q}_i {\mathbf{k}_j}^\top}{\sqrt{d_k}})$ between query $\mathbf{q}_i$ and key $\mathbf{k}_j$
- **Attention matrix**: $\mathbf{A} \in \mathbb{R}^{L \times L}$ for input sequence of length $L$: $\mathbf{A} = \text{softmax}(\mathbf{Q}\mathbf{K}^\top / \sqrt{d_k})$
- **Scaling rationale**: Division by $\sqrt{d_k}$ prevents dot products from growing large in magnitude
- **Attention scope**: $S_i$ denotes collection of key positions for $i$-th query $\mathbf{q}_i$ to attend to
- **Cross-reference**: See [[model-architecture]] for multi-head implementation details

## Positional Encoding Methods

### Sinusoidal Positional Encoding (2017)
- **Type**: Fixed, non-learned positional encoding in original Transformer
- **Properties**: Deterministic function of position

### Learned Positional Encoding
- **Type**: Trainable positional embeddings
- **Tradeoff**: More flexible but requires learning from data

### Relative Position Encoding
- **Approach**: Encodes relative rather than absolute positions between tokens
- **Motivation**: May better capture local dependencies

### Rotary Position Embedding (RoPE)
- **Type**: Rotation-based positional encoding
- **Properties**: Encodes position through rotation in embedding space

## Extended Context Techniques

### Context Memory
- **Purpose**: Extend effective context length beyond standard attention window
- **Mechanism**: (Details to be added from future sources)

### Non-Differentiable External Memory
- **Type**: External memory module that is not differentiable
- **Purpose**: Store and retrieve information beyond standard context window

### Distance-Enhanced Attention Scores
- **Approach**: Modify attention scores based on distance between tokens
- **Purpose**: Bias attention based on positional distance

### Recurrent Mechanisms
- **Approach**: Make transformer recurrent to process longer sequences
- **Purpose**: Enable processing of sequences longer than training context

## Adaptive Modeling

### Adaptive Attention Span
- **Mechanism**: Allow model to learn different attention spans for different heads or layers
- **Benefit**: Efficiency by focusing computation where needed

### Depth-Adaptive Transformer
- **Mechanism**: Adaptively determine computation depth per token
- **Benefit**: Computational efficiency by using less computation for easier tokens

## Efficient Attention Patterns

### Sparse Attention Overview
- **Motivation**: Full $O(L^2)$ attention complexity becomes prohibitive for long sequences
- **Approach**: Restrict attention to subset of positions
- **Cross-reference**: See [[inference-efficiency]] for implementation optimizations

### Fixed Local Context
- **Pattern**: Each token attends only to fixed window of nearby tokens
- **Complexity**: Reduces to $O(L \times w)$ where $w$ is window size
- **Tradeoff**: Loss of long-range dependencies

### Strided Context
- **Pattern**: Attend to tokens at regular intervals (stride)
- **Use case**: Capture regular patterns at distance

### Combination of Local and Global Context
- **Pattern**: Mix of local attention and global attention (e.g., to special tokens)
- **Examples**: Longformer, BigBird patterns
- **Benefit**: Balance between local detail and global context

### Content-Based Attention
- **Approach**: Determine attention pattern based on content similarity
- **Examples**: Routing attention, learned sparse patterns
- **Benefit**: Data-dependent sparsity patterns

### Low-Rank Attention
- **Approach**: Approximate attention matrix with low-rank decomposition
- **Complexity**: Reduce memory and computation through factorization
- **Examples**: Linformer, other low-rank approximations

## Application Domains

### Transformers for Reinforcement Learning
- **Application**: Use transformer architectures in RL settings
- **Adaptations**: (Details to be added from future sources)
- **Cross-reference**: See [[reinforcement-learning]] for training approaches