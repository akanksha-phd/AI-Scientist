# LLM Inference and Deployment

## Inference Basics

Hugging Face tokenizers prepare text for Transformer models by handling:

* Tokenization
* Input IDs
* Padding
* Attention masks
* Truncation
* Special tokens

```python
inputs = tokenizer(
    sequences,
    padding=True,
    truncation=True,
    return_tensors="pt"
)

outputs = model(**inputs)
```

### Important Concepts

* **Batching:** Process multiple sequences together.
* **Padding:** Makes sequences equal length.
* **Attention mask:** `1` = use token, `0` = ignore padding.
* **Truncation:** Cuts sequences that are too long.
* **Special tokens:** Model-specific tokens such as `[CLS]` and `[SEP]`.

## Optimized LLM Deployment

Three common frameworks are:

| Framework | Main Use                  | Optimization                          |
| --------- | ------------------------- | ------------------------------------- |
| TGI       | Production serving        | Flash Attention + continuous batching |
| vLLM      | High-throughput inference | PagedAttention                        |
| llama.cpp | Local inference           | Quantization                          |

### TGI

Designed for production LLM serving. It uses Flash Attention and continuous batching to improve GPU efficiency.

### vLLM

Uses **PagedAttention** to manage the KV cache efficiently, reducing GPU memory waste and increasing throughput.

### llama.cpp

Optimized for running models locally on CPUs and consumer GPUs. It uses **quantization** to reduce model size and memory usage.

## Generation Parameters

* **Temperature:** Controls randomness.
* **Top-k:** Samples from the `k` most likely tokens.
* **Top-p:** Samples from tokens covering a chosen probability mass.
* **Repetition penalty:** Reduces repetitive output.
* **Max tokens:** Controls output length.
* **Stop sequences:** Stop generation when specific text appears.

## Key Takeaway

```text
TGI       → production serving
vLLM      → fast GPU inference + PagedAttention
llama.cpp → local inference + quantization
```

The KV cache stores previous attention keys and values so the model does not need to recompute them during generation.
