# Churn_Model_Predictor

This is an end to end HR Data Analytics Project having made use of Google Cloud Platform(GCP) using Google BigQuery, Google Collab for coding, AutoML from PyCaret for model builing and finally using LockerStudio to build the dashboard.

Technologies used:
BigQuery
Collab
AutoML
LookerStudio for creating dashboards.

Directory Structure:
\data\ -> contains 2 csv files tbl_hr_data.csv and tbl_new_employees.csv as primary datasets.
Pilot_Analysis_Employee_Churn.ipynb -> Python notebook for building our prediction algorithm.

Problem Statement:
We have a company named RevWorks24 (fictitious company) who are market leaders in the software industry. Now a new CEO has been appointed and he wants to make some important changes to the company by retaining the employees of the company for longer periods. He assigns me to work closely with the Human Resources Department to find out what are the primary reasons for employee chruning in the workplace and what is the general sentiment of majority of the employees.

Methodology:

Data Collection: After closely working with the HR Department, they provide me the data in 2 CSV files tbl_hr_data.csv and tbl_new_employees.csv.

Asking the right questions: After meticiously going through the dataset, here are some of the questions that I need to ask the data:
  1. What is causing Employees to Leave?
  2. Who is predicted to Leave(highest probability)?
  3. What departments have the most Churn?

Data Pre-processing:
1. We will make use of Google BigQuery.
2. After uploading the datasets into BigQuery, we create a new view of combining both the datasets into a single dataset on which we will predominantly work on.
3. Next, we open up GoogleCollab where we first connect our GCP account and then to BigQuery.
4. And, then convert our tables to DataFrames for us to work on.

Model Building:
Primary module used for this was AutoML from the PyCaret library.

# setup our model
setup(df, target='Quit_the_Company', 
      session_id=123,
      ignore_features=['employee_id'],
      categorical_features=['salary','Departments'])

compare_models()

![image](https://github.com/cyber-prags/Churn_Model_Predictor/assets/74003758/226a1184-f9af-4b70-96f0-688145a65124)

The model selected RandomForestClassifier as the best performing model and we will use this model for further predictions.

After making the predictions, we write it back to BigQuery as a new table named pilot_predictions as the table containing the predicted labels.

![image](https://github.com/cyber-prags/Churn_Model_Predictor/assets/74003758/7d3b56b0-a7a8-4773-b1c3-32d3906ba500)
Plotting the features according to their importance it was found that satisfaction level was the most important factor leading to churning by far, followed by total time spent in the company and then the number of projects worked on followed by the other factors.

rf_model.feature_names_in_

Next, we create a feature table containing all the features which can be found under \data\feature_table.csv

#Creating the final report.

To present our findings to the relevant stakeholders, we made use of LookerStudio to create our final report by connecting it to Google Big Query.

Key Findings:
The Random Forest model found that the most crucial factor for predicting whether employees will stay or leave a company is their job satisfaction. The longer they've been with the company, the more projects they have, the moderate number of hours they work, and higher their performance evaluations, the more likely they are to stay. Surprisingly, whether or not they had a work accident doesn't seem to have much impact on their decision to stay or leave. This information can help the company focus on improving job satisfaction to retain valuable employees.

Recommendations:
1. Employee Recognition Program: Acknowledging and Rewarding employees boosts job satisfaction and motivation, addressing a key factor in reducing turnover.
2. Professional Development Initiatives: Investing in training and development helps employees grow within the company, increasing their commitment and job satisfaction.

  Retention Bonus Retention Incentives:
  1.Reward Long Term Employees: Offering retention incentives encourages long-term commitment, addressing the importance of time spent with the company.


LookerStudio Link: https://lookerstudio.google.com/reporting/10c071dd-f431-4607-b104-5f37bbeb6e0f
