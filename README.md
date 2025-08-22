# Credit Risk Assessment - Exploratory Data Analysis

This repository contains a comprehensive Exploratory Data Analysis (EDA) for the German Credit Dataset, focusing on the cost-sensitive nature of credit risk assessment.

## Repository Contents

- `kredit.dat` - German Credit Dataset (1000 instances, 20 features + target)
- `credit_risk_eda.ipynb` - Comprehensive EDA Jupyter notebook
- `Projekt04_credit.pdf` - Original project documentation

## Key Features of the Analysis

### 1. Cost-Sensitive Problem Definition
- **5:1 cost ratio**: Misclassifying an unworthy customer as creditworthy costs 5 times more than the reverse
- Target variable: 1 = creditworthy, 2 = not creditworthy
- Analysis of cost implications for different prediction strategies

### 2. Dataset Characteristics
- **Size**: 1000 instances with 21 columns (20 features + target)
- **Missing values**: Present in 4 features (purpose, employment, job, foreign_worker)
- **Class distribution**: 700 creditworthy (70%) vs 300 not creditworthy (30%)
- **Feature types**: Mix of numerical (7) and categorical (13) features

### 3. Comprehensive Analysis Sections

#### Data Loading and Initial Exploration
- Proper feature naming based on domain knowledge
- Missing value identification and handling
- Basic dataset statistics and information

#### Target Variable Analysis
- Class distribution and imbalance analysis
- Cost matrix visualization
- Expected costs for naive prediction strategies

#### Feature Distribution Analysis
- Separate analysis for numerical vs categorical features
- Distribution plots with statistical summaries
- Missing value patterns in visualizations

#### Relationship Analysis with Target
- Statistical tests (Mann-Whitney U for numerical, Chi-square for categorical)
- Box plots and violin plots for numerical features
- Contingency tables and stacked bar charts for categorical features

#### Correlation and Association Analysis
- Correlation matrices for numerical features
- Cramér's V for categorical feature associations
- Feature importance ranking based on target relationship

#### Cost-Sensitive Analysis
- Break-even threshold calculation (optimal = 0.167)
- Comparison of prediction strategies and their costs
- Sensitivity analysis of classification thresholds

#### Missing Value Analysis
- Detailed pattern analysis and co-occurrence
- Impact of missing values on target variable
- Statistical significance tests for missing value patterns

#### Key Insights and Recommendations
- Actionable recommendations for preprocessing
- Model selection guidance for cost-sensitive learning
- Evaluation strategy recommendations

## Requirements

```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

## Usage

### Running the Jupyter Notebook

1. **Start Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

2. **Open the notebook:**
   - Navigate to `credit_risk_eda.ipynb`
   - Run all cells sequentially

### Alternative: Python Script Execution

The notebook can also be converted to a Python script:

```bash
jupyter nbconvert --to script credit_risk_eda.ipynb
python credit_risk_eda.py
```

## Key Findings

1. **Cost Sensitivity**: The 5:1 cost ratio means conservative classification is optimal - better to reject a good customer than approve a bad one.

2. **Class Imbalance**: 2.33:1 ratio (good:bad) combined with cost sensitivity requires special handling.

3. **Feature Importance**: Duration, credit amount, and age show strongest correlations with target.

4. **Missing Values**: Significant missing data in employment (49.6%) and foreign_worker (36.0%) features.

5. **Optimal Threshold**: For cost-sensitive classification, use 0.167 probability threshold (need only 16.7% confidence to classify as creditworthy).

## Recommended Next Steps

1. **Preprocessing**: Handle missing values with domain-appropriate imputation
2. **Feature Engineering**: Create interaction terms, encode categorical variables
3. **Model Selection**: Use cost-sensitive algorithms (Random Forest with class weights, cost-sensitive SVM)
4. **Evaluation**: Focus on total cost rather than accuracy as primary metric
5. **Cross-validation**: Maintain cost ratios in validation strategy

## Model Selection Recommendations

- **Algorithms**: Cost-sensitive Random Forest, SVM with class weights, ensemble methods
- **Techniques**: SMOTE with cost adjustment, threshold tuning
- **Evaluation**: ROC curves with cost-sensitive thresholds, business impact assessment

This analysis provides a solid foundation for building effective credit risk assessment models that account for the real-world business costs of misclassification.