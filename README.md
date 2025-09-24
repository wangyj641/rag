# RAG — Pride & Prejudice Demo

A small Retrieval-Augmented Generation (RAG) demo that shows how to:

- load the Project Gutenberg text (Pride and Prejudice),
- split it into retrieval-friendly chunks,
- compute embeddings with SentenceTransformers,
- store embeddings in a Chroma collection (ephemeral by default),
- run simple retrieval over the text from a Jupyter notebook.

This repo is intentionally minimal and geared toward learning and experimentation.

## Contents

- `main.ipynb` — primary notebook that performs chunking, embedding, and saving to Chroma.
- `PridePrejudice.txt` — Project Gutenberg source text used for the demo.
- `pyproject.toml` — dependency and packaging metadata.
- `.gitignore` — patterns to ignore local artifacts.

## Quick start (Windows)

1. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   ```

2. Install the package and dependencies:

   ```bash
   pip install -e .
   ```

3. Launch the notebook and run cells:

   ```bash
   jupyter lab
   # or
   jupyter notebook
   ```

   Open `main.ipynb` and run the notebook cells in order.

## What the notebook does

- Loads `PridePrejudice.txt`.
- Splits the text into overlapping chunks (see `split_into_chunks` in the notebook).
- Instantiates a SentenceTransformers model to produce embeddings (`embedder` / `embed_chunk`).
- Stores embeddings and metadata in a Chroma collection (`save_embeddings`).
- Demonstrates simple retrieval with nearest-neighbor search.

## Configuration & tips

- Embedding model: change the model name in the notebook to try different SentenceTransformers variants.
- Device: the notebook will use CPU by default; enable GPU by configuring PyTorch if available.
- Chroma persistence: the example uses an ephemeral in-memory collection. To persist vectors, update the Chroma client configuration in `main.ipynb` and set a persistent directory.
- Chunking: adjust chunk size and overlap parameters to balance retrieval granularity and index size.

## Notes on the text

`PridePrejudice.txt` includes Project Gutenberg headers and license information. See the top of that file for full attribution and license terms.

## Contributing

Small fixes, improvements to chunking/embedding, or notebook clarifications are welcome. Open an issue or submit a PR.

## License

The demo code is provided under the repository license (see `pyproject.toml`). The included text file is from Project Gutenberg and is subject to its terms (see header in `PridePrejudice.txt`).
