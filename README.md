# 🧠 Brain Tumor Patient Survival Time Prediction

### Machine Learning Regression Project

A machine learning project that predicts **patient survival time in months** using clinical and treatment-related features from a brain tumor dataset.

The project explores the dataset, performs preprocessing and categorical encoding, trains regression models, evaluates their performance, and analyzes feature importance using Random Forest.

> ⚠️ **Disclaimer:** This project is created for machine learning education and experimentation. It must not be used for medical diagnosis, prognosis, treatment decisions, or real-world clinical decision-making.

---

## 🎯 Project Objective

The main objective of this project is to build a regression model capable of predicting:

**`Survival Time (months)`**

using available patient-related clinical and treatment features.

The notebook compares two machine learning approaches:

* 📈 Linear Regression
* 🌲 Random Forest Regressor

---

## 📊 Project Workflow

```text
Brain Tumor Dataset
        ↓
Data Loading
        ↓
Data Exploration
        ↓
Missing Value Analysis
        ↓
Duplicate & Data Quality Checks
        ↓
Numerical / Categorical Analysis
        ↓
Data Visualization
        ↓
Feature Selection
        ↓
Categorical Encoding
        ↓
Train/Test Split
        ↓
Feature Scaling
        ↓
Linear Regression
        ↓
Random Forest Regressor
        ↓
Model Evaluation
        ↓
Model Comparison
        ↓
Feature Importance Analysis
```

---

## 🔍 Dataset

The notebook loads the dataset from:

```text
BrainTumor.csv
```

The target variable is:

```text
Survival Time (months)
```

The notebook performs exploratory analysis including:

* Dataset shape
* Column inspection
* Data types
* Descriptive statistics
* Missing-value analysis
* Numerical feature analysis
* Categorical feature analysis
* Correlation analysis
* Data visualization

---

## 🧹 Data Preprocessing

The project prepares the dataset before model training.

### Target and Features

The following columns are separated:

```python
X = data.drop(columns=["Patient ID", "Survival Time (months)"])
y = data["Survival Time (months)"]
```

`Patient ID` is removed because it is an identifier rather than a predictive feature.

### Categorical Encoding

Categorical variables are converted into numerical representations using `LabelEncoder`.

### Train/Test Split

The dataset is divided into:

```text
80% → Training Data
20% → Testing Data
```

with:

```python
random_state = 42
```

### Feature Scaling

Feature scaling is applied before training the Linear Regression model.

---

## 🤖 Machine Learning Models

### 1. Linear Regression

Linear Regression is used as a baseline regression model.

```python
model = LinearRegression()

model.fit(X_train_scaled, y_train)
```

The trained model predicts survival time on the test dataset.

---

### 2. Random Forest Regressor

A Random Forest Regressor is also trained:

```python
rf_model = RandomForestRegressor(
    n_estimators=200,
    random_state=42
)

rf_model.fit(X_train, y_train)
```

The model uses multiple decision trees to learn relationships between patient features and survival time.

---

## 📈 Model Evaluation

The models are evaluated using:

* **MAE** — Mean Absolute Error
* **MSE** — Mean Squared Error
* **RMSE** — Root Mean Squared Error
* **R² Score** — Coefficient of Determination

The notebook also includes:

* Actual vs Predicted plots
* R² score comparison
* Feature importance analysis
* Metrics comparison table

---

## 📊 Results

The current notebook reports the following test-set results:

| Model             |  MAE |   MSE | RMSE |    R² |
| ----------------- | ---: | ----: | ---: | ----: |
| Linear Regression | 5.29 | 47.47 | 6.89 | 0.378 |
| Random Forest     | 1.51 | 14.05 | 3.75 | 0.816 |

The reported Random Forest result has an **R² score of 0.816** and an **MAE of approximately 1.51 months** on the notebook's test split.

These are results from this particular dataset, preprocessing pipeline, model configuration, and train/test split; they should not be interpreted as clinical performance.

---

## 🌲 Feature Importance

The project also analyzes feature importance using the trained Random Forest model.

The notebook identifies features such as:

* **Time to Recurrence**
* **Age**
* **Recurrence Site**

among the more influential predictive features in the current model.

Feature importance indicates how the trained model used the available features; it does **not** establish medical causation.

---

## 🛠️ Technologies Used

* 🐍 Python
* 📓 Jupyter Notebook
* 🐼 Pandas
* 🔢 NumPy
* 📊 Matplotlib
* 🎨 Seaborn
* 🤖 Scikit-learn
* 📈 Linear Regression
* 🌲 Random Forest Regression

---

## 📁 Project Structure

```text
Brain-Tumor-Survival-Prediction/
│
├── BrainTumor.csv
├── project_Brain_Tumor.ipynb
├── README.md
└── LICENSE
```

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/suman9834/Brain-Tumor-Patient-Survival-Time-Prediction-Project.git
cd Brain-Tumor-Survival-Prediction
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the Notebook

Open:

```text
project_Brain_Tumor.ipynb
```

Make sure:

```text
BrainTumor.csv
```

is located in the same directory as the notebook.

### 5. Run the Notebook

Run the cells from top to bottom to reproduce the analysis and model evaluation.

---

## 📚 Key Learning Outcomes

This project demonstrates practical experience with:

* Exploratory Data Analysis
* Data cleaning and preprocessing
* Missing-value analysis
* Categorical data encoding
* Feature scaling
* Train/test splitting
* Regression models
* Linear Regression
* Random Forest Regression
* MAE, MSE and RMSE
* R² evaluation
* Actual vs predicted visualization
* Feature importance analysis
* Model comparison

---

## 🔮 Future Improvements

Possible improvements include:

* Cross-validation for more robust evaluation
* Hyperparameter tuning
* Testing additional regression algorithms
* More advanced feature engineering
* Improved handling of categorical variables
* Comparing different encoding strategies
* External validation on an independent dataset
* Model interpretability using additional techniques

---

## ⚠️ Medical Disclaimer

This project is **not a medical tool**.

The predictions generated by this machine learning model should not be used to:

* Diagnose brain tumors
* Predict an individual patient's actual prognosis
* Recommend treatment
* Replace medical professionals
* Make clinical decisions

The model is intended strictly for **educational and machine-learning experimentation purposes**.

---

## 👨‍💻 Author

**Suman Kumar**

B.Tech — Computer Science & Engineering
Specialization: Artificial Intelligence & Data Science

**Areas of Interest:**
Python • Machine Learning • Data Science • Artificial Intelligence • Computer Vision

---

## ⭐ Project

If you found this project useful, feel free to explore the repository and follow the development of more machine learning projects.

<p align="center">
  Made with 🐍 Python & 🤖 Machine Learning
</p>
