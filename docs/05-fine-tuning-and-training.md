# Fine-Tuning and Training

## Data Preparation
- `load_dataset()` loads datasets from Hugging Face Hub.
- `Dataset.map(..., batched=True)` speeds up tokenization.
- `DataCollatorWithPadding` performs dynamic padding.
- `token_type_ids` identify sentence 1 vs sentence 2 in BERT.

## Trainer API
- `TrainingArguments` controls training settings.
- `Trainer` handles training/evaluation.
- `compute_metrics` calculates accuracy/F1.
- `fp16=True` enables mixed precision.
- Gradient accumulation simulates larger batches.

## Manual PyTorch Loop
Forward → Loss → Backward → Optimizer → Scheduler → Zero gradients

- `AdamW` updates model weights.
- `model.train()` enables training mode.
- `model.eval()` enables evaluation mode.
- `torch.no_grad()` disables gradients during evaluation.

## Accelerate
`accelerator.prepare()` and `accelerator.backward()` simplify multi-GPU/TPU training.

## Learning Curves
- Healthy: train and validation improve together.
- Overfitting: train improves, validation worsens.
- Underfitting: both perform poorly.
- Erratic curves: often reduce learning rate or increase batch size.

## Workflow
Raw data → Tokenization → Dynamic padding → Fine-tuning → Evaluation → Learning-curve analysis
