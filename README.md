# Complete Project Overview: University Student Dropout Prediction
## Predicting Academic Risk using Logistic Regression

# 🎯 Project Overview

## 📋 Problem Statement
Universities typically identify struggling students only after poor exam results, when intervention opportunities are limited. This reactive approach leads to:

- 📉 Higher dropout rates
- 💸 Wasted resources  
- 🎓 Unfulfilled student potential

## 🚀 Solution
**University Student Dropout Prediction** is a Predictive Model that flags at-risk students 4-6 weeks before critical assessments, enabling proactive academic counseling, tutoring allocation, and financial aid support.



# 📊 Dataset Description

## 📁 Source Information
- **Dataset**: [Higher Education Predictors of Student Retention](https://www.kaggle.com/datasets/thedevastator/higher-education-predictors-of-student-retention)
- **Direct Download Link**: [dataset.csv](https://www.kaggle.com/datasets/thedevastator/higher-education-predictors-of-student-retention)
- **Institution**: Portuguese Higher Education University
- **License**: Public Domain (Kaggle)

## 📈 Statistics Overview

| Metric | Value |
|--------|-------|
| Original Records | 4,424 students |
| After Preprocessing | 3,630 students |
| Features | 36 predictor variables |
| Target Classes | Binary |
| Class Distribution | Graduate: 60.86%, Dropout: 39.14% |
| Train/Test Split | 80% / 20% (2,904 / 726 students) |

## 🧹 Data Preprocessing

### 🔍 Filtering & Cleaning
- **Removed Ambiguous Cases**: Excluded 794 "Enrolled" students (17.95%)
- **Rationale**: "Enrolled" status represents unknown outcomes, introducing label noise

### 🔢 Encoding & Splitting
- **Binary Encoding**: Graduate = 0, Dropout = 1
- **Stratified Split**: Maintained class distribution in train/test sets
## 🗂️ Feature Categories

### 1. 📚 Academic Performance (14 features)
- **Curricular units 1st/2nd semester**:
  - Credited units
  - Enrolled units  
  - Evaluations completed
  - Approved units
  - Grades achieved
  - Units without evaluations
- Previous qualification grade
- Admission grade

### 2. 👥 Demographics (4 features)
- Age at enrollment
- Gender
- Marital status  
- Nationality

### 3. 💰 Socioeconomic (8 features)
- Mother's qualification & occupation
- Father's qualification & occupation
- Scholarship holder (Yes/No)
- Debtor status (Outstanding tuition fees)
- Tuition fees up to date

### 4. 🎓 Enrollment Information (7 features)
- Application mode (e.g., general contingent, special regimes)
- Application order (preference ranking)
- Course enrolled
- Previous qualification type
- Daytime/evening attendance
- Displaced student status

### 5. 📈 Macroeconomic Indicators (3 features)
- Unemployment rate (%)
- Inflation rate (%)
- GDP (economic context)
  
## 🛠️ Methodology

### 📅 Development Timeline (8-Day Sprint)

| Day | Focus | Key Activities |
|-----|-------|----------------|
| **Day 1** | Environment Setup | Library imports and initial configuration |
| **Day 2** | Data Exploration & Cleaning | Dataset loading, class distribution analysis, removed ambiguous "Enrolled" cases |
| **Day 3** | Feature-Target Separation | Split independent/dependent variables, 80/20 train-test split with stratification |
| **Day 4** | Feature Engineering | Identified 17 numerical & 18 categorical features, set up ColumnTransformer |
| **Day 5** | Pipeline Construction | Built scikit-learn pipeline with feature mapping verification |
| **Day 6** | Model Training | Logistic regression with balanced class weights (max_iter=5000) |
| **Day 7** | Initial Evaluation | Calculated confusion matrix, accuracy, F1-score, and predicted probabilities |
| **Day 8** | Advanced Evaluation | ROC-AUC analysis, coefficient importance, and SHAP interpretability |

### ⚙️ Technical Implementation

**Data Processing:**
- Binary target encoding: Graduate (0) vs. Dropout (1)
- One-hot encoding for 18 categorical variables
- Stratified sampling to maintain class distribution

**Model Architecture:**
- Scikit-learn Pipeline with ColumnTransformer
- Logistic Regression with balanced class weighting
- 105 total features after encoding

**Key Hyperparameters:**
- `max_iter=5000`: Ensures convergence
- `class_weight="balanced"`: Handles 60/40 class imbalance
- Stratified 80/20 train-test split

**Evaluation Framework:**
- Primary Metrics: Accuracy, F1-Score, ROC-AUC
- Interpretability: Coefficient analysis & SHAP values
- Practical Application: Individual student risk scoring
## 📈 Results

### Model Performance Metrics

| Metric | Score | Interpretation |
|--------|-------|----------------|
| **Accuracy** | `92.01%` | 92% of all predictions were correct |
| **F1 Score** | `0.902` | Excellent balance between precision & recall |
| **ROC-AUC** | `0.976` | Outstanding discrimination ability |
| **Precision** | `87.0%` | 87% of predicted dropouts were correct |
| **Recall** | `93.7%` | Captured 94% of actual at-risk students |


## 🔍 Model Explainability

### Top 10 Dropout Predictors (Coefficient Analysis)

#### ⚠️ **Positive Coefficients** (Increase Dropout Risk)

| Feature | Coefficient | Impact |
|---------|------------|--------|
| **Debtor Status** | +2.34 | Outstanding tuition fees strongly predict dropout |
| **Age at Enrollment** | +1.87 | Older students face higher dropout risk |
| **Curricular Units 1st Sem (Without Evaluations)** | +1.65 | Skipped assessments indicate risk |
| **Application Order** | +1.23 | Lower course preference ranking increases risk |
| **Unemployment Rate** | +0.98 | Economic hardship indicator |

#### ✅ **Negative Coefficients** (Decrease Dropout Risk)

| Feature | Coefficient | Impact |
|---------|------------|--------|
| **Curricular Units 1st Sem (Approved)** | -3.21 | Passing courses strongly predicts success |
| **Curricular Units 1st Sem (Grade)** | -2.89 | Higher grades = lower dropout risk |
| **Scholarship Holder** | -1.56 | Financial support improves retention |
| **Curricular Units 2nd Sem (Grade)** | -2.34 | Consistent academic performance |
| **Tuition Fees Up to Date** | -1.98 | Financial stability indicator |
## 🚀 How to Run the Model



###  Run the Model in Google Colab (Recommended for Quick Start)

### Step 1: Upload notebook to Google Colab
### Step 2: Upload dataset.csv to Colab environment
### Step 3: Run all cells
