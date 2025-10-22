# Logistic Regression Activity: Weather & Climate (Graduate Data Analysis)

This repository contains an **interactive activity** for a graduate-level weather & climate data analysis course.
Students will build a **logistic regression** classifier with `scikit-learn`, then evaluate it with:
- Confusion matrix
- Accuracy, Precision, Recall
- ROC curve (AUC)
- Precision–Recall (PR) curve
- **Threshold tuning** via an interactive slider (using `ipywidgets`)

> **Context**: We simulate a small "weather" dataset (e.g., CAPE, PWAT, wind shear) to predict a binary event (e.g., convective initiation or severe/no severe). You can easily swap in your own dataset.

## Quick Start

### Option A — Conda (recommended)
```bash
mamba env create -f environment.yml
mamba activate logreg-weather
jupyter lab
```
Open `notebooks/LogReg_Weather_Activity.ipynb` and run all cells.

### Option B — pip
```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

## Learning Objectives
By the end of this activity, students will be able to:
1. Formulate a binary classification problem from weather/climate context.
2. Train and interpret a **LogisticRegression** model in `scikit-learn`.
3. Compute and interpret **confusion matrix**, **accuracy**, **precision**, **recall**.
4. Plot and interpret **ROC** and **Precision–Recall** curves.
5. Understand the role of **decision threshold** and trade-offs (precision vs recall).

## Structure
```
logreg_weather_activity/
├── data/                          # (optional) place your CSV here; notebook auto-generates synthetic data by default
├── notebooks/
│   └── LogReg_Weather_Activity.ipynb
├── src/
│   └── utils.py                   # helper functions
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
└── environment.yml
```

## Use Your Own Data
- Put a CSV in `data/your_data.csv` with numeric feature columns and a binary target column (0/1).
- In the notebook, set `USE_SYNTHETIC = False` and update `DATA_PATH`, `FEATURES`, and `TARGET`.

## Suggested Assignment Prompts
- **Q1.** Report accuracy, precision, recall for (i) the default 0.5 threshold and (ii) a threshold chosen to prioritize recall ≥ 0.80. Discuss trade-offs.
- **Q2.** Compare **ROC-AUC** and **PR-AUC**. When is PR-AUC more informative?
- **Q3.** Swap to your own dataset (or NOAA/ERA5 subset) and replicate the workflow. Document differences.
- **Q4.** Add a new feature (e.g., a nonlinear transform or interaction). Does it improve performance? Why?

---

© 2025 Released under the MIT License.
