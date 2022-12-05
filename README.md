# Monisha-CIND-820
## Overview
This project looks at factors affecting COVID-19 hospitalizations of Medicare Beneficiaries in the US from 2020 to 2021, as well as determining a model for predicting hospitalizations and average length of stay at a hospital. The first research question is determining which features from the categorical variables are associated with higher hopsitalization rates using association rule mining. The second question looks at comparing different classification models in predicting high , middle, and low hospitalizations(Random Forest, Multinomial Logistic Regression) and the third question also compares the same classification models, but for the average length of stay in a hospital, which everything being done in R and only the EDA report coded in Python. Some of the commented code are techniques tried to compare the results to other techniques
#### Link to Dataset: 
https://data.cms.gov/covid-19/medicare-covid-19-hospitalization-trends

##  Files Located in Folders titled "final results"
#### Files for problem 1:
CIND-820-Association-rule-mining_3-levels
#### Files for problem 2:
CIND 820 Comparing Classification Models to Predict Hospitalization Numbers Final Results
#### Files for Problem 3:
CIND-820-AVG_los-Comparing-classification-models
## Stages of the of the Project
### Data Preprocessing
The Data Preprocessing included dropping some columns, replacing NA's with the median grouped by the Year and Month, and converting the year datatype from integer to factor. For problem 1 concatenated the Year and Month column. I also removed outliers and compared those results to the results with outliers for Questions 2 and 3. For Questions 1 and 2 and 3 I converted the dependent variables to categorical because the techniques involved a categorical dependent variable and categorized all in 3 levels. 
### Feature Selection
For feature selection, I used first eliminated the columns for events recorded after hospitalization and hospital stay because these dependent variables would not be based on them. Then I used backwards elimination on the rest of the variables to see which ones should be eliminated. in problems 1 and 2, backward elimination did not take out any more variables. For problem 3 when I removed outliers then the variable Total_Bene_Enr_Hosp_Per100K was eliminated by backwards elimination so I also removed that one. 
### Splitting 
Since problem 1 used the assoication rule technique for gathering information, I did not use a split technique for that problem. For problems 2 and 3 I used the test train split technique. This is because it is easier to run and it is easier for me to divide the dataset into 2020 and 2021. I subsetted the 2020 rows into the train set and the 2021 rows into the test set. 
### Balancing Technique.
I balanced the 1st problem using both over sampling and under sampling and compared the results. Since I did not split it into train and test I simply made 2 different dataframes, one with the data over-sampled and one with the data undersampled to compare them. For problem 2 and 3 I used undersampling because it gave similar results to over sampling for problem 1 and can help with increasing efficiency with less rows. 
### Format
For Problem 1 to use association rule mining I first converted the data frame into transaction format
### Models
In Problem 1 I used association rule mining. Problem 2 compared Random Forest Classifiers, Logistic Regression and Naive Bayes, And problem 3 Compared random forest regression and linear regression
### Evaluation
#### Problem 1 Association Rule Mining
For Association Rule mining I chose my important features based on support, lift and confidence values. I chose a lift of greater than 1, support of minimum 0.01 and confidence threshold over 0.55 for the oversampled data and the undersampled data. The results were similar for both sets; Bene_Race_Desc=Non-Hispanic White, Bene_Mdcd_Mdcr_Enrl_Stus=Medicare Only, and Bene_Mdcr_Entlmt_Stus=Aged were common features association with high hospitalizations. 
#### Problem 2 Classification
I used The F1 score, Matthew's correlation coefficient and ROC score to evaluate my models and compare them. Random Forest Classifier had the best results
#### Problem 3 Classfication
I used The F1 score, Matthew's correlation coefficient and ROC score to evaluate my models and compare them. Multinomial logistic regression had better results both they both showed to be inadequate models
