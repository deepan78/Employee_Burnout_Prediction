# Employee Burnout Prediction Using Machine Learning

## Project Overview

Employee burnout is a growing workplace concern that can affect employee well-being, productivity, and work performance. Identifying potential burnout levels through data analysis can help organizations better understand workplace-related factors.

This project uses **Machine Learning, specifically Random Forest Regression**, to predict employee burnout levels based on factors such as company type, work-from-home availability, designation, resource allocation, and mental fatigue score.

The project includes data exploration, preprocessing, visualization, model training, evaluation, and burnout rate prediction.

## Objectives

- Analyze employee-related data to understand burnout patterns.
- Identify important factors associated with employee burnout.
- Clean and preprocess the dataset for machine learning.
- Develop a predictive model using Random Forest Regression.
- Evaluate model performance using regression metrics.
- Generate burnout rate predictions for new employee records.

## Dataset Description

**Dataset Name:** Are Your Employees Burning Out?

The dataset contains employee-related information and a target variable called `Burn Rate`.

| Dataset Details | Information |
|---|---|
| Training dataset | 22,750 records |
| Testing dataset | 12,250 records |
| Training columns | 9 |
| Testing columns | 8 |
| Target variable | Burn Rate |
| Problem type | Regression |

### Features Description

| Feature | Description |
|---|---|
| Employee ID | Unique identifier for each employee |
| Date of Joining | Employee's joining date |
| Gender | Gender category |
| Company Type | Product-based or Service-based company |
| WFH Setup Available | Whether work-from-home setup is available |
| Designation | Numerical designation code ranging from 0 to 5 |
| Resource Allocation | Numerical resource allocation value ranging from 1 to 10 |
| Mental Fatigue Score | Mental fatigue score ranging from 0 to 10 |
| Burn Rate | Target variable representing the burnout rate, ranging from 0 to 1 |

**Note:** The dataset does not document the exact mapping of designation codes or the questionnaire and scoring formula used for mental fatigue. The raw CSV also does not establish the measurement unit for resource allocation.

## Technologies Used

- **Python** – Main programming language.
- **Jupyter Notebook** – Development environment.
- **Pandas** – Data manipulation and cleaning.
- **NumPy** – Numerical operations.
- **Matplotlib** – Data visualization.
- **Seaborn** – Statistical visualization and correlation analysis.
- **Scikit-learn** – Data preprocessing, model development, and evaluation.
- **Random Forest Regressor** – Machine learning algorithm.
- **Joblib** – Saving and loading the trained model.
- **CSV** – Dataset storage format.

## Project Workflow

### 1. Problem Understanding and Dataset Exploration

- Identified employee burnout prediction as a regression problem.
- Explored the dataset structure, columns, and data types.
- Analyzed numerical and categorical features.
- Examined missing values and feature distributions.
- Identified `Burn Rate` as the prediction target.

### 2. Data Cleaning and Preprocessing

- Removed records with missing target values.
- Handled missing numerical values using median imputation.
- Handled missing categorical values using most-frequent imputation.
- Applied One-Hot Encoding to categorical features.
- Selected relevant features for model training.
- Used a Scikit-learn preprocessing pipeline.

### 3. Exploratory Data Analysis and Visualization

- Analyzed feature distributions.
- Examined relationships between employee-related features and Burn Rate.
- Generated correlation analysis.
- Identified important patterns and insights using Matplotlib and Seaborn.

### 4. Model Development

The project uses **Random Forest Regression**, an ensemble machine learning algorithm that combines multiple decision trees to predict continuous numerical values.

**Model Configuration:**

- Algorithm: Random Forest Regressor
- Number of Estimators: 100
- Maximum Depth: 10
- Random State: 42
- Parallel Processing: Enabled using `n_jobs=-1`

### 5. Model Evaluation

The dataset was divided into training and validation sets using an 80:20 split.

The model was evaluated using the following regression metrics:

| Evaluation Metric | Result |
|---|---:|
| Mean Absolute Error (MAE) | 0.0472 |
| Root Mean Squared Error (RMSE) | 0.0604 |
| R² Score | 0.9042 |

**Metric Explanation:**

- **MAE:** Measures the average absolute difference between actual and predicted Burn Rate values.
- **RMSE:** Measures prediction error while giving greater weight to larger errors.
- **R² Score:** Indicates how much variation in the target variable is explained by the model on the validation dataset.

**Important:** R² = 0.9042 is not 90.42% prediction accuracy. These are validation results, not guaranteed performance on unseen real-world employee data.

### 6. Prediction and Model Saving

- Retrained the final model using all available labelled training records.
- Saved the trained model using Joblib.
- Generated predictions for the test dataset.
- Exported predictions into a CSV file.
- Included an option for manual employee data input and prediction.

## Key Findings

- Mental Fatigue Score showed the strongest positive correlation with Burn Rate.
- Resource Allocation also showed a strong positive correlation with Burn Rate.
- Designation showed a positive correlation with Burn Rate.
- The Random Forest model achieved an R² score of 0.9042 on the validation split.

**Correlation values from the dataset analysis:**

| Feature | Correlation with Burn Rate |
|---|---:|
| Mental Fatigue Score | 0.945 |
| Resource Allocation | 0.856 |
| Designation | 0.738 |

*Correlation indicates association, not causation.*

## Project Structure

```text
Employee-Burnout-Prediction/
│
├── train.csv
├── test.csv
├── sample_submission.csv
├── employee_burnout_model.pkl
├── burnout_predictions.csv
├── Employee_Burnout_Prediction.ipynb
└── README.md
```

*Adjust the filenames above to match the files in your actual GitHub repository.*

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repository-name.git
```

### 2. Navigate to the Project Folder

```bash
cd Employee-Burnout-Prediction
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter
```

### 4. Launch Jupyter Notebook








# Employee_Burnout_Prediction
Machine Learning project that predicts employee burnout levels using Random Forest Regression. Includes data preprocessing, exploratory data analysis, visualization, model training, and evaluation using MAE, RMSE, and R² metrics.
