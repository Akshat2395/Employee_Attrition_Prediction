# Employee_Attrition_Prediction

## Overview

Attrition is the normal life cycle of employment. Employees who move, retire, pass away or leave the company to raise a family or attend school represent the usual ebb and flow of staffers through a business. In other words, when it comes to attrition, employees are leaving not because they have a problem with your company or their jobs – it’s a matter of life unfolding.


## Project Summary

1. Data preparation

2. Exploratory Data Analysis

3. ML Model Comparisons

4. Improving Performance


## Project Summary

### 1. Data Preparation

**Dataset:** https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset

The dataset provided on the website has already been cleaned for us and has no missing or NAN values. 

The datset includes columns of Attrition, Age, Department, Education, EnvironmentSatisfaction, JobRole, JobSatisfaction, TotalWorkingYears, YearsAtCompany and YearsInCurrentRole to name a few.


### 2. Exploratory Data Analysis

* Relation between Attriton, and Job position and eduation.

<img src="https://github.com/Akshat2395/Employee_Attrition_Prediction/blob/main/images/Attrition-Job-Education.png" width="700" height="600">

In our dataset we have more people related with the Research and Development Area, with mid-high levels of educations, and they are from fields related with Life Sciences and Medicine.

But when we analyze the proportion of attrition in each category, we discover that the education level is not so important as the Education field or the Area. More people working in Marketing, Technical and Human Resouces showed attrition.

* Relation between Attrition and other dependent features

<img src="https://github.com/Akshat2395/Employee_Attrition_Prediction/blob/main/images/Attrition-Temporal.png" width="700" height="600">

W can see that we have 100% attrition of people who have worked more than 40 years. Maybe beacuse at that time, people start to retire and leave.

But, we can also notice an interesting number of people who quit between the 0 and 5 total working years. Maybe we are talking about young proffesionals, who want to aquire experience in different companies.

* Relation between Attrition and people belonging to diferent generations

**Let's see the demographic of different generations**


|Generation | Birth Start | Birth End	| Youngest Age | Oldest Age |
| :-: | :-: | :-: | :-: | :-: |
|The Silent Generation | 1928 | 1945 | 71 | 88 |
|Baby Boomer | 1946 | 1964 | 52 | 70 |
|Generation X | 1965 | 1980 | 36 | 51 |
|Millenials | 1981 | 1999 | 17 | 35 |
|Gen Z | 2000 | 2020 | 0 | 16 |

(*age taken as of year 2016, that's when the data was collected)

<img src="https://github.com/Akshat2395/Employee_Attrition_Prediction/blob/main/images/Attrition-Generations.png" width="700" height="600">

We can see that most employees are in Sales, Research and lab technician. We also notice that millenials are paid less than Gen X and Baby Boomers. This happens due to lack of professional experience. 

* Relation between Attrition and Gender

<img src="https://github.com/Akshat2395/Employee_Attrition_Prediction/blob/main/images/Attrition-Gender.png" width="700" height="600">

After the analysis, we didn't see diferences between gender if we talk about income, job posittions or attrition. Instead of that, we see more men in positions like Laboratory, Sales, Human Resources and Research.

Something to take note, is that the proportion of women is less than men, in the total number of employees by gender.

* Relation between Attrition and Job Features

<img src="https://github.com/Akshat2395/Employee_Attrition_Prediction/blob/main/images/Attrition-Job.png" width="700" height="600">

We can see that attrition happend if the employee is not satisfied with his annual salary and that too at the early stages of their career. Another reason is that the employee is working overtimeas they tend to get worked out and ultimately get tired of working late hours. Environment satisfaction also matters a lot as this leads to dissatisfaction from their job. 


### 3. Machine Learning Implementation

For our classification problem, I have implemented multiple ML models and compared their performances based on their accuracy. For better performance, hyperparameter tuning has been done and used ensemble methods to improve performance. 

I have used cross validation and implemented stratifiedKFold for splitting the training set into 5 folds. cross_val_score from sklearn is used to determine the performance.

**1. Logistic Regression:** 88%

**2. Decision Tree:** 82.2%

**3. Adaboost Classifier:** 82.3% (Ensemble technique with Decision trees)

**4. Gradient Boosting Classifier:** 89.5%

As our dataset is imbalanced, we will try to restore the balance by increasing the number of positive attrition values. 

### 4. Performsnce Improvement - Oversampling 

In this secton, I have used SMOTE as my oversampler to increase the positive attrition values in my training set. 

**Note:** The test set was not touched and it has the same ratio of attrition values as before. It has not been oversampled.

Using our best performing ML model - Gradient Boosting Classifier, it was trained by the new oversampled training set and performed hyperparameter tuning to furthermore improve the performance.

The model ultimately achieved an accuracy of **93.5%**.

Additionally, important features were calculated from the ML model we implemented and the top 5 features were:

1.Stock Option Level

2. Monthly Income

3. Job Satisfaction

4. Years with Current Manager

5. Education Field 



This project was intended to implement multiple supervised ML models on an unbalanced dataset and try to improve it's accuracy. Moreover, I have also tried and tested different ways to do EDA in an experimented manner.
