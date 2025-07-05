# Healthcare Analytics: Predictive Modeling for Obesity Diagnosis

## 1. Project Overview
This project performs an in-depth analysis of a synthetic healthcare dataset with the goal of understanding trends and building a predictive model. The core objective is to determine if there is a significant relationship between a patient's age and gender and a diagnosis of obesity.

The project follows a standard data science workflow:
1.  **Data Loading & Initial Exploration:** Understanding the structure and basic statistics of the dataset.
2.  **Data Cleaning & Preprocessing:** Identifying and addressing potential issues such as negative values, duplicates, outliers, and data type inconsistencies.
3.  **Predictive Modeling:** Building and evaluating a logistic regression model to classify obesity diagnoses.
4.  **Analysis & Conclusion:** Interpreting the model's performance and drawing conclusions about the relationships between the variables.

The dataset used for this analysis can be found on Kaggle: [Healthcare Dataset](https://www.kaggle.com/datasets/prasad22/healthcare-dataset?resource=download).

## 2. Data Cleaning and Validation
A thorough data cleaning process was undertaken to ensure the quality and integrity of the analysis. Key steps included:

* **Negative Billing Amounts:** Identified 108 records with negative billing amounts. An analysis of these records showed no significant correlation with other variables like admission type or medical condition, so they were kept in the dataset to avoid biasing the overall distribution.
* **Outlier Detection:** Used Z-scores, the Interquartile Range (IQR) method, and boxplots to investigate outliers in numerical columns. The analysis concluded that no significant outliers were present.
* **Duplicate Records:** Found and removed 534 duplicate rows from the dataset, resulting in a cleaned dataset of 54,966 unique entries.
* **Categorical & Data Type Consistency:** Verified that all categorical columns contained only expected values and converted date columns from `object` to `datetime` type for proper time-based calculations.

## 3. Predictive Modeling & Results

A logistic regression model was built to predict whether a patient had an obesity diagnosis based on their age and gender.

* **Technologies Used:** Python, Pandas, Matplotlib, Seaborn, Scikit-learn
* **Model:** Logistic Regression with `class_weight='balanced'` to account for the imbalanced nature of the dataset.
* **Performance:** The model achieved a baseline accuracy of **~49.5%**.

### Key Insight
The model's accuracy, which is close to random chance (50/50), strongly suggests that **age and gender alone are not significant predictors of an obesity diagnosis within this dataset.** The low precision for the 'obesity' class (0.16) and the insights from the confusion matrix further reinforce this conclusion. This finding highlights a classic data science principle: the initial features selected for a model may not have sufficient predictive power, emphasizing the critical importance of feature engineering and incorporating more relevant variables.

## 4. Learnings & Next Steps
This project served as a comprehensive exercise in the end-to-end data analysis workflow. Key takeaways include the importance of rigorous data cleaning, the necessity of critically evaluating model performance beyond simple accuracy, and understanding how to interpret model results to draw meaningful conclusions.

* **Next Steps:** If I were to continue this project, my immediate focus would be on **feature engineering**. I would incorporate other variables from the dataset (such as Blood Type, Insurance Provider, etc.) to see if a more complex model could achieve higher predictive accuracy. I would also explore other classification algorithms to compare their performance.
