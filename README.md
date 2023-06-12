# PwC-Switzerland-Virtual-Case-Tasks

# TABLE OF CONTENTS :-

- Problem Statement 
- Datasource
- Data Preparation
- Data Modelling
- Data Analysis Expressions(DAX)
- Data Visualization
- Insights

# PROBLEM STATEMENT :-

In this project create a dashboard in Power BI for the call center manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

Possible KPIs include (but not limited to):

- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

# DATASOURCE :-

Dataset used for this task was provided by PwC Switzerland.

Dataset : [Call centre trends](https://github.com/Philomath08/PwC-Switzerland-Virtual-Case-Tasks/blob/main/01%20Call-Center-Dataset.xlsx)

# DATA PREPARATION :-

Completed the Data transformation in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modelling.

Call Center trends dataset has 10 columns and 5000 rows of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary columns and rows
- Removed blank entries
- Each of the columns in the table were validated to have the correct data type

# DATA MODELLING :-

After the dataset was cleaned and transformed, it was ready for data modelling.

- Created new columns and measures.

# DATA ANALYSIS EXPRESSIONS (DAX) :-

Measures used in this visualization are: (** Here 'Sheet1' is dataset)

- Total Agents = DISTINCTCOUNT('Sheet1'[Agent])

- Total Calls = COUNT('Sheet1'[Call Id])

- Total calls answered = CALCULATE(COUNTA('Sheet1'[Answered (Y/N)]),'Sheet1'[Answered (Y/N)]="Y")

- Total calls resolved = CALCULATE(COUNTA(Sheet1[Resolved]),'Sheet1'[Resolved]="Y")

- Count of satisfaction rating = COUNT(Sheet1[Satisfaction rating])

- Positive satisfaction rating = CALCULATE(COUNT(Sheet1[Satisfaction rating]),FILTER('Sheet1','Sheet1'[Satisfaction rating] IN {4,5}))

- Overall Customer Satisfaction % = DIVIDE([Positive satisfaction rating],[Count of satisfaction rating])

- Average of satisfaction = AVERAGE(Sheet1[Satisfaction rating])

- Average of speed of answer = AVERAGE(Sheet1[Speed of answer in seconds])

# DATA VISUALIZATION :-

Dashboard : [Call Centre Trends Analysis](https://github.com/Philomath08/PwC-Switzerland-Virtual-Case-Tasks/blob/main/PWC_Call_centre_task.pbix)

# INSIGHTS :-

THe insights drawn from visualization are :

- Most of the satisfaction ratings are 3 & 4.
- The average satisfaction rating is 3.4
- The average satisfaction rating has decreased over the span of three months. 
- The percentage of issue resolved in January was the highest, with a dip in February. It increased again in March.
- The average speed of answer by Joe is the highest.
- Becky's speed of answer is the lowest among all, and her rate of calls resolved is higher.
- Martha has the highest speed of answered in the sec.

