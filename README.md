# Sales Effectiveness ML Project

## 📌 Project Overview

The **Sales Effectiveness ML Project** focuses on analyzing sales and lead-related data to understand lead behavior, identify high-potential and low-potential leads, and build a machine learning workflow that can support better sales decision-making.

The project includes data cleaning, exploratory data analysis, visualization, feature preprocessing, categorical encoding, and machine learning model development.

The overall goal is to use historical sales data to identify patterns that can help sales teams **prioritize leads and improve sales effectiveness**.

---

## 🎯 Objectives

The main objectives of this project are:

* Analyze the available sales/lead dataset.
* Clean and preprocess the raw data.
* Handle missing values and inconsistent data.
* Explore relationships between different features and lead status.
* Create meaningful visualizations to understand sales patterns.
* Categorize leads based on their status and potential.
* Encode categorical variables for machine learning.
* Prepare training and testing datasets.
* Build and evaluate machine learning models.
* Identify features that contribute to sales effectiveness.
* Develop a workflow that can help prioritize potential leads.

---

## 📂 Project Structure

```text
Sales-Effectiveness-ML/
│
├── Sales_Effectiveness.ipynb
├── README.md
├── dataset/
│   └── sales_data.csv
│
└── images/
    └── visualizations/
```

> The exact file and folder names can be modified according to the structure of the GitHub repository.

---

## 📊 Dataset

The dataset contains information related to sales leads and their associated attributes.

The project uses various numerical and categorical features to understand lead characteristics and their relationship with lead status.

The target/status information is also used to create meaningful lead categories such as:

* **High Potential**
* **Low Potential**
* Other relevant categories depending on the cleaned status values.

---

## 🔄 Project Workflow

The project follows the following machine learning workflow:

```text
Raw Dataset
     ↓
Data Understanding
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Data Visualization
     ↓
Feature Engineering
     ↓
Lead Categorization
     ↓
Train/Test Split
     ↓
Numerical Feature Processing
     ↓
Categorical Feature Encoding
     ↓
Feature Combination
     ↓
Machine Learning Model
     ↓
Model Evaluation
     ↓
Sales Effectiveness Insights
```

---

## 🧹 Data Preprocessing

Several preprocessing steps are performed before applying machine learning models.

### Data Cleaning

The dataset is examined for:

* Missing values
* Duplicate records
* Incorrect data types
* Inconsistent categorical values
* Unnecessary columns
* Invalid or inconsistent status values

### Status Cleaning

A cleaned status variable is created to standardize the different status values.

This allows the project to group similar sales outcomes together and use them consistently during analysis.

### Lead Categorization

The cleaned status values are further grouped into meaningful lead categories.

For example:

```python
df.loc[df['Status_Clean'].isin(high_potential),
       'Lead_Category'] = 'High Potential'

df.loc[df['Status_Clean'].isin(low_potential),
       'Lead_Category'] = 'Low Potential'
```

This categorization helps transform raw sales status information into a more useful business-oriented feature.

---

## 📈 Exploratory Data Analysis

Exploratory Data Analysis (EDA) is performed to understand the structure and patterns within the dataset.

The analysis includes:

* Distribution of lead statuses
* Comparison of features with lead status
* Numerical feature analysis
* Categorical feature analysis
* High-potential vs low-potential lead comparisons
* Identification of relationships between variables

---

## 📊 Data Visualization

Visualizations are used to make the patterns in the dataset easier to understand.

The project includes visualizations such as:

* Status distribution
* Feature vs Status comparisons
* Categorical feature comparisons
* Numerical feature distributions
* Lead category comparisons

### Plotly

**Plotly** can also be used to create interactive visualizations that allow users to explore the data dynamically.

Example:

```python
import plotly.express as px

fig = px.bar(
    df,
    x='Lead_Category',
    title='Lead Category Distribution'
)

fig.show()
```

---

## 🔧 Feature Engineering

Feature engineering is performed to convert the raw dataset into features that can be used effectively by machine learning algorithms.

The process includes:

* Selecting relevant features
* Separating numerical and categorical features
* Cleaning categorical variables
* Encoding categorical variables
* Preparing features for model training

---

## 🔢 Categorical Encoding

Machine learning algorithms generally require numerical input.

Therefore, categorical features are converted into numerical representations using encoding techniques such as **One-Hot Encoding**.

For example:

```python
from sklearn.preprocessing import OneHotEncoder

encoder = OneHotEncoder(
    handle_unknown='ignore',
    sparse_output=False
)

x_train_encode = encoder.fit_transform(x_train_categorical)
x_test_encode = encoder.transform(x_test_categorical)
```

The encoded categorical features are then combined with the numerical features.

```python
x_train_final = np.hstack([
    x_train_numeric,
    x_train_encode
])

x_test_final = np.hstack([
    x_test_numeric,
    x_test_encode
])
```

---

## 🤖 Machine Learning

After preprocessing, the prepared dataset is used to train machine learning models.

The general process is:

1. Define features and target.
2. Split the dataset into training and testing sets.
3. Process numerical variables.
4. Encode categorical variables.
5. Combine the processed features.
6. Train machine learning models.
7. Generate predictions.
8. Evaluate model performance.

---

## 📏 Model Evaluation

The model performance can be evaluated using appropriate classification metrics such as:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* ROC-AUC

These metrics help determine how effectively the model can distinguish between different lead outcomes/categories.

---

## 💡 Business Insights

The project aims to provide useful insights for sales teams, including:

* Which characteristics are associated with high-potential leads?
* Which leads are less likely to convert?
* Which features have the strongest relationship with sales outcomes?
* How can sales representatives prioritize leads?
* How can data-driven lead categorization improve sales efficiency?

The ultimate objective is to support **better lead prioritization and more effective allocation of sales resources**.

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Plotly**
* **Scikit-learn**
* **Git**
* **GitHub**

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
```

### 2. Navigate to the project directory

```bash
cd Sales-Effectiveness-ML
```

### 3. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the project notebook

Open:

```text
Sales_Effectiveness.ipynb
```

Run the notebook cells sequentially.

---

## 📌 Future Improvements

The project can be further improved by:

* Testing additional machine learning algorithms.
* Performing hyperparameter tuning.
* Applying cross-validation.
* Performing feature importance analysis.
* Handling class imbalance if present.
* Creating an interactive Plotly dashboard.
* Comparing multiple models.
* Deploying the final model as a web application or API.
* Automating lead scoring for new sales leads.

---

## 👥 Project Collaboration

This project can be developed collaboratively using GitHub.

Recommended workflow:

```text
Clone Repository
       ↓
Create/Update Your Work
       ↓
Test the Notebook
       ↓
Commit Changes
       ↓
Push to GitHub
       ↓
Share Repository / Updated File
```

When collaborating, avoid modifying the original project file directly unless the team has agreed on the changes. Work can be developed separately and then merged after review.

---

## 📜 License

This project is intended for educational and project-development purposes.

---

## 👤 Author

**Sales Effectiveness ML Project**

Developed as a machine learning project focused on sales data analysis, lead categorization, and predictive modeling.
