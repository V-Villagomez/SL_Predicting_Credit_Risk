# Supervised Machine Learning Challenge - Predicting Credit Risk

I will build a machine learning model that attempts to predict whether a loan from LendingClub will become high risk or not. 

## Background

LendingClub is a peer-to-peer lending services company that allows individual investors to partially fund personal loans as well as buy and sell notes backing the loans on a secondary market. LendingClub offers their previous data through an API.

I will be using this data to create machine learning models to classify the risk level of given loans. Specifically, I will be comparing the Logistic Regression model and Random Forest Classifier.

## Steps

### Retrieve the data

In the `Generator` folder in `Resources`, there is a [GenerateData.ipynb](/Resources/Generator/GenerateData.ipynb) notebook that will download data from LendingClub and output two CSVs: 

* `2019loans.csv`
* `2020Q1loans.csv`

I will be using an entire year's worth of data (2019) to predict the credit risk of loans from the first quarter of the next year (2020).

Note: these two CSVs have been undersampled to give an even number of high risk and low risk loans. In the original dataset, only 2.2% of loans are categorized as high risk. To get a truly accurate model, special techniques need to be used on imbalanced data. Undersampling is one of those techniques. Oversampling and SMOTE (Synthetic Minority Over-sampling Technique) are other techniques that are also used.

## Preprocessing: Convert categorical data to numeric

Create a training set from the 2019 loans using `pd.get_dummies()` to convert the categorical data to numeric columns. Similarly, create a testing set from the 2020 loans, also using `pd.get_dummies()`. Note! There are categories in the 2019 loans that do not exist in the testing set. I'll need to use code to fill in the missing categories in the testing set.

## Consider the models

I will be creating and comparing two models on this data: a logistic regression, and a random forests classifier. 

## Fit a LogisticRegression model and RandomForestClassifier model

Create a LogisticRegression model, fit it to the data, and print the model's score. Do the same for a RandomForestClassifier. 

## Revisit the Preprocessing: Scale the data

The data going into these models was never scaled, an important step in preprocessing. Use `StandardScaler` to scale the training and testing sets.

Fit and score the LogisticRegression and RandomForestClassifier models on the scaled data. 

## Model Training Analysis

Following the training of scaled data, the Logistic Regression model performed better than the Random Forest Classifier model by 10%. Compared to the previous results on unscaled data, the Logisitc Regression's accuracy improved from approximately 52% to 67%, thats over 10% increase in accuracy. In addition, the Random Forest Classifier model decreased in accuracy from approximately 62% to 57%, a 5% decrease in accuracy. 

## Rubric

[Unit 19 - Supervised Machine Learning Homework Rubric](https://docs.google.com/document/d/1f_eN3TYiGqlaWL9Utk5U-P491OeWqFSiv7FIlI_d4_U/edit?usp=sharing)

### References

LendingClub (2019-2020) _Loan Stats_. Retrieved from: [https://resources.lendingclub.com/](https://resources.lendingclub.com/)

- - -

© 2021 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
