# COS 801 Project: Deep Learning on Tabular Data for Fraud Detection Under Extreme Class Imbalance

## Background

Fraud detection presents two major challenges that make it difficult for traditional deep learning approaches:

1. Extreme class imbalance, where fraudulent transactions may account for fewer than one positive case per thousand transactions.
2. Concept drift, where fraud patterns change over time as fraudsters adapt their behavior.

Gradient Boosted Trees (GBTs) remain a strong benchmark for tabular data. Therefore, any claim that deep learning architectures outperform GBTs must be supported through careful experimental evaluation.

This project investigates whether modern deep learning architectures for tabular data can outperform traditional machine learning methods in fraud detection while accounting for extreme class imbalance and temporal changes in fraud patterns.

---

## Research Questions

### RQ10.1
Under what conditions, if any, do tabular neural architectures such as **TabNet**, **FT-Transformer**, and **SAINT** outperform tuned Gradient Boosted Trees on fraud detection tasks?

### RQ10.2
How do **resampling**, **focal loss**, and **cost-sensitive learning** compare as strategies for handling extreme class imbalance, and how does each method affect model calibration?

### RQ10.3
How quickly does model performance degrade when evaluated on transaction data collected after the training period?

---

## Datasets

This project will investigate the following dataset:

### IEEE-CIS Fraud Detection
- Source: Kaggle
- Approximately 590,000 transactions
- Rich categorical, transactional, and temporal features
- Primary dataset for this project

Dataset URL:

https://www.kaggle.com/competitions/ieee-fraud-detection

---

## Suggested Methods and Baselines

The project follows a baseline-first approach.

### Traditional Machine Learning Baselines
- LightGBM
- XGBoost

### Deep Learning Models
- FT-Transformer
- TabNet
- Embedding-based Multi-Layer Perceptron (MLP)
- SAINT

### Data Splitting Strategy

Temporal splits will be used instead of random train-test splits to prevent data leakage and simulate real-world fraud detection scenarios.

---

## Evaluation Plan

Models will be evaluated using:

- Precision-Recall AUC (PR-AUC)
- Precision at a fixed alert budget
- Expected monetary cost using a cost matrix
- Calibration analysis
- Performance-over-time decay plots

---

## Skills Developed

- Tabular Data Modelling
- Imbalanced Learning
- Cost-Sensitive Evaluation
- Temporal Validation
- Model Calibration
- Fraud Analytics

---

## Project Structure

```text
COS-801-Project_Fraud-Detection/
│
├── data/
│   ├── raw/
│   └── transformed/
│
├── notebooks/
│
├── src/
│
├── models/
│
├── outputs/
│
├── reports/
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Dataset Setup

The datasets are not stored in this repository because they exceed GitHub's file size limits.

### Download IEEE-CIS Fraud Detection

Authenticate with Kaggle:

```bash
py -m kaggle auth login
```

Download the dataset:

```bash
py -m kaggle competitions download -c ieee-fraud-detection
```

Extract the downloaded archive and place the files in:

```text
data/raw/
```

Expected files:

```text
data/raw/
├── train_transaction.csv
├── train_identity.csv
├── test_transaction.csv
├── test_identity.csv
└── sample_submission.csv
```

---

## Running the Project

Run exploratory analysis:

```bash
python src/eda.py
```

Run model training:

```bash
python src/train.py
```

---

## Current Project Status

- [x] Project selected
- [x] Kaggle access configured
- [x] IEEE-CIS dataset downloaded
- [ ] Data exploration
- [ ] Data preprocessing pipeline
- [ ] LightGBM baseline
- [ ] Deep learning models
- [ ] Calibration analysis
- [ ] Temporal drift evaluation
- [ ] Final report