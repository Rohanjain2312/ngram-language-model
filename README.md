# N‑Gram Language Modeling (with Smoothing & Backoff)

This repository contains a clean, reproducible implementation of **n‑gram language models** with **Laplace smoothing**, **interpolation/backoff**, and **perplexity evaluation**. It is based on the course work for a graduate‑level NLP class and demonstrates classic statistical NLP techniques with clear code and explanations.

## What’s inside
- Unigram, Bigram, Trigram (optionally 4‑gram) models
- Laplace/add‑1 smoothing and interpolated backoff
- Perplexity evaluation on validation/test sets
- Basic text generation demo from the best model

## Repo structure
```
ngram-language-model/
├── data/                 # Put corpus files here (see 'Data' below)
├── notebooks/
│   └── NGramModels.ipynb # Place your notebook here
├── src/                  # (Optional) Python modules if you factor code out of the notebook
├── reports/              # Saved charts/tables (optional)
├── requirements.txt
├── LICENSE
└── README.md
```

> **Note:** Copy your existing `NGramModels.ipynb` into `notebooks/` before committing.

## Data
The notebook currently expects the **Penn Treebank (PTB)**‑style files:
```
ptbdataset/ptb.train.txt
ptbdataset/ptb.valid.txt
ptbdataset/ptb.test.txt
```


## Reproducibility
- Set a random seed at the top of the notebook for any sampling/generation.
- Capture the package versions with `pip freeze > reports/requirements.freeze.txt` after a successful run.
- Avoid hard‑coded absolute paths; use project‑relative paths (`os.path.join(...)`).

## Quickstart
1. Create and activate a virtual environment.
2. `pip install -r requirements.txt`
3. Put your corpus files into `data/` (or update paths in the notebook).
4. Open `notebooks/NGramModels.ipynb` and run all cells.
5. Export results (perplexities, plots) into `reports/` for the README badges/table.