# Models and Hugging Face Pipeline

## How a Pipeline Works

A Hugging Face `pipeline()` combines three main steps:

```text
Raw Text
   ↓
Tokenizer
   ↓
Model
   ↓
Post-processing
   ↓
Prediction
```

For classification:

```text
Text
↓
Tokenizer
↓
input_ids + attention_mask
↓
Transformer
↓
Hidden States
↓
Classification Head
↓
Logits
↓
Softmax
↓
Probabilities / Label
```

## Loading a Model

```python
from transformers import AutoModel

model = AutoModel.from_pretrained("bert-base-cased")
```

`AutoModel` automatically selects the correct model architecture for the checkpoint.

A **checkpoint** is a saved pretrained model that can be loaded and reused.

## Model Files

When a model is saved, important files include:

* `config.json` — model configuration
* `model.safetensors` — learned model weights

## Hidden States

The Transformer produces contextual numerical representations called **hidden states**.

Example shape:

```text
[2, 16, 768]

Batch size × Sequence length × Hidden size
```

## Base Model vs Task-Specific Model

`AutoModel`

```text
Input → Transformer → Hidden States
```

`AutoModelForSequenceClassification`

```text
Input
↓
Transformer
↓
Classification Head
↓
Logits
```

## Logits and Softmax

**Logits** are the model's raw prediction scores.

```text
Logits
↓
Softmax
↓
Probabilities
```

For example:

```text
[-1.56, 1.61]
       ↓
    Softmax
       ↓
[0.04, 0.96]
```

## Key Points to Remember

* `pipeline()` combines preprocessing, inference, and post-processing.
* `AutoModel` loads the base Transformer.
* A checkpoint contains a pretrained model that can be reused.
* Transformers produce hidden states.
* Task-specific heads generate outputs such as classification logits.
* Logits are raw model scores.
* Softmax converts classification logits into probabilities.

## Interview Summary

A Hugging Face pipeline preprocesses text with a tokenizer, passes the numerical inputs through a Transformer, and post-processes the model output. The Transformer produces contextual representations, while a task-specific head can generate logits for tasks such as classification.
