# Churn Model Predictor: RevWorks24 Employee Retention Analysis

## Introduction
Welcome to the 'Churn Model Predictor' project, an end-to-end HR Data Analytics initiative aimed at assisting RevWorks24, a leader in the software industry, in enhancing employee retention. With a new leadership, our objective was to identify key factors contributing to employee turnover and provide strategic insights for improving employee satisfaction and retention.

## Technologies & Tools
- **Google BigQuery**: For data storage and querying.
- **Google Colab**: For executing Python notebooks and data analysis.
- **AutoML (PyCaret)**: For building predictive models.
- **LookerStudio**: For dashboard creation and data visualization.

## Directory Structure
- `/data/`: Contains `tbl_hr_data.csv` and `tbl_new_employees.csv`, the primary datasets.
- `Pilot_Analysis_Employee_Churn.ipynb`: Python notebook for developing the prediction algorithm.

## Project Overview
The project encompasses a structured approach, from data collection to final reporting:

### Data Collection
Sourced from `tbl_hr_data.csv` and `tbl_new_employees.csv`, provided by RevWorks24's HR Department.

### Data Preprocessing
1. Uploaded to **Google BigQuery**.
2. Combined datasets into a unified view in BigQuery.
3. Connected Google Colab to BigQuery and converted tables to DataFrames.

### Model Building
Utilized AutoML from PyCaret. The setup and comparison of models led to the selection of RandomForestClassifier based on performance.

```python
# Setup the model in PyCaret
from pycaret.classification import setup, compare_models

setup(df, target='Quit_the_Company', 
      session_id=123,
      ignore_features=['employee_id'],
      categorical_features=['salary','Departments'])

compare_models()
