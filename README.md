# 🚗 Car Price Prediction Model  

This repository contains a Machine Learning project for predicting **used car prices** using structured data. The project demonstrates not only model training but also a **full evaluation pipeline**, including hyperparameter tuning, bias–variance diagnostics, residual/error analysis, segmentation and robustness testing. 

---

## 📂 Project Structure  

├── data/  Dataset 

├── notebooks/ Jupyter notebook with EDA, preprocessing, and modeling

└── README.md  Project documentation


## ⚙️ Tech Stack  

- **Language:** Python 3.11  
- **Libraries:** pandas, numpy, scikit-learn, matplotlib, seaborn, XGBoost  
- **Environment:** Poetry for dependency management  


## 🔬 Project Workflow  

1. **Data Preprocessing**  
   - Handling missing values  
   - Feature engineering (log-transform target with `log1p`)  
   - Encoding categorical variables  
   - Scaling numeric features  

2. **Exploratory Data Analysis (EDA)**  
   - Visualizations (distribution plots, correlation heatmaps)  
   - Outlier detection and removal  
   - Feature-target relationship analysis  

3. **Modeling**  
   - Base models tested:  Random Forest, XGBoost  
   - Hyperparameter tuning via **GridSearchCV**  
   - Cross-validation to ensure stable performance  

4. **Model Evaluation**  
   - Metrics:  
     - **MAE** (Mean Absolute Error) → interpretable error in currency  
     - **RMSE** (Root Mean Squared Error) → penalizes large errors  
     - **R² Score** → proportion of variance explained  
   - Example results after reversing log-transform:  
     ```
     XGB MAE : 82,865  
     XGB RMSE : 171,083  
     XGB R²   : 0.90
     ```

5. **Bias–Variance Diagnosis**  
   - Learning curves to understand underfitting vs. overfitting  
   - Fine-tuned regularization parameters to balance bias/variance  

6. **Residual & Error Analysis**  
   - Plots of residuals vs. predictions to detect bias patterns  
   - Error segmentation by fuel type 

7. **Robustness & Stress Testing**  
   - Injected Gaussian noise into numeric features to test model stability  
   - Results: error only increased slightly, showing **robustness to perturbations**  

## 📊 Key Insights  

- XGBoost achieved the best balance between bias and variance.  
- The model is **robust to small noise**, meaning it can generalize well to slightly imperfect inputs.  
- Errors are not uniform: Diesel cars showed higher MAE compared to Petrol, revealing a possible **data imbalance**.  
- Residual analysis confirmed no major systematic bias.  

## 🚀 How to Run  

1. Clone this repository:  
   ```bash
   git clone https://github.com/Maxwell-Selassie/car-price-prediction-model.git
   cd car-price-prediction
