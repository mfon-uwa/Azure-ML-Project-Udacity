# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
**In 1-2 sentences, explain the problem statement: e.g "This dataset contains data about... we seek to predict..."**

-- This dataset is related to a bank marketing campaign, it contains about 32950 records × 21 attributes (20 independent attributes (X values) & 1 Target (the y value)).
our objective is to predict the 'y' (potential customers that are likly to subscribe to their product).

**In 1-2 sentences, explain the solution: e.g. "The best performing model was a ..."**

-- The dataset was cleaned and transformed, splitted into train and test sets. A logistic regression model was define and submitted to an experiment. With a maximium of 16 runs, all completed with same model score of 0.91 though with diffenent hyperparameter values.

## Scikit-learn Pipeline
**Explain the pipeline architecture, including data, hyperparameter tuning, and classification algorithm.**

-- The Scikit-learn pipeline is made up of Azure ML objects: a Workspace, ComputeTarget, and Experiment. It also includes Machine learning task like: - 
    1. Data preparation -  This include importing the dataset, cleaning, and transformation, as well as spliting the dataset into train and test sets. 
    2. Model Training - The model was trained using Logistic regression with two hyperparamters(Regularization Strength and Max iterations).
    3. Model Evaluation - Accuracy was selected as the primary metric for scoring the model.
    

**What are the benefits of the parameter sampler you chose?**

-- 1. **max_iter:** This indicate the maximum iterations it took for the model to converged.

-- 2. **C:** a positive float that indicate an inverse strength of regularization.

**What are the benefits of the early stopping policy you chose?**

-- Early stopping policy is efficient, as it conserves resources and saves time by exiting runs (training of the model) that are unlikely to produce a better model than those generated from previous runs.

## AutoML
**In 1-2 sentences, describe the model and hyperparameters generated by AutoML.**
-- The best model Accuracy score is 0.9167, VotingEnsemble algorithm

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**

-- 1. **Accuracy:** There is no much difference in the accuracy from the two model(AutoML best model accuracy = 0.9167 while Hyperdrive = 0.91

-- 2. **Performance:** Hyperdrive run took 20m 30.80sec for maximium of 16 runs, 1 algorithm,  while AutoML total duration was 32m 38.55sec, 16 algorithms. In this regard, I will conclude that the AutoML pipeline performance is better.

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**

-- 1. Feature engineering.
-- 2. Since this a binary classification problem, we can consider other metric like AUC instead of accuracy.

