# Embeddings and Attention Foundations

## What I learned

### Embeddings
Embeddings convert discrete token IDs into learned vector representations.

### Attention
Attention allows a model to determine which tokens are most relevant when processing another token.

### Query, Key, Value
- Query: What information am I looking for?
- Key: How relevant is this token?
- Value: What information does this token provide?

### Self-Attention
Self-attention allows tokens within the same sequence to exchange contextual information.

### Attention Flow

Embedding
→ Query / Key / Value
→ Attention scores
→ Softmax
→ Attention weights
→ Weighted values
→ Contextual representation
