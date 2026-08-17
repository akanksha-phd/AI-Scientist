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



## Tokenizer Training

Tokenizer:
Text → tokens → token IDs → model

Training a tokenizer learns useful words/subwords from a corpus.

`train_new_from_iterator()`:
existing tokenizer rules + new corpus → new vocabulary

## Fast Tokenizers
- Rust-backed and faster for batches.
- Keep mappings between tokens and original text.
- Useful methods: `word_ids()`, offset mapping.

## QA
Question + context → predict answer start/end tokens → offsets recover exact text.

Long contexts:
- split into chunks
- use overlap with `stride`

## Tokenization Pipeline
Raw text
→ Normalization
→ Pre-tokenization
→ Subword tokenization

Normalization = clean text  
Pre-tokenization = initial word/punctuation splitting

Main subword algorithms:
- BPE
- WordPiece
- Unigram
