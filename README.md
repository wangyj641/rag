# RAG — Pride & Prejudice Demo

A small retrieval-augmented workflow that:

- loads the Project Gutenberg text [PridePrejudice.txt](PridePrejudice.txt),
- splits it into chunks,
- computes embeddings with SentenceTransformers,
- stores them in an ephemeral ChromaDB collection.

This repository contains the runnable analysis notebook [main.ipynb](main.ipynb) which implements the core steps and prints progress/results.

Key files

- [main.ipynb](main.ipynb) — primary notebook (chunking, embedding, ChromaDB save). Important symbols: [`split_into_chunks`](main.ipynb), [`embed_chunk`](main.ipynb), [`save_embeddings`](main.ipynb), and [`embedder`](main.ipynb).
- [PridePrejudice.txt](PridePrejudice.txt) — source text used for chunking / retrieval.
- [pyproject.toml](pyproject.toml) — project metadata and dependencies.
- [.gitignore](.gitignore) — ignores virtual env and build artifacts.

Quick start

1. Create and activate a virtual environment

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate
```
