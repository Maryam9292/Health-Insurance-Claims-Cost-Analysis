# Health-Insurance-Claims-Cost-Analysis
A comprehensive project to predict medical insurance claim costs, identify high-risk claimants, and analyze key cost drivers using regression models and feature engineering.

![Machine Learning](https://img.shields.io/badge/-Machine%20Learning-blueviolet)
![Python](https://img.shields.io/badge/Python-3.8%2B-success)
![License](https://img.shields.io/badge/License-MIT-green)

This project analyzes medical insurance claim costs using machine learning to predict expenses, profile high-risk claimants, and identify key cost drivers. Designed for insurers, actuaries, and healthcare analysts.

## Key Features  
- 🧠 **Predictive Modeling**: 5 regression models (Linear, Ridge, Lasso, Random Forest, Gradient Boosting) to forecast claim costs.  
- 🔍 **High-Risk Profiling**: Identifies claimants with top 20% expenses using synthetic pre-existing conditions.  
- 📊 **Feature Engineering**:  
  - BMI categories (Underweight/Healthy/Overweight/Obese)  
  - Age groups (18-30, 31-45, 46-60, 60+)  
  - High-risk flag (smoker + BMI ≥30 + pre-existing condition)  
- 📈 **Visual Analytics**: Correlation heatmaps, feature importance plots, and distribution graphs.  

## Results  
| Model                  | R² Score | 
|------------------------|----------|
| Gradient Boosting      | 0.88     | 
| Random Forest          | 0.87     |  
| Ridge Regression       | 0.85     |  
| **Top Test Performance** |          |
| R²                     | 0.87     |
| MAE                    | $2,450   |  
| RMSE                   | $6,980   |  

**Key Cost Drivers**:  
1. Smoking status  
2. BMI  
3. Age  
4. Pre-existing conditions  

## Dataset  
`insurance.csv` (publicly available) with columns:  
- `age`, `sex`, `bmi`, `children`, `smoker`, `region`, `charges`  
- **Engineered Features**: `pre_existing_condition`, `bmi_category`, `age_group`, `high_risk`  

## Usage  
1. Clone the repo:  
```bash
git clone https://github.com/your-username/insurance-claims-cost-analysis.git
