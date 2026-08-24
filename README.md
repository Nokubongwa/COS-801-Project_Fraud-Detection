# COS-801-Project_Fraud-Detection-under-Extreme-Class-Imbalance
 Deep Learning on Tabular Data for Fraud Detection under Extreme Class Imbalance
Domain: Tabular data and financial technology. Suggested level: introductory to intermediate.

Background
Fraud detection combines two conditions that break naive deep learning practice: fewer than one positive
case in every thousand transactions, and a data-generating process that shifts as fraudsters adapt. Gradient
boosted trees remain a very strong baseline on tabular data, so any claim that a neural architecture is
preferable needs careful support. This project tests that claim honestly and studies the cost-sensitive
threshold decision.
Research questions
RQ10.1 Under what conditions, if any, do tabular neural architectures such as TabNet, FT-Transformer and
SAINT outperform tuned gradient boosted trees on fraud detection?
RQ10.2 How do resampling, focal loss and cost-sensitive learning compare as strategies for extreme class
imbalance, and how does each affect calibration?
RQ10.3 How quickly does model performance decay when evaluated on transactions from a later time period
than the training window?
Datasets
• IEEE-CIS Fraud Detection on Kaggle, roughly 590,000 transactions with rich categorical and temporal
features.
• Credit Card Fraud Detection on Kaggle (mlg-ulb/creditcardfraud), 284,807 transactions with 0.17 percent
positives.
• The PaySim synthetic mobile money dataset on Kaggle, which is useful for mobile money scenarios
relevant to African markets.
Suggested methods and baselines
Establish a tuned LightGBM or XGBoost baseline first. Then evaluate FT-Transformer, TabNet and a simple
embedding-based multilayer perceptron. Use temporal splits rather than random splits so that leakage
through time is impossible.
Evaluation plan
Area under the precision-recall curve, precision at a fixed alert budget, expected monetary cost under an
explicit cost matrix, calibration assessment, and a performance-over-time plot showing decay.
Skills developed: Tabular modelling, imbalanced learning, cost-sensitive evaluation, temporal validation. 
