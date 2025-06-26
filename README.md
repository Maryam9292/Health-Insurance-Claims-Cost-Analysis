# Health-Insurance-Claims-Cost-Analysis
This project analyzes medical insurance claim costs using machine learning to predict expenses, profile high-risk claimants, and identify key cost drivers. The insights are visualized in an interactive Power BI dashboard for business intelligence. Designed for insurers, actuaries, and healthcare analysts.

![Python](https://img.shields.io/badge/Python-3.8%2B-success)
![Power BI](https://img.shields.io/badge/Power_BI-FFC000?style=flat&logo=powerbi&logoColor=white)
![Machine Learning](https://img.shields.io/badge/-Machine%20Learning-blueviolet)


## Key Features  
- 🧠 **Predictive Modeling**: 5 regression models (Linear, Ridge, Lasso, Random Forest, Gradient Boosting) to forecast claim costs  
- 📊 **Power BI Dashboard**: Interactive visualizations of high-risk profiles and cost drivers
- 🔍 **High-Risk Profiling**: Identifies claimants with top 20% expenses using synthetic pre-existing conditions  
- ⚙️ **Feature Engineering**:  
  - BMI categories (Underweight/Healthy/Overweight/Obese)  
  - Age groups (18-30, 31-45, 46-60, 60+)  
  - High-risk flag (smoker + BMI ≥30 + pre-existing condition)  

## Power BI Dashboard Insights
![Power BI Dashboard Preview](https://i.imgur.com/placeholder-pbi.png)

**Key Visualizations:**
1. High-Risk Claimant Distribution by Region
2. Cost Breakdown by Age Group and BMI Category
3. Smoker vs Non-Smoker Cost Comparison
4. Pre-existing Condition Impact Analysis
5. Top 10 Cost Driver Indicators

**Interactive Features:**
- Drill-down regional analysis
- Dynamic risk profiling filters
- Year-over-year cost trend projections
- Claimant demographic segmentation

## Results  
| Model                  | R² Score | 
|------------------------|----------|
| Gradient Boosting      | 0.88     | 
| Random Forest          | 0.87     |  
| Ridge Regression       | 0.85     |  

**Power BI Analysis Findings:**
- Smokers incur 3.8x higher costs than non-smokers
- Obese claimants represent 68% of high-cost cases
- Southwest region has 22% more high-risk claimants
- 60+ age group accounts for 41% of top-cost claims

## Dataset  
`insurance.csv` with columns:  
- `age`, `sex`, `bmi`, `children`, `smoker`, `region`, `charges`  
- **Engineered Features**: `pre_existing_condition`, `bmi_category`, `age_group`, `high_risk`  

## Workflow  
```mermaid
graph LR
A[Raw Data] --> B[Python Processing]
B --> C[Feature Engineering]
C --> D[ML Modeling]
D --> E[Power BI Dashboard]
E --> F[Business Insights]

Use these key DAX measures:

### DAX Measure Used
Avg Cost = AVERAGE('Claims'[charges])
High Risk % = DIVIDE(
    CALCULATE(COUNTROWS('Claims'), 'Claims'[high_risk]=1),
    COUNTROWS('Claims')
)
Cost Variance = [Predicted Cost] - [Actual Cost]

### Recommended Repository Structure with Power BI Files:
insurance-claims-cost-analysis/
├── data/
│ ├── insurance.csv # Raw data
│ └── final_insurance_dataset.csv # Processed data
├── powerbi/
│ ├── insurance_analysis.pbix # Power BI dashboard
│ └── assets/ # Dashboard exports
├── outputs/
│ ├── plots/ # Saved visualizations
│ └── models/ # Serialized trained models
├── claims_cost_analysis.py # Main processing code
├── README.md
└── requirements.txt


### Power BI Integration Highlights:
1. **Dataset Connection**: Processed CSV feeds directly into Power BI data model
2. **Key Visualizations**:
   - Risk matrix heatmaps (BMI vs Age vs Cost)
   - Geographical cost distribution maps
   - Smoker impact donut charts
   - Cost driver waterfall charts
3. **Interactive Features**:
   - Risk profile sliders (adjust BMI/smoking thresholds)
   - Region comparison tool
   - Claimant demographic filters
4. **Business Insights**:
   - High-risk group segmentation
   - Cost reduction opportunity analysis
   - Premium pricing recommendations

This structure highlights the complete workflow from Python processing to Power BI business intelligence, making it valuable for both technical and business stakeholders.

