🚨 Real-Time Financial Fraud Detection using Anomaly Detection
📌 Project Overview

This project implements an industry-grade real-time financial fraud detection system using a hybrid anomaly detection approach.
Instead of relying on a single classifier, the system combines multiple complementary models to assign a risk score to each transaction and make business-aware decisions.

The pipeline is designed to closely mirror how banks and fintech companies detect fraud in production.

🎯 Problem Statement

Financial fraud detection is challenging because:

Fraud cases are extremely rare (<1%)

Fraud patterns evolve over time

Wrong decisions lead to:

Financial loss (false negatives)

Customer dissatisfaction (false positives)

The goal is to:

Identify high-risk transactions in near real-time while minimizing customer friction.

🧠 Solution Approach

Instead of binary fraud classification, this system:

Detects anomalous behavior

Assigns a continuous risk score

Converts risk into business actions

🔹 Models Used
Model	Purpose
Isolation Forest	Detects globally rare transactions
Autoencoder	Detects behavioral deviation from normal spending
LSTM	Learns temporal fraud patterns from transaction sequences

Each model contributes a risk signal, which is fused into a final score.

🧱 System Architecture
Raw Transactions
      ↓
Feature Engineering
      ↓
Isolation Forest  → Global Anomaly Score
Autoencoder       → Behavioral Anomaly Score
LSTM              → Temporal Fraud Probability
      ↓
Risk Score Fusion
      ↓
ALLOW / VERIFY / BLOCK

📂 Datasets Used

fraudTrain.csv – Historical transaction data (model training)

fraudTest.csv – Future unseen transactions (real-time simulation)

Each transaction includes:

Transaction amount

Merchant category

Location (customer & merchant)

Timestamp

Fraud label (is_fraud)

⚠️ Fraud labels are used only for evaluation, not during inference.

🔧 Feature Engineering Highlights

Log-transformed transaction amount

Time-based features (hour, day, night indicator)

Location-aware features

Carefully selected categorical encodings

Removal of identifiers and PII to prevent leakage

🔢 Risk Scoring Strategy

Each model output is normalized and combined:

Risk Score =
0.40 × Isolation Forest
0.35 × Autoencoder
0.25 × LSTM

🚦 Decision Logic
Risk Score Range	Action
< 0.30	ALLOW
0.30 – 0.60	VERIFY (OTP / 2FA)
> 0.60	BLOCK

This mirrors real banking decision systems.

📊 Model Performance
🔹 Ranking Metrics

ROC-AUC: 0.85

PR-AUC: 0.03 (expected due to extreme class imbalance)

🔹 Operational Metric

Precision @ Top 1% Risk: 4.23%

This is ~8× better than random selection, demonstrating strong concentration of fraud in the highest-risk segment.

🧠 Key Insights

High ROC-AUC confirms strong fraud ranking capability

Low PR-AUC is expected in highly imbalanced fraud datasets

Precision@Top-K is the most meaningful real-world metric

Anomaly detection is effective when fraud labels are scarce

🛠 Tech Stack

Language: Python

ML: scikit-learn

Deep Learning: TensorFlow / Keras

Data Handling: Pandas, NumPy

Visualization: Matplotlib

🚀 Future Improvements

Per-card rolling behavioral features

Dynamic threshold optimization

Cost-sensitive risk scoring

Real-time deployment using FastAPI

Streaming ingestion (Kafka / REST)
