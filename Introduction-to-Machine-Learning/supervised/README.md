# Bellingham Property Price Prediction (Supervised Learning)

This repository contains a supervised learning project to predict residential property prices in Bellingham, WA. The workflow covers data cleaning, exploratory data analysis (EDA), feature engineering, model training, evaluation, and discussion of insights and limitations.

The project is implemented in a single Jupyter notebook: `Supervised_Learning_Project.ipynb`.

## Contents

- Problem description and business context
- Data understanding and cleaning
- Exploratory data analysis (EDA)
- Feature engineering
- Modeling (Linear Regression, Random Forest, XGBoost)
- Results and diagnostics (R², RMSE, residual analysis, feature importance)
- Discussion, limitations, and next steps

## Data

- Source file: `Bellingham_Property_Database.csv`
- Target variable: MLS Amount (sale price)
- Key features include structural attributes (beds, baths, square footage, year built), categorical attributes, and some engineered features.

Ensure the CSV is present in the repository root (as referenced by the notebook). No external APIs are required.

## Environment Setup

Use Python 3.9+ (3.10 recommended). Create an isolated environment and install required packages:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install numpy pandas scikit-learn xgboost seaborn matplotlib scipy jupyter
```

If you prefer a requirements file, install with:

```bash
pip install -r requirements.txt
```

Note: The notebook imports the following libraries detected from its code: `pandas`, `numpy`, `scipy`, `seaborn`, `matplotlib`, `scikit-learn`, and `xgboost`.

## Running the Notebook

1. Activate your environment.
2. Launch Jupyter and open the project notebook:

```bash
jupyter lab  # or: jupyter notebook
```

3. In Jupyter, open `Supervised_Learning_Project.ipynb` and run cells in order (Kernel → Restart & Run All for a clean run).

## Methodology Overview

- Problem & Metrics: Defines the prediction goal and success criteria (e.g., RMSE, R²), with business motivation and scope.
- Data Cleaning: Assesses schema, handles missing values, removes duplicates, treats outliers (IQR-based methods), and validates post-cleaning structure.
- EDA: Summary statistics, histograms, boxplots, correlation heatmap, grouped price distributions, pairwise relationships with trendlines, and log-transform checks.
- Feature Engineering: Encodes categorical variables and builds additional features intended to improve model performance and interpretability.
- Modeling: Trains baseline and advanced regressors:
  - Linear Regression
  - Random Forest Regressor
  - XGBoost Regressor
  Models are evaluated on held-out data using standard metrics.
- Results & Analysis: Compares model performance, inspects residuals and diagnostics, and reviews feature importance (where applicable).
- Discussion & Conclusions: Summarizes findings, highlights business implications, notes limitations/assumptions, and outlines future work.

## Reproducibility

- Use `train_test_split` with a fixed `random_state` to ensure stable splits across runs.
- For stochastic models (e.g., Random Forest, XGBoost), set seeds where applicable for comparable metrics.
- For clean execution, consider Kernel → Restart & Run All before exporting results.

## Repository Structure

- `Supervised_Learning_Project.ipynb` — main notebook with the complete workflow.
- `Bellingham_Property_Database.csv` — input dataset referenced by the notebook.
- `README_SUPERVISED.md` — this README describing the supervised learning project.



