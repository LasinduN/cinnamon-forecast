# **README.md**

# **Predictive Modeling of Sri Lankan Cinnamon Supply & Demand**

*A Machine Learning and Climate-Integrated Forecasting Project*

This repository contains all code, datasets, documentation, and models developed for a research project on forecasting the supply and demand of Sri Lankan Ceylon cinnamon using machine learning and ensemble learning techniques.
The project integrates **trade data**, **production data**, **climate data**, **Google Trends**, and **market indicators** to build a unified, high-resolution forecasting system.

---

## **1. Research Overview**

Sri Lanka supplies most of the world’s Ceylon cinnamon, but production and pricing are highly sensitive to climate, market competition, and global demand.
This project aims to:

### **Research Objectives**

* Predict **future supply** of Sri Lankan cinnamon using production, exports, climate data, and environmental indicators.
* Predict **global demand** using import data, Google Trends, and market activity in key importing countries.
* Build a **hybrid stacking ensemble** combining ARIMA, Random Forest, XGBoost, and LSTM.
* Provide a **Decision Support System (DSS)** for farmers, exporters, and policymakers.
* Analyze climate stress, competitor activity, and market shifts.

---

## **2. Key Research Questions**

1. What variables most strongly influence Sri Lanka’s cinnamon supply?
2. How do import trends, consumer interest, and global competition shape demand?
3. Can ensemble models outperform traditional time-series methods?
4. How do climate anomalies (rainfall, temperature, ENSO events) impact supply?
5. Can we build a reliable forecast 3–12 months ahead for export planning?

---

## **3. Methodology Summary**

### **Data Sources**

* **UN Comtrade / WITS** – exports & imports
* **FAOSTAT** – production & yield
* **Sri Lanka Meteorology Dept / NASA POWER / NOAA** – climate variables
* **Google Trends** – consumer interest
* **World Bank / Trading Economics** – prices
* **Sector studies & value-chain reports** – policy & structural information

### **Modeling Techniques**

* **Classical Models**: ARIMA, SARIMA
* **Tree Models**: Random Forest, XGBoost, LightGBM
* **Deep Learning**: LSTM
* **Stacking Ensemble**: Ridge regression meta-learner combining all models
* **Evaluation**: MAE, RMSE, MAPE, walk-forward cross validation

### **Final Output**

* Forecasts for:

  * Supply (production + exports)
  * Demand (imports + interest indicators)
* Driver importance analysis
* Climate-risk scenario modeling
* Graphical decision dashboard

---

## **4. Repository Structure**

```
cinnamon-forecast/
│
├── data/
│   ├── raw/
│   │   ├── supply/       # Exports, production, prices
│   │   ├── demand/       # Imports, Google Trends, market interest
│   │   ├── context/      # Climate, anomalies, shocks
│   │   └── README.md     # Notes on data sources
│   ├── processed/        # Cleaned + merged master datasets
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_training.ipynb
│   └── 04_forecasting.ipynb
│
├── src/
│   ├── data_ingest.py
│   ├── features.py
│   ├── models/
│   │   ├── arima.py
│   │   ├── random_forest.py
│   │   ├── xgboost_model.py
│   │   └── lstm_model.py
│   └── ensemble.py
│
├── results/
│   ├── metrics/
│   ├── plots/
│   └── forecasts/
│
├── docs/
│   ├── research_report/
│   └── presentations/
│
└── README.md
```

---

## **5. How to Run the Project**

### **1. Clone the repository**

```bash
git clone <repo-url>
cd cinnamon-forecast
```

### **2. Install dependencies**

Using virtual environment:

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### **3. Run data ingestion**

```bash
python src/data_ingest.py
```

### **4. Run modeling notebooks**

Open Jupyter Notebook or VSCode.

---

## **6. Naming & Formatting Rules**

### **Every dataset must:**

* Be a **CSV file**
* Start with a `date` column in **YYYY-MM** format
* Use clear units (kg, tonnes, mm, °C, USD)

### **File naming example**

```
sri_lanka_exports.csv
imports_major_markets.csv
climate_monthly_sri_lanka.csv
```

### **Commit message format**

```
add: sri_lanka_exports.csv (Member 1)
```

---

## **7. Final Deliverables**

### **Research Outputs**

* Full research report (PDF)
* Clean master dataset
* Forecasting models + evaluation metrics
* Dashboard for decision support
* Visualizations (trends, drivers, scenarios)

### **Software Outputs**

* Modular Python forecasting pipeline
* Reusable scripts for data ingestion and preprocessing
* Trainable ensemble model
* Prediction export functions

---

## **8. License**

For academic research use only unless otherwise stated.
