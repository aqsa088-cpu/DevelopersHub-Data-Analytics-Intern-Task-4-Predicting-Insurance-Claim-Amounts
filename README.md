# 🏥 Predicting Insurance Claim Amounts

## 📌 Task Objective

The goal of this project is to **predict medical insurance claim amounts** for individuals based on personal and lifestyle attributes. Using a dataset (`insurance.csv`) containing features like age, BMI, smoking status, and region, we build machine learning models to accurately estimate the `charges` (insurance cost) for each person.

This is a **regression problem** where the target variable is a continuous numerical value representing medical expenses.

---

## 🔍 Dataset Features

| Feature | Description |
|---------|-------------|
| `age` | Age of the individual |
| `sex` | Gender (male/female) |
| `bmi` | Body Mass Index |
| `children` | Number of dependent children |
| `smoker` | Smoking status (yes/no) |
| `region` | Residential region (northeast, northwest, southeast, southwest) |
| `charges` | Medical insurance charges **(target variable)** |

---

## 🛠️ Approach

### 1. Data Loading & Exploration
- Loaded the dataset using `pandas`
- Inspected data types, shape, and descriptive statistics
- Checked for missing values (none found)

### 2. Data Preprocessing
- Applied **One-Hot Encoding** on categorical features: `sex`, `smoker`, `region`
- Used `drop_first=True` to avoid multicollinearity
- Applied **StandardScaler** on numerical features: `age`, `bmi`, `children`

### 3. Exploratory Data Analysis (EDA)
- Plotted distribution of `charges`, `age`, and `bmi`
- Analyzed relationship between smoker status and charges (box plots)
- Visualized impact of age and BMI on charges using scatter plots with smoker as hue

### 4. Model Building
Two models were trained and evaluated:

#### ✅ Linear Regression (Baseline)
- Simple, interpretable model
- Assumes linear relationship between features and target

#### ✅ Random Forest Regressor
- Ensemble method with 100 decision trees
- Captures non-linear relationships
- Provides feature importance scores

### 5. Model Evaluation
Models were evaluated using:
- **MAE** – Mean Absolute Error
- **MSE** – Mean Squared Error
- **RMSE** – Root Mean Squared Error
- **R²** – R-squared (goodness of fit)

---

## 📊 Results & Insights

### Model Performance Comparison

| Metric | Linear Regression | Random Forest |
|--------|:-----------------:|:-------------:|
| MAE | Higher | **Lower ✅** |
| RMSE | Higher | **Lower ✅** |
| R² Score | ~0.75–0.78 | **~0.85–0.88 ✅** |

> *Random Forest significantly outperformed Linear Regression due to its ability to capture non-linear patterns.*

---

### 🔑 Key Insights

1. **Smoking is the strongest predictor** — Smokers have dramatically higher insurance charges compared to non-smokers.
2. **Age has a positive correlation** — Charges increase consistently with age.
3. **High BMI + Smoking = Highest Risk** — The combination of high BMI and smoking leads to the highest claim amounts.
4. **Region has minimal impact** — Geographic region shows little variation in charges.
5. **Number of children has low influence** — Slightly increases charges but is not a major factor.

---

## 🧰 Tools & Libraries

- **Python**
- `pandas` — Data manipulation
- `matplotlib` & `seaborn` — Data visualization
- `scikit-learn` — Preprocessing, model building, evaluation

---


## 🚀 How to Run

1. Clone the repository
2. Install dependencies: `pip install pandas matplotlib seaborn scikit-learn`
3. Open the notebook: `jupyter notebook Predicting_Insurance_Claim_Amounts.ipynb`
4. Run all cells in order

---

*Project completed as part of DevelopersHub Internship Program*
