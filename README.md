# 🌐 Global Supply Chain Risk Prediction — 2026

> **Predict shipment disruptions across global trade lanes using machine learning.**

---

## 📋 Project Description

This project builds a complete machine learning pipeline to predict whether a shipment will experience a **supply chain disruption** (`Disruption_Occurred = 1`). Using 5,000 historical shipment records across major global ports, transport modes, and product categories, the project delivers:

- Comprehensive **Exploratory Data Analysis (EDA)** with 10 visualisations
- **Feature Engineering** — temporal, interaction, and inverse-reliability features
- Training and evaluation of **5 classification models** (Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, XGBoost)
- **Feature importance** analysis to identify the top disruption drivers
- **High-risk route profiling** for logistics decision-making

**Best Model:** XGBoost — ~87% Accuracy | ROC-AUC ~0.94 | F1-Score ~0.88

---

## 📂 Project Structure

```
GlobalSupplyChainRisk_Project/
├── app.py                                    # Standalone Python script
├── GlobalSupplyChainRisk.ipynb               # Main Jupyter Notebook (EDA + ML)
├── ProjectReport.docx                        # Full project report (Word)
├── requirements.txt                          # Python dependencies
├── README.md                                 # This file
└── *.png                                     # Generated chart screenshots
```

---

## 📊 Dataset

| Field | Value |
|-------|-------|
| **File** | `global_supply_chain_risk_2026.csv` |
| **Records** | 5,000 shipments |
| **Features** | 14 (13 inputs + 1 target) |
| **Target** | `Disruption_Occurred` (binary: 0 / 1) |
| **Date Range** | 2024 – 2026 |
| **Source** | [Kaggle — Global Supply Chain Risk 2026](https://www.kaggle.com/) |

---

## 🖼️ Screenshots & Visualisations

### 1. Disruption Class Distribution
![Disruption Distribution]
> Bar chart and pie chart showing the balance between disrupted (1) and non-disrupted (0) shipments across the full dataset.

---

### 2. Disruption Rate by Categorical Features
![Categorical Disruption Rates]
> Disruption rate breakdown across Origin Port, Destination Port, Transport Mode, Product Category, and Weather Condition.

---

### 3. Numerical Feature Distributions
![Numerical Distributions]
> Histogram + KDE overlays for Distance, Weight, Fuel Price Index, Geopolitical Risk Score, Carrier Reliability, and Lead Time — split by disruption class.

---

### 4. Correlation Heatmap
![Correlation Heatmap]
> Pairwise Pearson correlations between all numerical features and the target variable. Helps identify multicollinearity and key predictors.

---

### 5. Transport Mode vs Disruption
![Transport Mode Disruption]
> Stacked bar chart showing the percentage of disrupted vs non-disrupted shipments for each transport mode (Air, Rail, Road, Sea).

---

### 6. Monthly Disruption Trend
![Monthly Disruption Trend]
> Time-series line chart of monthly disruption rates from 2024 to 2026, highlighting seasonal peaks (Q3: July–September).

---

### 7. Model Performance Comparison
![Model Comparison]
> Grouped bar chart comparing Accuracy, Precision, Recall, F1-Score, and ROC-AUC across all five trained models.

---

### 8. ROC Curves — All Models
![ROC Curves]
> Receiver Operating Characteristic curves for all five models, with AUC scores. XGBoost achieves the highest AUC (~0.94).

---

### 9. Confusion Matrix — XGBoost
![Confusion Matrix XGBoost]
> Confusion matrix for the best model (XGBoost), showing True Positives, True Negatives, False Positives, and False Negatives on the test set.

---

### 10. Feature Importance — XGBoost
![Feature Importance]
> Top 15 most important features ranked by XGBoost gain-based importance. Carrier Reliability Score and Geopolitical Risk Score are the dominant predictors.

---

## 🛠️ Technologies Used

| Technology | Version | Purpose |
|------------|---------|---------|
| Python | 3.10+ | Core language |
| pandas | ≥ 2.0.0 | Data manipulation |
| NumPy | ≥ 1.24.0 | Numerical computing |
| Matplotlib | ≥ 3.7.0 | Visualisation |
| Seaborn | ≥ 0.12.0 | Statistical plots |
| scikit-learn | ≥ 1.3.0 | ML models & evaluation |
| XGBoost | ≥ 1.7.0 | Best-performing classifier |
| joblib | ≥ 1.3.0 | Model serialisation |
| Jupyter Notebook | ≥ 7.0.0 | Interactive execution |

---

## ⚙️ Setup & Run Instructions

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Update dataset path
In `app.py` or Cell 2 of the notebook, set:
```python
DATA_PATH = r'C:\path\to\global_supply_chain_risk_2026.csv'
```

### 3a. Run as Jupyter Notebook
```bash
jupyter notebook GlobalSupplyChainRisk.ipynb
```
Use **Kernel → Restart & Run All**

### 3b. Run as Python script
```bash
python app.py
```

---

## 📈 Key Results

| Model | Accuracy | ROC-AUC |
|-------|----------|---------|
| Logistic Regression | ~74% | ~0.82 |
| Decision Tree | ~79% | ~0.79 |
| Random Forest | ~85% | ~0.92 |
| Gradient Boosting | ~86% | ~0.93 |
| **XGBoost** | **~87%** | **~0.94** |

**Top 5 Disruption Predictors (XGBoost):**
1. `Carrier_Reliability_Score`
2. `Geopolitical_Risk_Score`
3. `Risk_x_Distance` *(engineered feature)*
4. `Lead_Time_Days`
5. `Fuel_Price_Index`

---

## 👤 Author

**Vinay Naikv**  
Project: Global Supply Chain Risk Prediction  
Dataset: `global_supply_chain_risk_2026.csv`

---
