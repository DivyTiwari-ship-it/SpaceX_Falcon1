# 🚀 SpaceX Falcon 9 Landing Prediction

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![ML](https://img.shields.io/badge/ML-XGBoost-green)
![Accuracy](https://img.shields.io/badge/Accuracy-94%25-brightgreen)
![API](https://img.shields.io/badge/Data-SpaceX%20REST%20API-red)

## 📌 Overview
Predicted whether **Falcon 9's first stage will successfully land**  
using real launch data pulled directly from the **SpaceX REST API**.

Landing prediction matters because SpaceX saves $100M+ per launch  
by reusing the first stage booster — if it lands, it flies again.

---

## 📊 Results

| Model | Accuracy | Fail F1 | Success F1 |
|-------|----------|---------|------------|
| Random Forest | 90% | 0.40 | 0.95 |
| **XGBoost ✅** | **94%** | **0.67** | **0.96** |

**Unseen launches test: 29/31 correct → 93.55%**

---

## 🔧 Feature Engineering

| Feature | Description |
|---------|-------------|
| payload_category | Light / Medium / Heavy / Super Heavy |
| site_success_rate | Historical success rate per launch site |
| orbit_success_rate | Historical success rate per orbit type |
| is_recent | 2018+ launches — SpaceX improved significantly |
| reused | Was the booster previously flown? |
| gridfins | Grid fins deployed for steering? |
| legs | Landing legs deployed? |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/-Python-black?logo=python)
![Pandas](https://img.shields.io/badge/-Pandas-black?logo=pandas)
![XGBoost](https://img.shields.io/badge/-XGBoost-black)
![Scikit-Learn](https://img.shields.io/badge/-ScikitLearn-black?logo=scikit-learn)
![Matplotlib](https://img.shields.io/badge/-Matplotlib-black)
![SMOTE](https://img.shields.io/badge/-SMOTE-black)

---

## 🚀 How to Run

```bash
git clone https://github.com/DivyTiwari-ship-it/SpaceX-Falcon9
pip install -r requirements.txt
jupyter notebook spacex_eda_model.ipynb
```

---

## 💡 Key Learnings
- Real API data pull karna — no Kaggle CSV used
- Imbalanced data (142 success vs 11 fail) — fixed using SMOTE
- XGBoost outperformed RandomForest on both accuracy and Fail F1
- flight_number sabse important feature nikla — SpaceX time ke saath improve hua
- Unseen 31 launches pe 93.55% accuracy — model generalizes well
