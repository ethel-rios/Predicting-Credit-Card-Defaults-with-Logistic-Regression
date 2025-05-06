# Credit Card Default Prediction Analysis
**`Logistic Regression Model | Cost-Optimized Thresholds | Business Impact`**

## Introduction
I developed a logistic regression model to tackle a critical business challenge: how to reduce credit card defaults without unnecessarily rejecting good customers. By making the model cost-sensitive, assigning a cost of $5,000 to each false negative (missed defaulter) and $2,500 to each false positive (wrongly rejected applicant), it achieved both goals. The model cut default losses by 50% while preserving approval rates, ultimately saving $625 per application compared to industry standards.

## Business Objectives
| Goal | Metric | Achievement |
|------|--------|-------------|
| Reduce default costs | Cost/Event < $1,250 | **$625/event** |
| Improve risk detection | AUC > 0.5 | **0.834 AUC** |
| Maintain precision in approvals | Precision > 25% | **54.8%** |
| Avoid false rejections of good clients|Negative Predictive Value > 75%| **93.9%** |

## Key Insights

### Top 3 Predictors of Default
1. Credit Card Debt  
2. Employment Tenure
3. Customer Age

### Financial Impact Analysis
- Defaults Prevented: 17 (Saved $85,000)
- Good Customers Rejected: 14 (Lost $35,000)
- Net Savings: $50,000.00 total | $625.00 per application

## Technical Skills Demonstrated
- Data Processing:	Pandas, NumPy, Stratified Sampling
- Feature Selection: SelectKBest, ANOVA F-Test
- Modeling: Logistic Regression with class_weight='balanced'
- Evaluation: AUC, Confusion Matrix, Precision, Recall, NPV
- Optimization: Threshold Tuning, Custom Cost Function
- Visualization: Matplotlib, Seaborn – ROC, Cost Bar Charts, Heatmaps
- Business Framing: Cost modeling, ROI analysis, risk mitigation logic

## Model Development

### 1: Data Overview
✔ View Table Structure  
✔ Check for Missing Values  
✔ Visualize distributions

**Dataset Summary:**  
- **400 rows** | **8 columns**

**Numerical Columns**:  

| Feature            | Description                 |
| ------------------ | --------------------------- |
| `id`               | Customer ID                 |
| `age`              | Customer age                |
| `years_employer`   | Years at current employer   |
| `years_address`    | Years at current address    |
| `income`           | Annual income               |
| `credit_card_debt` | Credit card debt            |
| `automobile_debt`  | Auto loan debt              |
| `outcomes`         | 1 = Default, 0 = No Default |


### 2. Feature Ranking (SelectKBest - ANOVA F-test)
Identified top predictors based on statistical significance:

### ANOVA Test Results
| Feature            | F-Score | p-Value   |
|--------------------|---------|-----------|
| Credit card debt   | 85.2    | < 0.001   |
| Years at employer  | 42.7    | < 0.001   |
| Age                | 38.9    | < 0.001   |
| Automobile debt    | 22.1    | < 0.001   |
| Income             | 15.6    | 0.003     |
| Years at address   | 8.3     | 0.042     |

### Part 3: Logistic Regression Model
The model was designed not only to classify defaults but to optimize business outcomes by adjusting the classification threshold and calculating the financial cost of decisions.
Key steps:
- Data Split: Stratified Train/Test
- Scaling: StandardScaler
- Training: Logistic Regression with class imbalance handling
- Threshold Tuning: Set to 0.55 for optimal cost
- Evaluation: Metrics + Custom Cost Function
- Visualization: ROC, Confusion Matrix, and Cost Comparison Charts


## Next Steps
- Test with Larger Dataset
- Automate Threshold Selection
- Compare Other Classifiers like Random Forest


