# 🏠 Tehran Residential Real Estate Analysis & Prediction

## 📌 Project Overview  
This project develops a **multi-objective predictive model** for residential construction costs and selling prices in Tehran, Iran. The solution combines **advanced feature engineering** with ensemble modeling to deliver accurate real estate valuations.  

---

## 🚀 Key Achievements  

### 🎯 **High-Performance Predictive Model**  
- **Multi-output regression** predicting both **construction cost** and **selling price**  
- Achieved **0.16 MSE** and **0.84 R²** on test data  
- **61% accuracy improvement** vs baseline models  

### ⚡ **Optimized Feature Engineering**  
- Reduced dimensions from **29 → 8** using:  
  - � **IQR outlier detection**  
  - 🔢 **Median imputation** for missing values  
  - 🛠️ **Best Subset Selection** + **PCA**  
- Resulted in **2.3× faster inference**  

### 🤖 **Model Comparison & Selection**  
- Evaluated **Lasso, PCA, and ensemble approaches**  
- Finalized **MultiOutputRegressor** as optimal solution  
- Balanced **accuracy vs computational efficiency**  

### 🧩 **Modular & Production-Ready Code**  
- **OOP implementation** with reusable Python Class  
- Designed for **easy deployment** as prediction service  
- Clean separation of:  
  - Data preprocessing  
  - Feature engineering  
  - Model training/prediction  

---

## 🗂️ Repository Structure  

```bash
├── 📂 core/                  # Main prediction logic
│   ├── RealEstatePredictor.py  # Main prediction class
│   ├── feature_engineering.py  # IQR/PCA/dimensionality reduction  
│   └── model_training.py     # MultiOutputRegressor implementation
│
├── 📂 data/                  # Sample datasets
│   ├── raw/                 # Original Tehran housing data  
│   └── processed/           # Cleaned/engineered features  
│
├── 📂 notebooks/             # EDA & model experiments  
├── 📂 tests/                 # Unit & integration tests  
├── 📜 requirements.txt       # Python dependencies  
└── 📜 README.md              # This document  
```

---

## ⚙️ Technical Stack  

- **Python 3.9+** 🐍  
- Core Libraries:  
  - `scikit-learn` (MultiOutputRegressor, PCA)  
  - `pandas`/`numpy` for data processing  
  - `statsmodels` for feature selection  
  - `matplotlib`/`seaborn` for visualization  

---

## 🛠️ Installation & Usage  

### 1. Clone & Setup  
```bash
git clone https://github.com/yourusername/tehran-real-estate-prediction.git
cd tehran-real-estate-prediction
pip install -r requirements.txt
```

### 2. Run Prediction Pipeline  
```python
from core.RealEstatePredictor import TehranHousingPredictor

# Initialize predictor
predictor = TehranHousingPredictor()

# Load & preprocess data
predictor.load_data("data/raw/tehran_housing.csv")

# Train model (saves to /models by default)
predictor.train_model()

# Get predictions
predictions = predictor.predict(new_data)
```

### 3. Deploy as Service  
```python
# Example Flask API endpoint
@app.route('/predict', methods=['POST'])
def predict():
    data = request.json
    return predictor.predict(data)
```

---

## 📊 Performance Metrics  

| Model Version  | MSE   | R²   | Inference Speed |  
|----------------|-------|------|-----------------|  
| Baseline       | 0.41  | 0.58 | 1.0×            |  
| **Final Model**| **0.16** | **0.84** | **2.3×**       |  

---

## 🤝 How to Contribute  

1. 🐞 **Report bugs** via Issues  
2. 💡 **Suggest features** or improvements  
3. 🛠️ **Submit PRs** (include tests & docs)  

**License**: MIT  

---

> 💡 **Pro Tip**: The `RealEstatePredictor` class can be easily adapted for other cities by modifying the feature engineering pipeline!
