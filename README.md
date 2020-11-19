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
**This pipeline use Hyperdrive tunning package which is a way to automate search through the parameters you defined to pick the best fitted by experiment multiple combinations between these parameters.
The architecture of this pipeline depends on main steps 
1-Define the parameter: these parameters are put based on the used model or algorithm and here it is a Logistic Regression, the given parameters were c: Inverse of regularization strength and max_iter which is the number of iterations through all classes and then chose the Random sampling method to use over hyperdrive space   
2- Specify a primary metric and here it is Accuracy
3- Specify early termination policy to define when the experiment has to stop looking for answers 
4- submit an experiment with config function 
5- retrieve the best model
In our case the hyperdrive config function use estimator to enter the train.py script.in train file create tabular dataset from the given link and use clean data method to git best possible result and apply split function to divide the dataset to train and test set, main function in train add the arguments to hyperparameter tuning parameters and use fit with classification algorithm then score the model by primary matric and use joblip to store best model in output folder
in the controller file we add random numbers around default value for hyperparameter parameters.**

**What are the benefits of the parameter sampler you chose? chose the random sampling because it more efficient to move randomly over the space than use grid sampling which it has to go through all possible value. Random way allow adding range of parameters and it is better than put specific numbers may they aren’t best choice also, from previous examples comparing between random and grid accuracy were so close and grid method was consuming time so random is best for this experiment to go through more parameter choices with saving time.

**What are the benefits of the early stopping policy you chose? defined after how much certain number of failures the experiment will stop looking for answers and in this case the slack factor which I chose 0.1 and intervals 3 and that mean stop the run and terminate it if its smaller than best run by 91% and 3 is the frequency for applying policy so stopping the failures running allow move to another parameter may it is the better for the model and that save time and resources and rise the experiment efficient **

## AutoML
**In 1-2 sentences, in the AutoML we just need to put the task and prepare the data by clean data and train test split function and specify the target column which is 'y' to expect if the customer subscribe or not and also add compute target to apply the AutoML in the created cluster compute . Print the best run after finishing and retrieve the best model information which is Voting Ensembles that combines the predictions from multiple other models 
 **

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**
the performance of hyperdrive and the automl was close result in accuracy because the chosen parameter and policy were fit and that come after multiple failures by wrong policy factors but with AutoMl the accuracy is better from the first time and the build way is easier and don’t need specifying termination policy or sample parameters 

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**
try using different policy factors or different parameter sampler for hyperdrive to get better results  
