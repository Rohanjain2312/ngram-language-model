# N-Gram Language Model — Predicting Words the Classical Way

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![NLP](https://img.shields.io/badge/NLP-N--Gram%20Modeling-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Focus](https://img.shields.io/badge/Focus-Laplace%20%26%20Backoff%20Smoothing-lightgrey)

---

### Project Summary
This project implements a **statistical N-Gram Language Model** from scratch — a foundational concept in Natural Language Processing that predicts the next word in a sequence based on the previous words.  
It explores how different model orders and smoothing strategies affect language modeling performance.

Key components include:
- **Unigram, Bigram, Trigram, and 4-Gram** models  
- **Laplace (Add-1) smoothing**, **Interpolated smoothing**, and **Backoff** techniques  
- **Perplexity evaluation** to measure how well each model predicts unseen text  

The notebook provides step-by-step explanations, probability derivations, and visual comparisons to illustrate the trade-off between model complexity and generalization.

---

### Outcome Summary
The results clearly demonstrate the limitations of higher-order MLE models due to data sparsity, and the effectiveness of smoothing and backoff methods in improving performance.

| Model | Technique | Test Perplexity | Observation |
|:------|:-----------|----------------:|:-------------|
| Unigram (MLE) | Maximum Likelihood | 771.16 | Captures word frequency only |
| Bigram (MLE) | Maximum Likelihood | ∞ | Fails due to unseen bigrams |
| Trigram (MLE) | Maximum Likelihood | ∞ | Severe sparsity issue |
| 4-gram (MLE) | Maximum Likelihood | ∞ | Even higher sparsity |
| Trigram (Laplace) | Add-1 Smoothing | 2575.20 | Over-smooths, poor generalization |
| Trigram (Interpolated, λ=(0.33, 0.33, 0.34)) | Linear Interpolation | 151.16 | Balanced context weighting |
| Trigram (Backoff, α=0.9) | Katz Backoff | **80.39** | Best overall performance |

These results highlight how **probabilistic backoff** and **weighted interpolation** significantly reduce perplexity, producing smoother and more reliable predictions compared to raw frequency counts.


### Key Takeaway
This project shows how early statistical models learned to predict language using simple probability rules — long before neural networks and transformers.  
It connects historical NLP foundations to modern generative models, bridging the gap between **count-based learning** and **context-based reasoning**.

## Repo structure
```
ngram-language-model/
├── ptbdataset/
├── NGramModels.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

## Data
Source: https://www.kaggle.com/datasets/aliakay8/penn-treebank-dataset

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
3. Put your corpus files into `ptbdataset/` (or update paths in the notebook).
4. Open `NGramModels.ipynb` and run all cells.

## Author

**Rohan Jain**
- GitHub: [@Rohanjain2312](https://github.com/Rohanjain2312)
- LinkedIn: [Profile](https://www.linkedin.com/in/jaroh23/)
- Email: rohanjain2312@gmail.com


## AI Assistance Disclosure

This project was primarily developed and implemented by me.
AI tool - Claude 3.5 Sonnet (Anthropic) were used selectively to refine code structure, improve documentation clarity, and support performance analysis.

All model design decisions, experiments, and final evaluations were independently executed and validated by the author.
AI was used only as a supplementary aid to enhance learning and efficiency, not as a replacement for human understanding or work.