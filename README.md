# 📊 Hotel Demand Forecasting Project

## 📌 Overview
This project forecasts daily hotel room demand using a 28-day forecast horizon. The goal is to compare multiple forecasting approaches—including statistical, machine learning, and neural models—and evaluate their performance across multiple hotel time series.

---

## 📂 Dataset
- Source: `sample_hotels.parquet`
- Time range: January 2022 – June 2023  
- Number of hotel series: 18  
- Frequency: Daily  
- Target variable: Normalized room demand (`y`)

---

## ⚙️ Models Used
The project compares a diverse set of forecasting models:

### Statistical Models
- Naive  
- Seasonal Naive  
- AutoARIMA  
- AutoETS  

### Machine Learning Model
- LightGBM (via MLForecast)

### Neural Forecasting Models
- NBEATS  
- NHITS  

---

## 🔁 Evaluation Method
The project uses **5-fold time-series cross-validation** with a rolling forecasting origin.

Each model is evaluated using the following metrics:
- **ME** (Mean Error)  
- **MAE** (Mean Absolute Error)  
- **RMSE** (Root Mean Squared Error)  
- **MAPE** (Mean Absolute Percentage Error)  

Evaluation is performed:
- Per hotel (individual time series)
- Overall (average across all hotels)

---

## 📊 Key Results
- **NHITS** was the best overall model based on lowest average MAE  
- Neural and machine learning models performed best on more complex demand patterns  
- Statistical models (AutoARIMA, AutoETS) remained competitive on stable series  
- No single model dominated all hotels, highlighting the importance of model comparison  

---

## 🏆 Model Win Counts
The project includes a model win-count analysis, showing how often each model achieved the lowest error across hotels for each metric.

---

## 📁 Project 

---

## 📈 Example Forecast

![Forecast](plots/hotel_0_forecast.png)

---

## 🧠 Main Findings
The strongest overall model based on 5-fold time-series cross-validation was **NHITS**, which achieved the lowest average MAE across hotel series. Model performance varied across hotels, indicating that no single approach consistently outperformed others. Neural and machine learning models were better at capturing complex demand patterns, while simpler statistical models performed well on more stable series. These results support using multiple models and evaluating performance at the individual series level.

---

## ⚠️ Foundation Model Note
A foundation model (Chronos) was considered for this project. However, it was not included in the final implementation due to dependency conflicts in Google Colab. The final submission fully satisfies the project requirements by including statistical, machine learning, and neural models with complete 5-fold time-series cross-validation and evaluation.

---

## ▶️ How to Run
1. Open the notebook in **Google Colab**
2. Upload `sample_hotels.parquet`
3. Run all cells
4. Outputs (CSV files and plots) will be generated automatically

---

## 👤 Author
**Joseph Lubertozzi**
