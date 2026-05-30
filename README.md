# 🚀 SpaceX Falcon 9 Landing Prediction

## 📓 View Full Notebook
[Open in Kaggle](https://www.kaggle.com/code/divyanshtiwari01/spacex)



![Python](https://img.shields.io/badge/Python-3.8+-blue)
![ML](https://img.shields.io/badge/ML-XGBoost-green)
![Accuracy](https://img.shields.io/badge/Accuracy-94%25-brightgreen)
![API](https://img.shields.io/badge/Data-SpaceX%20REST%20API-red)

## 📌 Overview
Predicted whether **Falcon 9's first stage will successfully land**  
using real launch data pulled directly from the **SpaceX REST API**.

Landing prediction matters because SpaceX saves $100M+ per launch  
by reusing the first stage booster — if it lands, it can fly again.

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
| site_success_rate | Historical success rate for each launch site |
| orbit_success_rate | Historical success rate for each orbit type |
| is_recent | Launches after 2018 — SpaceX reliability improved significantly |
| reused | Whether the booster had flown before |
| gridfins | Whether grid fins were deployed |
| legs | Whether landing legs were deployed |

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
cd SpaceX-Falcon9

pip install -r requirements.txt

jupyter notebook spacex_eda_model.ipynb
```

---

## 💡 Key Learnings
- Pulled real-world launch data directly from the SpaceX REST API instead of using static CSV datasets
- Handled class imbalance (142 successful landings vs 11 failures) using SMOTE
- XGBoost outperformed Random Forest in both overall accuracy and Fail F1 score
- `flight_number` emerged as the most important feature, reflecting SpaceX’s improvement over time
- Achieved 93.55% accuracy on 31 unseen launches, demonstrating strong model generalization

---

## 📈 Future Improvements
- Add weather and wind-speed launch conditions
- Deploy the model using Flask or FastAPI
- Build an interactive Streamlit dashboard
- Train on newer Falcon 9 launches for better real-world performance

---

## 🤝 Contributing
Pull requests are welcome.  
Feel free to fork the project and improve the model or visualization pipeline.

---

## 📜 License
This project is licensed under the MIT License.
