
Frontend (not decided yet)
Backend (Python)
LLM (OpenAI)
Database (later)
Deployment (AWS/Azure later)


User

↓

Upload DEG

↓

LLM

↓

PubMed

↓

Pathway DB

↓

Report



## Text Processing Layer

Scientific text will be processed before being passed to language models.

Planned flow:

Research paper / query
→ text preprocessing
→ tokenizer
→ model-compatible inputs
→ LLM or embedding model
→ downstream retrieval / reasoning
