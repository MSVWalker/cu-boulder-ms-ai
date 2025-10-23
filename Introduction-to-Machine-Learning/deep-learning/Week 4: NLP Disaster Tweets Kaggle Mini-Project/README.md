# NLP Disaster Tweets – Week 4 Mini-Project

This folder contains my Coursera Week 4 mini‑project for the Kaggle competition “Real or Not? NLP with Disaster Tweets”. The work is implemented in a single Jupyter notebook that covers exploratory analysis, classic ML (TF‑IDF + Logistic Regression), and simple deep learning baselines (FastText‑style and BiGRU).

## Contents
- `Week 4: NLP Disaster Tweets Kaggle Mini-Project.ipynb` — end‑to‑end notebook with EDA, preprocessing, baselines, model sweeps, and evaluation.

## Dataset
Place Kaggle files in a local `data/` directory at runtime (not committed):
- `data/train.csv`
- `data/test.csv`

The notebook may write cleaned versions (`train_clean.csv`, `test_clean.csv`) into `data/` for convenience. These are derived artifacts and should not be committed.

## How to Run
1. Create and activate a Python 3.10+ environment.
2. Install dependencies (example):
   - numpy, pandas, scikit-learn, matplotlib, seaborn
   - tensorflow (or tensorflow-macos on Apple Silicon), keras
   - nltk
3. Ensure Kaggle CSVs exist under `data/` as listed above.
4. Open the notebook and run cells in order. If NLTK stopwords aren’t present locally, download them once (internet required) or comment out that cell.

## Notes
- The notebook keeps model training deterministic-ish via fixed random seeds and early stopping.
- Large artifacts (trained models, submissions) are intentionally excluded from version control.
- Absolute paths in I/O cells can be switched to relative paths (`data/...`) if running in a different directory layout.

## License
Educational project for coursework; no dataset redistributed. Kaggle data subject to the competition’s terms.

