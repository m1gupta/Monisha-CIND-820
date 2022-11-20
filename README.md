# Monisha-CIND-820
## Overview
This project looks at factors affecting COVID-19 hospitalizations of Medicare Beneficiaries in the US from 2020 to 2021, as well as determining a model for predicting hospitalizations and average length of stay at a hospital. The first research question is determining which features from the categorical variables are associated with higher hopsitalization rates using association rule mining. The second question looks at comparing different classification models in predicting higher vs lower hospitalizations(Random Forest, Logistic Regression and Naive Bayes), and the third question compares regression models(random forest and linear), which everything being done in R and only the EDA report coded in Python. 
## Stages of the of the Project
### Data Preprocessing
The Data Preprocessing included dropping some columns, replacing NA's with the median grouped by the Year and Month, and converting the year datatype from integer to factor. For problem 1 concatenated the Year and Month column. I also removed outliers and compared those results to the results with outliers for Questions 2 and 3. For Questions 1 and 2 I converted the dependent variable to a categorical because the techniques involved a categorical dependent variable. For question 1 I made 2 files, one where I categorized the dependent variable into 3 levels and another where I categorized it into 5 levels.
### Feature Selection
For feature selection, I used first eliminated the columns for events recorded after hospitalization and hospital stay because these dependent variables would not be based on them. Then I used backwards elimination on the rest of the variables to see which ones should be eliminated. in problems 1 and 2, backward elimination did not take out any more variables. For problem 3 when I removed outliers then the variable Total_Mth_Enrl was eliminated by backwards elimination so I also removed that one. 
### Splitting 
Since problem 1 used the assoication rule technique for gathering information, I did not use a split technique for that problem. For problems 2 and 3 I used the test train split technique. This is because it is easier to run and it is easier for me to divide the dataset into 2020 and 2021. I subsetted the 2020 rows into the train set and the 2021 rows into the test set. 
### Balancing Technique.
I only balanced the 1st problem. Since I did not split it into train and test I simply made 2 different dataframes, one with the data over-sampled and one with the data undersampled to compare them. For problem 2 I did not need to balance it because I categorized it into 2 categories from the 50th percentile, so each category was already balanced. Problem 3 did not need balancing because the dependent variable is continuous. 
### Format
For Problem 1 to use association rule mining I first converted the data frame into transaction format
### Models
In Problem 1 I used association rule mining. Problem 2 compared Random Forest Classifiers, Logistic Regression and Naive Bayes, And problem 3 Compared random forest regression and linear regression
### Evaluation
#### Problem 1 Association Rule Mining
For Association Rule mining I chose my important features based on support, lift and confidence values. I chose a lift of greater than 1, support of minimum 0.001 and confidence threshold over 0.8 over the oversampled data and 0.85 for the undersampled data. What I saw was that the features for the model with 3 levels had higher confidence values than model with 5 levels. But a lot of the features chosen for high hospitalization was similar for all versions; Bene_Race_Desc=Non-Hispanic White, Bene_Mdcd_Mdcr_Enrl_Stus=Medicare Only, and Bene_Mdcr_Entlmt_Stus=Aged were common features association with high hospitalizations. 
#### Problem 2 Classification
I used The ROC score to evaluate my models and compare them. Out of the 3 models Random Forest had the highest ROC score and removing outliers increased over not removing them
#### Problem 2 Regression
I compared the models with the R2 and RMSE scores. The results were mixed, with Random Forest Performing Better with certain changes and Linear Regression performing better with certain changes. The model with the best result was Linear regression with 2020-2021 Train_test split and the outliers removed. It performed with an RMSE of 1.732463 and R2 of 0.4457301.
