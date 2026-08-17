# Hugging Face Datasets

## Loading Data
- `load_dataset()` loads Hub, local, or remote datasets.
- Supports CSV, JSON, text, Pandas, etc.

## Cleaning Data
- `map()` → transform/add columns
- `filter()` → remove rows
- `shuffle()` → randomize
- `select()` → select rows
- `batched=True` → faster processing

## Large Datasets
- Memory mapping avoids loading the whole dataset into RAM.
- `streaming=True` processes huge datasets without downloading everything.

## Creating Datasets
API → JSON → Dataset → clean/augment → `push_to_hub()`

## Semantic Search
Text → Embeddings → FAISS → nearest matching documents

## Splits
Train → model training  
Validation → model tuning  
Test → final evaluation
