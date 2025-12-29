# Energy Demand Forecasting Across Domains

Capstone project exploring **energy demand forecasting using machine learning**, with a focus on  
**domain generalization**, **domain adaptation**, and **global vs specialized models**.

This project goes beyond achieving high accuracy on a single dataset and instead investigates a
critical real-world question:

> **Can an energy demand forecasting model trained in one domain generalize to another?**

---

## 📄 Project Report (Start Here)

The complete technical report, including methodology, experiments, plots, and analysis, is available here:

➡️ **[Full Project Report (Jupyter Notebook)](notebooks/project_report.ipynb)**

The report documents:
- Data preprocessing and feature engineering
- Baseline, machine learning, deep learning, and ensemble models
- Cross-domain generalization failure
- Domain adaptation via retraining
- Global multi-domain modeling and trade-offs

---

## 🔍 Executive Summary

- A LightGBM model achieves **strong performance on city-level electricity demand (Delhi)**.
- The same trained model **fails catastrophically on residential demand (Pecan Street)** due to domain shift.
- Retraining the same architecture on residential data **restores performance**, confirming the failure was domain-related.
- A global model trained on both domains improves robustness but **sacrifices local accuracy**, especially for residential demand.

**Key conclusion:**  
Energy demand forecasting models are **domain-specific**, and high local accuracy does not imply generalization.

---

## 📊 Datasets

### 1. Delhi Electricity Demand
- City-level electricity demand
- 5-minute resolution (aggregated to hourly)
- Includes weather and temporal features
- Smooth, low-variance demand patterns

### 2. Pecan Street Residential Electricity Data
- Household-level electricity consumption
- 1-minute resolution (aggregated to hourly)
- No weather features
- Highly variable, behavior-driven demand

⚠️ **Raw datasets are not included** due to licensing and size constraints.

---

## 📥 Data Availability & Setup

Raw data must be obtained from the original sources:

- **Delhi Electricity Demand**: Kaggle(https://www.kaggle.com/datasets/yug201/delhi-5-minute-electricity-demand-for-forecasting)
- **Pecan Street Residential Data**: Kaggle (https://www.kaggle.com/datasets/zhitingzheng/pecan-street-electricity-data)

### To run locally:
1. Download raw datasets from the sources above
2. Place them in a local `data/` directory (ignored by Git)
3. Run notebooks sequentially from `01_` to `09_`
4. Processed datasets will be generated in the `results/` directory

---

## 🧠 Modeling Workflow

The project follows a structured experimental pipeline:

1. Data understanding and cleaning  
2. Feature engineering and time-aware splitting  
3. Baseline forecasting models (Naive, Seasonal Naive, Prophet)  
4. Machine learning model (LightGBM)  
5. Deep learning comparison (LSTM)  
6. Ensemble modeling  
7. Cross-dataset testing (generalization failure)  
8. Domain adaptation via retraining  
9. Global multi-domain model and trade-off analysis  

---

## 📈 Key Results

| Scenario | Outcome |
|--------|--------|
| LightGBM on Delhi | Excellent accuracy |
| Delhi model on residential data | Severe failure |
| Residential retraining | Performance restored |
| Global model | Robust but less accurate |

---

## 🧩 Key Insights

- Energy demand forecasting is **highly domain-dependent**
- Tree-based models outperform deep learning for structured energy time series
- Cross-domain generalization fails without adaptation
- Retraining is essential when moving across demand regimes
- Global models trade local optimality for robustness

---

## 📂 Repository Structure

- notebooks/ → All Jupyter notebooks(01–09 with including project report).
- models/ → Trained model artifacts.
- models/ → Trained model artifacts.
- data/ → Dataset documentation only.

---

## 🚀 Technologies Used

- Python
- Pandas, NumPy
- LightGBM
- Scikit-learn
- Prophet
- TensorFlow (LSTM)
- Matplotlib / Seaborn
- Git & Git LFS

---

## ▶️ How to Run

```bash
pip install -r requirements.txt