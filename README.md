# Credit Card Default Prediction Analysis
**`Logistic Regression Model | Cost-Optimized Thresholds | Business Impact`**

## 📌 Introduction
Developed a logistic regression model to predict credit card defaults and optimize financial decision-making. The model is designed to:
- Minimize losses per default
- Identify high-risk applicants with interpretable features
- Improve upon the 25% baseline default rate ($1,250 per defaulted customer)

## 🎯 Business Objectives
| Goal | Metric | Achievement |
|------|--------|-------------|
| Reduce default costs | Cost/Event < $1,250 | ✅ **$625./event** |
| Improve risk detection | AUC > 0.5 | ✅ **0.834 AUC** |
| Maintain precision in approvals | Precision > 25% | ✅ **54.8%** |
| Avoid false rejections of good clients|Negative Predictive Value > 75%| ✅ **93.9%** |

## 🗂 Dataset Overview

📦 **Dataset Summary:**  
- **📊 400 rows** | **📁 8 columns**  

🔢 **Numerical Columns**:  

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


## ⚙️ Python Analysis Process  
### 1: Data Overview**  
✔ View Table Structure  
✔ Check for Missing Values  
✔ Visualize distributions

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

### Part 3: Model Development (Logistic Regression)
The model was designed not only to classify defaults but to optimize business outcomes by adjusting the classification threshold and calculating the financial cost of decisions.

Trained with class_weight='balanced' to handle imbalance. Threshold tuned to 0.55 to minimize cost per application.
Key steps:
1. Stratified Train/Test Split
2. Feature Scaling (StandardScaler)
3. Probability Threshold Adjustment
4. Custom Cost Function Applied

### Part 4: 📈 Visualizations:
- ROC Curve with AUC
- Confusion Matrix with Accuracy, Recall, Specificity, Precision
- Cost Comparison Chart: Model vs Baseline


## 🔍 Key Insights

### 🏆 Top 3 Predictors of Default
1. **Credit Card Debt**  
2. **Employment Tenure**  
3. **Customer Age**

### 💰 Financial Impact Analysis
- Defaults Prevented: 17 (Saved $85,000)
- Good Customers Rejected: 14 (Lost $35,000)
- Net Savings: $50,000.00 total | $625.00 per application

