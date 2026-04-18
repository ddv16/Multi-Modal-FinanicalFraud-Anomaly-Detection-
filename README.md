# 💳 Multi-Modal Financial Anomaly Detection with Genetic Algorithm Optimization

An advanced AI-powered fraud detection system that combines **Machine Learning**, **Deep Learning**, **Sequential Pattern Analysis**, and **Genetic Algorithm Optimization** to detect suspicious financial transactions in real time.

This project uses a **multi-modal hybrid detection framework** integrating **Isolation Forest**, **Autoencoder**, **LSTM**, and a **Genetic Algorithm (GA)** to optimize ensemble model weights for maximum fraud detection performance.

---

# 📌 Project Overview

Financial fraud systems often struggle because one single model cannot capture all fraud patterns.

This project solves that problem by:

- Detecting global anomalies
- Detecting behavioral deviations
- Detecting sequence-based fraud patterns
- Optimizing model contribution weights using **Genetic Algorithm**

The final system intelligently combines all models to generate accurate fraud risk scores.

---

# 🚀 Key Features

✅ Multi-model fraud detection system  
✅ Genetic Algorithm optimized ensemble weights  
✅ Reduced false positives  
✅ Real-time fraud scoring  
✅ Adaptive learning architecture  
✅ High scalability for banking systems  
✅ Intelligent ALLOW / VERIFY / BLOCK engine  

---

# 🧠 Models Used

## 1️⃣ Isolation Forest
Detects outlier transactions.

## 2️⃣ Autoencoder
Detects abnormal reconstruction errors.

## 3️⃣ LSTM
Learns sequential transaction behavior.

## 4️⃣ Genetic Algorithm
Optimizes weight distribution among all models to maximize fraud detection performance.

---

# 🧬 Genetic Algorithm Optimization

Instead of manually assigning weights to each model, a **Genetic Algorithm** was used to automatically search for the best ensemble combination.

### Optimized Ensemble Formula

```text id="r6v4f2"
Final Score =
(W1 × Isolation Forest Score) +
(W2 × Autoencoder Score) +
(W3 × LSTM Score)
