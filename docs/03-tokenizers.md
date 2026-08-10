# Tokenizers

## Core idea
Tokenizers convert raw text into numerical inputs that Transformer models can process.

## Types of tokenization
- Word-based
- Character-based
- Subword-based

## Why subword tokenization matters
Subword tokenization balances vocabulary size, sequence length, and unknown-token frequency.

## BERT example
BERT uses WordPiece tokenization.

Example:

Transformer
→ transform + ##er

## Encoding
Text → Tokens → Input IDs

## Decoding
Input IDs → Tokens → Readable text

## Key methods
- AutoTokenizer.from_pretrained()
- tokenizer.tokenize()
- tokenizer.convert_tokens_to_ids()
- tokenizer.decode()

## Interview takeaway
Subword tokenization allows models to represent rare words using reusable smaller units while keeping the vocabulary manageable.
