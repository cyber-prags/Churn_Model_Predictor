# Churn Model Predictor: RevWorks24 Employee Retention Analysis

## Introduction
Welcome to the **Churn Model Predictor** project, an end-to-end HR Data Analytics initiative designed to tackle the challenges of employee retention at RevWorks24, a fictitious leader in the software industry. This project is a response to the strategic shift brought about by the appointment of a new CEO, who is keen on understanding and mitigating employee turnover. My role was to collaborate closely with the Human Resources Department to delve into the reasons behind employee churn and gauge the general sentiment among the workforce.

## Problem Statement
As the new CEO of RevWorks24 began reshaping the company's vision, a critical issue was brought to the forefront: **Why are employees leaving, and how can we encourage them to stay?** This question led us to embark on a journey through data analytics, exploring key factors contributing to employee turnover and identifying potential areas for intervention.

## Technologies & Tools
- **Google BigQuery**: For robust data storage and complex querying.
- **Google Colab**: For executing Python notebooks and data analysis.
- **AutoML (PyCaret)**: For efficient and effective predictive modeling.
- **LookerStudio**: For creating insightful and interactive dashboards.

## Directory Structure
- `/data/`: Contains primary datasets `tbl_hr_data.csv` and `tbl_new_employees.csv`.
- `Pilot_Analysis_Employee_Churn.ipynb`: The Python notebook where the prediction algorithm was developed.

## Project Journey

### Data Collection
Working with the HR Department, I acquired two essential datasets, `tbl_hr_data.csv` and `tbl_new_employees.csv`, which provided the basis for our analysis.

### Data Preprocessing
1. **Integration with Google BigQuery**: Uploaded datasets to Google BigQuery.
2. **Data Consolidation**: Combined the datasets into a single, unified dataset for analysis.
3. **Connection to Google Colab**: Linked Google Colab to BigQuery, converting tables into DataFrames for further processing.

### Model Building
Utilized AutoML from PyCaret, focusing on identifying the most effective model for our needs.

```python
# PyCaret Model Setup
from pycaret.classification import setup, compare_models

setup(df, target='Quit_the_Company', 
      session_id=123,
      ignore_features=['employee_id'],
      categorical_features=['salary','Departments'])

compare_models()
```
## Key Findings
- **Job Satisfaction**: Identified as a critical determinant in predicting employee turnover.
- **Duration & Engagement**: Length of service and project involvement significantly impact retention.
- **Work-Life Dynamics**: The balance between work hours and performance evaluations influences churn.
- **Unexpected Insights**: Incidences like work accidents were found to have minimal impact on turnover decisions.

## Strategic Recommendations
1. **Employee Recognition Program**: To acknowledge and reward employees, thereby enhancing job satisfaction.
2. **Professional Development**: Programs aimed at encouraging employee growth and development to boost retention.
3. **Retention Incentives**: Offering special benefits to long-serving employees to foster loyalty and commitment.

## Reporting & Visualization
Our insights were encapsulated in an interactive dashboard created in LookerStudio, providing a clear, comprehensive view of our analysis.

### Dashboard Link
Explore the LookerStudio Dashboard: https://lookerstudio.google.com/reporting/10c071dd-f431-4607-b104-5f37bbeb6e0f

## Conclusion
The Churn Model Predictor project illuminates the complex dynamics of employee turnover at RevWorks24. Our analysis has yielded actionable insights and strategies designed to elevate employee satisfaction and retention, perfectly aligning with the company's new leadership goals.

