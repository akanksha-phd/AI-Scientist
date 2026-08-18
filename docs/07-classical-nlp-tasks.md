# Classical NLP Tasks

## Token Classification
Assign a label to each token.
Examples: NER, POS, chunking.

Important:
- B-/I-/O labels
- align labels after subword tokenization
- -100 = ignored during loss
- AutoModelForTokenClassification
- metric: F1 / precision / recall

## Masked Language Modeling
Predict randomly hidden tokens.

Text → mask ~15% → predict missing tokens

Used for domain adaptation.
Model: AutoModelForMaskedLM
Metric: perplexity (lower is better)

## Translation
Sequence-to-sequence task.

Source language → model → target language

- AutoModelForSeq2SeqLM
- Seq2SeqTrainer
- DataCollatorForSeq2Seq
- metric: SacreBLEU (higher is better)

## Summarization
Long text → short meaningful text

- encoder-decoder model
- mT5 example
- Seq2SeqTrainer
- metric: ROUGE

## Causal Language Modeling
Predict the next token.

Previous tokens → next token

Used by GPT-style models.
- GPT2LMHeadModel
- mlm=False
- metric: perplexity

## LLM Foundations

Encoder → understanding/classification  
Decoder → generation  
Encoder-decoder → translation/summarization

Pretraining → learn general patterns  
Fine-tuning → adapt to a task/domain
