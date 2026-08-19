# Debugging Transformers

## Debugging order

Dataset
→ DataLoader
→ Model forward pass
→ Loss
→ Backward
→ Optimizer
→ Evaluation

## Key checks

- Read Python traceback from bottom to top.
- Inspect `trainer.train_dataset`.
- Decode `input_ids` to verify preprocessing.
- Use tokenized datasets, not raw datasets.
- Use `DataCollatorWithPadding` when sequence lengths differ.
- Make sure `num_labels` matches the dataset.
- For strange CUDA errors, reproduce on CPU for a clearer error.
- CUDA OOM → reduce batch size or model size.
- Test `trainer.evaluate()` before full training.
- Classification logits usually need:

```python
predictions = np.argmax(predictions, axis=1)
