# Predicting Arrest Outcomes in Seattle Terry Stops

## Project Overview

This project analyzes Seattle Terry Stop data using Exploratory Data Analysis (EDA) and Machine Learning techniques to better understand the factors associated with arrest outcomes during police stops.

The analysis focuses on identifying demographic, situational, and operational patterns that influence whether a Terry Stop results in an arrest. The project combines statistical analysis, data visualization, preprocessing, feature engineering, and classification modeling to build predictive models capable of classifying arrest outcomes.

In addition to predictive performance, the project also examines fairness considerations, demographic distributions, and the limitations of applying machine learning to real-world policing data.

---

# Problem Statement

Terry Stops are police stops conducted based on reasonable suspicion of criminal activity. Understanding the factors that influence arrest outcomes during these stops is important for evaluating policing practices, transparency, accountability, and public safety policies.

The goal of this project is to:

- Analyze historical Terry Stop data
- Identify variables associated with arrest outcomes
- Build machine learning models to predict arrests
- Evaluate model performance using appropriate classification metrics
- Explore demographic and operational patterns within the dataset

---

# Project Objectives

The main objectives of this project are:

1. Perform exploratory data analysis on Seattle Terry Stop data
2. Understand demographic distributions and stop characteristics
3. Identify patterns associated with arrest outcomes
4. Preprocess and prepare data for machine learning
5. Train and compare classification models
6. Evaluate model performance using multiple metrics
7. Interpret findings and discuss fairness considerations
8. Provide recommendations based on the analysis

---

# Dataset Description

The dataset used in this project is the Seattle Terry Stops dataset obtained from the Seattle Open Data Portal.

The dataset contains historical records of Terry Stops conducted by law enforcement officers in Seattle.

## Features Included

The dataset contains several important variables, including:

- Arrest Flag
- Subject Perceived Race
- Subject Perceived Gender
- Subject Age Group
- Officer Gender
- Officer Race
- Frisk Flag
- Call Type
- Weapon Type
- Stop Resolution
- Precinct
- Sector
- Officer Year of Birth

---

# Exploratory Data Analysis (EDA)

Exploratory Data Analysis (EDA) was performed to better understand the dataset before machine learning modeling.

The EDA focused on:

- Understanding the target variable distribution
- Identifying class imbalance
- Exploring demographic patterns
- Examining arrest rates across groups
- Investigating relationships between operational variables and arrests
- Identifying missing data and inconsistencies

## Target Variable Analysis

The target variable for this project was:

```python
Arrest Flag
```

Analysis showed that the dataset was heavily imbalanced:

- Non-Arrest (N): 59,542
- Arrest (Y): 7,820

This demonstrated a strong class imbalance problem, meaning most Terry Stops did not result in arrest.

Because of this imbalance, evaluation metrics such as Recall and F1-score became especially important during model evaluation.

---

# Demographic Analysis

## Subject Perceived Race

The analysis showed that Terry Stops were not evenly distributed across racial groups.

The largest categories were:

- White: 32,859
- Black or African American: 20,401

Other racial groups appeared in much smaller proportions, while some records contained missing or unknown race information.

Arrest rate analysis by race revealed variation across groups, although some categories had very small sample sizes that limited statistical reliability.

## Subject Perceived Gender

The dataset showed a strong imbalance toward male subjects:

- Male: 53,119
- Female: 13,449

Other categories such as Unknown and Gender Diverse had very low representation.

## Subject Age Group

The most represented age groups were:

- 26 - 35
- 36 - 45
- 18 - 25

This indicated that Terry Stops were most concentrated among young and middle-aged adults.

---

# Operational and Situational Analysis

Additional analysis explored operational variables related to arrest outcomes.

## Frisk vs Arrest

The relationship between frisk incidents and arrests was examined to determine whether frisked individuals were more likely to be arrested.

## Weapon Type Analysis

Weapon-related variables were analyzed to understand whether weapon presence influenced arrest likelihood.

A significant limitation identified during analysis was the high number of missing or unknown weapon entries.

## Call Type Analysis

Call type analysis revealed differences between officer-initiated stops and dispatched incidents.

Officer-initiated ONVIEW stops appeared frequently in the dataset but showed lower arrest rates compared to dispatched calls.

---

# Data Preprocessing

Several preprocessing steps were performed before modeling.

These included:

- Handling missing values
- Encoding categorical variables
- Feature selection
- Splitting the dataset into training and testing sets
- Scaling or transforming variables where necessary

Categorical variables were converted into numerical representations suitable for machine learning algorithms.

---

# Machine Learning Models

The following classification models were implemented and evaluated:

## 1. Logistic Regression

Logistic Regression was used as a baseline classification model for predicting arrest outcomes.

## 2. Decision Tree Classifier

A Decision Tree model was trained to capture non-linear relationships and improve interpretability.

## 3. Random Forest Classifier

The Random Forest model achieved the strongest predictive performance among the tested models.

Feature importance analysis from the Random Forest model helped identify which variables contributed most strongly to arrest prediction.

---

# Model Evaluation

Due to class imbalance within the target variable, multiple evaluation metrics were used instead of relying only on accuracy.

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

Recall and F1-score were especially important because they provided better insight into the model's ability to correctly identify arrest cases.

The Random Forest classifier achieved the best balance across evaluation metrics.

---

# Key Findings

The project identified several important findings:

- Most Terry Stops did not result in arrests.
- The dataset showed strong class imbalance.
- Terry Stops were heavily concentrated among male subjects.
- White and Black or African American individuals formed the majority of recorded stops.
- Arrest rates varied across demographic groups.
- Weapon presence and call type were among the strongest predictors of arrest.
- Officer-initiated stops appeared frequently but had relatively lower arrest rates.
- Missing data, especially within Weapon Type, affected analysis quality.

---

# Recommendations

Based on the findings from the analysis, the following recommendations were proposed:

1. Review officer-initiated stops to ensure fairness and consistency in stop decisions.
2. Improve weapon data reporting standards to reduce missing or unknown entries.
3. Continue monitoring arrest outcomes across demographic groups.
4. Use machine learning models responsibly and primarily for auditing and reporting purposes.

---

# Limitations

Several limitations affected the project:

- The dataset is observational and cannot establish causal relationships.
- Some variables contained significant missing data.
- Certain demographic categories had very small sample sizes.
- The target variable was heavily imbalanced.
- Some potentially useful variables were not included in the final model.
- Historical policing data may contain existing systemic biases.

These limitations should be considered when interpreting results and model predictions.

---

# Technologies Used

The following technologies and libraries were used:

## Programming Language

- Python

## Data Analysis and Visualization

- Pandas
- NumPy
- Matplotlib
- Seaborn

## Machine Learning

- Scikit-learn

## Development Environment

- Jupyter Notebook
- VS Code

---

# Project Structure

```text
project/
│
├── terry_stops_analysis.ipynb
├── README.md
├── requirements.txt
├── Terry_Stops_20260505.csv
└── presentation.pdf
```

---

# Running the Project

## 1. Clone the Repository

```bash
git clone <repository-url>
```

## 2. Navigate into the Project Directory

```bash
cd project-folder
```

## 3. Install Required Dependencies

```bash
pip install -r requirements.txt
```

## 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

## 5. Open the Notebook

Open the notebook file and run the cells sequentially.

---

# Conclusion

This project demonstrated how exploratory data analysis and machine learning can be used to analyze Terry Stop outcomes in Seattle. The analysis identified important factors associated with arrests, particularly weapon presence, call type, and stop circumstances.

Among the evaluated models, the Random Forest classifier achieved the strongest predictive performance, showing its effectiveness for predicting arrest outcomes. The study also revealed variation in arrest patterns across demographic groups, highlighting the importance of fairness and continued oversight in policing analysis.

Overall, the project provides a data-driven framework that can support policy evaluation, transparency, and future public safety research.