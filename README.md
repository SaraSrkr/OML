# OML
# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
**In 1-2 sentences, explain the problem statement: This dataset contains data about expected customers for bank marketing and it has information about every customer and the last cuolmn with answers yes or no defined the customer subscribed for a term deposit and use two ways to compare between their results"**

**In 1-2 sentences, explain the solution: "The best performing model was a voting enasamble that is created by AutoMl phase where is accuracy matric score 0.915 and the hyperdrive method score 0.912"**

## Scikit-learn Pipeline
**create the workspace and experiment then create cluster compute, in train.py file create tabular dataset from the given link and use clean data method to git best possible result and apply split function to divide the dataset to train and test set, hyperparameter tuning parameters are predefined and add random numbers around default value , and classification algorithm is Logistic Regression .**

**What are the benefits of the parameter sampler you chose? chose the random sampling for the defined parameter and that automate choosing parameters for regression parameter: c ,I chose numbers smaller the default because smaller values specify stronger regularization and the range between 100 and 200 to the maximum number of iterations taken for the solvers to converge  **

**What are the benefits of the early stopping policy you chose? defined how much certain number of failures the experiment will stop looking for answers and in this case the slack factor which I chose 0.1 and intervals 3 and that mean stop the run and terminate it if its smaller than best run by 91% and 3 is the frequency for applying policy**

## AutoML
**In 1-2 sentences, in the AutoML we just need to put the task and prepare the data by clean data and train test split function and specify the target column which is 'y' to expect if the customer subscribe or not and also add compute target to apply the AutoML in the created cluster compute . Print the best run after finishing and retrieve the best model information which is Voting Ensembles that combines the predictions from multiple other models 
 **

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**
the performance of hyperdrive and the automl was close result in accuracy because the chosen parameter and policy were fit and that come after multiple failures by wrong policy factors but with AutoMl the accuracy is better from the first time and the build way is easier and don’t need specifying termination policy or sample parameters 

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**
try using different policy factors or different sample parameters for hyperdrive to get better results  
