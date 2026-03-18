# 🏦 Loan Approval Prediction Analysis

## 📌 Project Overview

This project presents an end-to-end **loan approval prediction analysis** built using Python and machine learning. The work explores how **demographic, financial, and asset-related factors** influence whether a loan application is **approved or rejected**.

The project combines **data cleaning, feature engineering, exploratory data analysis, feature scaling, correlation analysis, and predictive modelling** to identify the strongest drivers of loan approval outcomes. Multiple classification models were trained and evaluated, with **XGBoost achieving the best performance at 98.24% accuracy**.

This project demonstrates how structured financial and behavioural data can be transformed into actionable lending insights for smarter credit decision-making.

---

## 🏢 Business Context

Loan approval is one of the most important decisions made by financial institutions. Approving the wrong applicant can increase default risk, while rejecting a creditworthy borrower can result in lost business opportunities and poor customer experience.

In practice, lenders must evaluate several factors before approving a loan, including:

- borrower income  
- creditworthiness  
- employment status  
- education  
- number of dependents  
- requested loan amount  
- available assets  

The challenge is that these variables often interact in complex ways, making it difficult to assess applications consistently through intuition or manual review alone.

This project simulates the type of analysis a lender or risk team would perform to understand what drives loan approvals and to build a model that can support more consistent and data-driven lending decisions.

---

## 🎯 Purpose of the Project

The purpose of this project was to:

- analyse the relationship between applicant attributes and loan approval outcomes  
- identify the strongest variables influencing loan decisions  
- build predictive models capable of classifying applications as approved or rejected  
- compare the performance of multiple machine learning algorithms  
- generate insights that could support lenders in improving approval strategies and risk evaluation  

In simple terms, the project converts raw applicant data into both **business insight** and a **predictive decision-support model**.

---

## ✅ Expected Business Outcome

The expected outcome of this project was to improve understanding of the drivers of loan approval and create a model that could support more informed lending decisions.

More specifically, the analysis was expected to:

- identify the variables most associated with loan approval  
- detect patterns in borrower behaviour and financial strength  
- support risk-aware decision-making  
- reduce subjectivity in applicant screening  
- improve approval consistency  
- provide a framework for future credit scoring or underwriting models  

---

## ⚠️ Business Challenges

Before model development, the following analytical challenges needed to be addressed:

### 1. Complex relationships between features
Loan approval is influenced by multiple interconnected variables, including income, assets, credit score, loan amount, and employment status.

### 2. Difficulty identifying the strongest approval drivers
Without structured analysis, it is difficult to determine which borrower attributes matter most in predicting approval outcomes.

### 3. Need for consistent decision-making
Manual loan review can introduce inconsistency and bias if decisions are not guided by clear patterns in the data.

### 4. Balancing risk and opportunity
Lenders must approve enough quality borrowers to grow the business while minimizing exposure to repayment risk.

### 5. Translating raw applicant data into prediction-ready inputs
The dataset required preprocessing, feature engineering, encoding, and scaling before meaningful modelling could take place.

---

## 💡 Rationale for the Project

This project was initiated because raw loan application data alone does not create value unless it is structured, analysed, and converted into predictive intelligence.

The rationale behind the project was to:

- uncover the true drivers of loan approval  
- test whether borrower approval outcomes could be predicted reliably  
- compare multiple classification models to identify the strongest performer  
- create an analytical foundation for credit decision support  
- provide evidence-based guidance for lenders and borrowers  

Rather than treating loan records as isolated applications, this project reframed them as a source of **credit risk intelligence**.

---

## 🎯 Project Objectives

The main objectives of the project were:

1. **Clean and prepare the dataset** by checking for missing values, duplicates, and irrelevant fields.

2. **Engineer additional features** such as:
   - Liquid Assets
   - Fixed Assets

3. **Perform exploratory data analysis (EDA)** to understand:
   - applicant demographics
   - financial strength
   - asset behaviour
   - loan patterns
   - approval/rejection distributions

4. **Examine relationships between variables** using visualisations and correlation analysis.

5. **Encode and scale features** to improve model readiness and consistency.

6. **Train and compare multiple classification models**:
   - Logistic Regression
   - Decision Tree
   - Random Forest
   - XGBoost

7. **Evaluate model performance** using:
   - Accuracy
   - Precision
   - Recall
   - Confusion Matrix

8. **Identify the best-performing model** and derive practical lending insights.

---

## 🗂️ Dataset Description

The dataset contains **4,269 loan application records** and **13 original columns**.

### Core Fields Included

- **loan_id** – unique identifier for each application  
- **no_of_dependents** – number of financial dependents  
- **education** – graduate / non-graduate  
- **self_employed** – whether the applicant is self-employed  
- **income_annum** – annual income  
- **loan_amount** – requested loan amount  
- **loan_term** – loan duration  
- **cibil_score** – applicant’s credit score  
- **residential_assets_value** – value of residential assets  
- **commercial_assets_value** – value of commercial assets  
- **luxury_assets_value** – value of luxury assets  
- **bank_asset_value** – value of bank assets  
- **loan_status** – approved / rejected  

### Derived Features Created

Two engineered variables were created to better summarize asset profiles:

- **Liquid_assets = bank_asset_value + luxury_assets_value**
- **Fixed_assets = residential_assets_value + commercial_assets_value**

These features improved interpretability by grouping related asset classes into more meaningful financial categories.

---

## 🛠️ Tech Stack Used

This project was developed in **Python** using a notebook-based workflow.

### Core Libraries Used

#### Data Handling
- **Pandas**
- **NumPy**

#### Visualisation
- **Matplotlib**
- **Seaborn**

#### Machine Learning
- **Scikit-learn**
- **XGBoost**

#### Modelling Utilities
- `train_test_split`
- `StandardScaler`
- `LabelEncoder`
- `classification_report`
- `accuracy_score`
- `precision_score`
- `recall_score`
- `confusion_matrix`

#### Environment
- **Google Colab**

---

## 📊 Project Scope

### ✅ Included in Scope
This project includes:

- data cleaning and validation  
- feature engineering  
- exploratory data analysis  
- correlation analysis  
- feature scaling  
- categorical encoding  
- model training and testing  
- model comparison  
- confusion matrix evaluation  
- interpretation of business-relevant findings  

### ❌ Excluded from Scope
The following were not covered in this project:

- hyperparameter tuning  
- class imbalance handling (if required)  
- deployment into a production API or web app  
- explainability tooling such as SHAP or LIME  
- loan pricing optimization  
- live model monitoring  

This means the project is focused on **exploratory, predictive, and comparative modelling**, not deployment.

---

## 📈 Interpretation and Key Insights

### 1. Loan Approval Distribution
The dataset shows that **approved loans outnumber rejected loans**, suggesting that a larger proportion of applicants in this dataset meet the lender’s criteria.

This indicates that the approval class is dominant and that the dataset may reflect an environment where a sizeable share of borrowers are creditworthy.

---

### 2. CIBIL Score is the Strongest Predictor
Correlation analysis showed that **CIBIL Score had the strongest positive relationship with loan approval**, with a correlation of approximately:

**0.7705**

This makes it the single most influential variable in the dataset. Visual analysis also showed that approved borrowers typically had **higher credit scores**, especially above the 600 range.

👉 This suggests that creditworthiness is the most important determinant of approval outcomes.

---

### 3. Assets Positively Influence Approval
The visualisations showed that both **liquid assets** and **fixed assets** increase the likelihood of loan approval.

Applicants with stronger asset positions were more likely to be approved, which is consistent with lending logic because assets indicate repayment strength and collateral support.

👉 Higher assets = stronger approval probability.

---

### 4. Income and Loan Amount Move Together
A clear positive relationship was observed between:

- **income_annum**
- **loan_amount**

Applicants with higher annual income tend to request larger loans, which is expected because lenders usually assess affordability partly through income strength.

---

### 5. Number of Dependents Affects Rejection More Than Approval
The countplot showed that **rejection tends to increase with more dependents**, while approval counts remain relatively stable.

This suggests that a higher number of dependents may increase perceived repayment burden, although it is not strong enough on its own to fully determine approval.

---

### 6. Education Alone is Not a Strong Approval Driver
Visual exploration indicated **little difference in approval outcomes between graduates and non-graduates**.

This suggests that education may matter less than financial strength, credit behaviour, and assets in determining loan outcomes.

---

### 7. Self-Employment and Education Show Behavioural Differences
The analysis of education and self-employment showed that **graduates were less likely to be self-employed**, while many non-graduates were self-employed.

This may reflect differences in income stability, which can influence approval decisions indirectly.

---

### 8. Feature Engineering Improved Financial Interpretation
By combining raw asset variables into **Liquid_assets** and **Fixed_assets**, the project simplified interpretation and gave a clearer view of applicant wealth structure.

This made the model and analysis more meaningful from a financial perspective.

---

## 🤖 Model Performance

Four classification models were trained and evaluated:

- Logistic Regression  
- Decision Tree  
- Random Forest  
- XGBoost  

### Best Performing Model
The strongest model was:

- **XGBoost**
- **Accuracy: 98.24%**

This slightly outperformed the Decision Tree model and demonstrated the strongest predictive capability on the test set.

### Why this matters
A model with this level of performance suggests that the available features capture loan approval behaviour very effectively, especially through the influence of credit score, assets, income, and related financial indicators.

---

## 🚀 Recommendations

### 1. Prioritise Credit Score in Approval Strategy
Since **CIBIL Score** is the strongest predictor, lenders should continue giving it significant weight in credit evaluation models.

### 2. Incorporate Asset-Based Risk Assessment
Both liquid and fixed assets showed clear value in predicting approval. Lenders should account for total asset strength as part of affordability and collateral analysis.

### 3. Use Income-to-Loan Relationship More Strategically
Because higher-income applicants request larger loans, institutions should review whether current loan sizing rules can be better calibrated to risk-adjusted affordability.

### 4. Monitor High-Dependent Applicants More Carefully
Applicants with many dependents may require closer affordability review, as rejection patterns appear to rise with dependent count.

### 5. Use Predictive Modelling to Support, Not Replace, Human Review
A high-performing model such as XGBoost can improve consistency and efficiency, but final lending decisions should still consider policy, compliance, and contextual judgment.

### 6. Expand the Model With Explainability Techniques
Future work should incorporate model explainability tools so lenders can better understand why specific approvals or rejections occur.

---

## 🧠 Final Business Value

This project provides a strong analytical foundation for **data-driven lending decisions** by enabling lenders to:

- identify the strongest drivers of loan approval  
- predict approval outcomes with high accuracy  
- reduce subjectivity in applicant screening  
- better understand the role of assets, income, and credit score  
- compare multiple predictive models  
- support smarter credit risk evaluation  

In practical terms, the project transforms raw loan application data into both **business insight** and a **predictive credit decision-support tool**.

---

