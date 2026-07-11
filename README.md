# 🚀 PortScan Detection using Machine Learning

> An end-to-end Machine Learning project for detecting Port Scan attacks from network traffic using Logistic Regression and Random Forest.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikitlearn)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Cybersecurity](https://img.shields.io/badge/Cybersecurity-Network%20Security-red)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)

---

## 📖 Overview

Port scanning is one of the first steps attackers perform during the reconnaissance phase of a cyber attack. By probing multiple ports on a target machine, attackers identify running services and potential vulnerabilities.

This project develops a **Machine Learning-based Port Scan Detection System** that classifies network traffic into:

- ✅ Normal Traffic
- 🚨 Port Scan Traffic

Instead of relying on IP or MAC addresses (which can cause data leakage), the model learns **behavioral characteristics** of network flows, making it more generalizable.

---

## ✨ Features

- 📂 Flow-based network traffic analysis
- 🧹 Data preprocessing and cleaning
- 📊 Exploratory Data Analysis (EDA)
- ⚖️ Class balancing using Random Undersampling
- 🤖 Logistic Regression baseline model
- 🌲 Random Forest classifier
- 📈 Cross-validation
- 📉 Confusion Matrix visualization
- 📋 Model comparison and evaluation

---

## 📂 Project Structure

```text
PortScan-Detection-ML/
│
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── normal.pcapng
│   └── scan.pcapng
│
├── notebooks/
│   └── PortScan_Detection.ipynb
│
├── reports/
│   └── PortScan_Detection_Report.pdf
│
├── results/
│   ├── prediction_results.csv
│   ├── class_distribution.png
│   ├── destination_port_distribution.png
│   ├── packet_distribution.png
│   ├── logistic_confusion_matrix.png
│   └── random_forest_confusion_matrix.png
│
└── src/
    ├── preprocess.py
    ├── train.py
    ├── evaluate.py
    └── utils.py
```

---

# 🎯 Problem Statement

Traditional rule-based Intrusion Detection Systems (IDS) struggle to detect evolving attack patterns.

The objective of this project is to investigate whether Machine Learning models can accurately distinguish **normal traffic** from **port scan traffic** using network flow characteristics.

---

# 📊 Dataset

The dataset was generated from **PCAPNG network captures**, which were converted into flow-based CSV records.

Each row represents one bidirectional network flow.

### Target Labels

| Label | Description |
|--------|-------------|
| 0 | Normal Traffic |
| 1 | Port Scan |

---

## 🧹 Data Preprocessing

To prevent **data leakage**, identity-related columns were removed, including:

- IP Address
- MAC Address
- Device ID
- VLAN ID
- Tunnel ID
- Timestamp
- Application Metadata

The model instead learns from behavioral features such as:

- Destination Port
- Protocol
- Flow Duration
- Packet Count
- Byte Count
- Traffic Direction Statistics

---

## 📈 Exploratory Data Analysis

The project includes several visual analyses:

- Class Distribution
- Destination Port Distribution
- Packet Count Distribution
- Flow Statistics
- Traffic Behavior Comparison

---

# 🤖 Machine Learning Pipeline

```text
PCAPNG Files
      │
      ▼
Flow-based CSV
      │
      ▼
Data Cleaning
      │
      ▼
Feature Engineering
      │
      ▼
Class Balancing
      │
      ▼
Train-Test Split
      │
      ▼
Model Training
      ├── Logistic Regression
      └── Random Forest
      │
      ▼
Performance Evaluation
```

---

# 🧠 Models Used

## Logistic Regression

- Baseline classification model
- StandardScaler applied
- Used for comparison

---

## Random Forest

Hyperparameters:

```python
RandomForestClassifier(
    n_estimators=100,
    max_depth=5,
    min_samples_leaf=2,
    random_state=42
)
```

---

# 📊 Results

| Model | Accuracy | Precision | Recall | F1 Score |
|--------|----------|-----------|--------|----------|
| Logistic Regression | 100% | 1.00 | 1.00 | 1.00 |
| Random Forest | **100%** | **1.00** | **1.00** | **1.00** |

### Cross Validation

```
F1 Scores

[1.00, 1.00, 0.9167, 1.00, 1.00]

Mean F1 Score

0.9833
```

---

# 📌 Key Insights

- Identity-related features were removed to avoid data leakage.
- Behavioral network features provided strong predictive capability.
- Random Forest successfully captured nonlinear traffic patterns.
- Cross-validation demonstrated stable model performance.

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---

# 🚀 Getting Started

## Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/PortScan-Detection-ML.git
cd PortScan-Detection-ML
```

---

## Install dependencies

```bash
pip install -r requirements.txt
```

---

## Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```
notebooks/PortScan_Detection.ipynb
```

---

# 📷 Results

> Add screenshots here after uploading them.

### Class Distribution

```
results/class_distribution.png
```

---

### Destination Port Distribution

```
results/destination_port_distribution.png
```

---

### Confusion Matrix

```
results/random_forest_confusion_matrix.png
```

---

# 📌 Future Improvements

- Deep Learning based Intrusion Detection
- XGBoost / LightGBM models
- Real-time packet capture using Scapy
- Explainable AI (SHAP/LIME)
- FastAPI deployment
- Streamlit Dashboard
- Evaluation on larger public datasets (CICIDS2017, UNSW-NB15)

---

# 📚 Learning Outcomes

This project demonstrates:

- Data Cleaning
- Feature Engineering
- Exploratory Data Analysis
- Classification Algorithms
- Model Evaluation
- Cross Validation
- Network Traffic Analysis
- Cybersecurity Fundamentals

---

# 📄 Project Report

A detailed technical report explaining the methodology, preprocessing, experiments, and evaluation is available in:

```
reports/PortScan_Detection_Report.pdf
```

---

# 👨‍💻 Author

**Pedapati Sujith**

🎓 B.Tech in Electronics & Communication Engineering  
🏛️ IIITDM Kurnool

- 🔬 Research Intern @ NIT Kurukshetra
- 🤖 AI | Machine Learning | Computer Vision | Cybersecurity
- 🌐 LinkedIn: https://linkedin.com/in/YOUR_LINKEDIN
- 💻 GitHub: https://github.com/YOUR_GITHUB

---

## ⭐ If you found this project helpful, consider giving it a Star!

It motivates me to build and share more Machine Learning and AI projects.