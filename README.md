# Terry Stop Arrest Outcome Prediction: A Comprehensive Analysis

## Executive Summary
This project analyzes data from the Seattle Police Department (SPD) regarding "Terry Stops"—temporary detentions based on "reasonable suspicion." The primary objective is to build a machine learning classification model to predict whether a stop will result in an arrest (`Arrest Flag`). 

By identifying the strongest predictors of arrest, this analysis provides the **Seattle City Council’s Public Safety Committee** with data-driven insights to audit for potential racial disparities and optimize police oversight.

---

## 1. Business Problem
Terry Stops are a critical juncture in policing where an officer's observation meets legal enforcement. The central policy questions addressed are:
* **Consistency:** Are arrest outcomes driven primarily by situational evidence (e.g., weapon presence, call type)?
* **Equity:** Do demographic factors (subject race/gender) play a statistically significant role in the likelihood of arrest even after situational factors are accounted for?

---

## 2. Data Understanding
The analysis utilizes the Seattle Police Department Terry Stops dataset.
* **Dataset Size:** 67,362 records.
* **Target Variable:** `Arrest Flag` (Binary: Yes/No).
* **Class Imbalance:** Only ~11.6% (7,820) of stops resulted in an arrest, creating a significant "needle-in-a-haystack" challenge for predictive modeling.

### Key Features Analyzed:
* **Demographics:** Subject Age Group, Perceived Race, Perceived Gender.
* **Officer Data:** Officer ID, Race, Gender, and Squad.
* **Contextual Data:** Call Type (911 vs. On-view), Weapon Type, Frisk Flag, and Precinct.

---

## 3. Technical Methodology

### A. Data Cleaning & Preprocessing
- **Null Handling:** Placeholder characters (e.g., "-") were converted to `NaN`. 
- **Imputation:** Given that 93% of `Weapon Type` data was missing, these were categorized as "Unknown" rather than dropped, to preserve the statistical integrity of the larger dataset.
- **Encoding:** Categorical variables were transformed using `LabelEncoder`.
- **Scaling:** Applied `StandardScaler` to ensure the model was not biased by numeric ranges.

### B. Exploratory Data Analysis (EDA)
- **Racial Disparity:** Analysis revealed that Native Hawaiian/Pacific Islander and Black subjects experience higher arrest rates compared to White subjects following a stop.
- **Initiation Type:** Stops initiated via 911 dispatch show a 16.2% arrest rate, while officer-initiated "On-view" stops show a lower rate of 10.3%.

### C. Modeling Approach
Three classification algorithms were rigorously tested:
1.  **Logistic Regression:** Established a baseline for interpretability.
2.  **Decision Tree:** Tuned via `GridSearchCV` for optimal depth.
3.  **Random Forest (Final Model):** Chosen for its superior handling of class imbalance and high recall (78%) for the arrest class.

---

## 4. Key Findings & Insights
* **Top Predictors:** Subject Age Group, Call Type (911 vs. On-view), and Weapon Presence were the strongest indicators of arrest.
* **Demographic Weight:** Perceived race remained a mid-tier predictor in the Random Forest model, indicating that demographics influence outcomes even when situational variables are held constant.
* **The "On-View" Gap:** The lower arrest rate for officer-initiated stops suggests higher levels of discretion, identifying a primary area for administrative review.

---

## 5. Strategic Recommendations
1.  **Standardize Weapon Reporting:** Address the reporting gaps in weapon data to improve predictive precision.
2.  **Audit Officer Discretion:** Focus oversight resources on "On-view" stops, where the threshold for reasonable suspicion is most subjective.
3.  **Focused Equity Training:** Direct resources to precincts where demographic signals show the highest predictive weight in arrest outcomes.

---

## 6. How to Use This Repository
1.  **Environment:** Ensure Python 3.8+ is installed.
2.  **Dependencies:** Install via `pip install pandas scikit-learn matplotlib seaborn`.
3.  **Run:** Open `terry_stops_index.ipynb` and execute cells sequentially.

---
*Authored by the Data Science Audit Team for the Seattle Public Safety Committee.*
