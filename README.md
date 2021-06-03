# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
**In 1-2 sentences, explain the problem statement: e.g "This dataset contains data about... we seek to predict..."**

-- This dataset is related to a bank marketing campaign, contains about 32950 records × 21 attributes (20 independent attributes (X values) & 1 Target (the y value)).
our objective was to build a model that will predict the 'y' (predict potential customers that are likly to subscribe to their product).

**In 1-2 sentences, explain the solution: e.g. "The best performing model was a ..."**

## Scikit-learn Pipeline
**Explain the pipeline architecture, including data, hyperparameter tuning, and classification algorithm.**

-- The Scikit-learn pipeline is made up of Azure ML objects: a Workspace, ComputeTarget, and Experiment. It also includes Machine learning task like: - 
    1. Data preparation -  This include importing the dataset, cleaning, and transformation. The Dataset was splitted into train and test sets. 
    2. Model Training - The model was trained using Logistic regression with two hyperparamters(Regularization Strength and Max iterations).
    3. Model Evaluation - Accuracy was selected as the primary metric for scoring the model.
    

**What are the benefits of the parameter sampler you chose?**

-- 1. **max_iter:** This indicate the maximum iterations it took for the model to converged.

-- 2. **C:** a positive float that indicate an inverse strength of regularization.

**What are the benefits of the early stopping policy you chose?**

-- Early stopping policy is efficient, as it conserves resources and saves time by exiting runs (training of the model) that are unlikely to produce a better model than those generated from previous runs.

## AutoML
**In 1-2 sentences, describe the model and hyperparameters generated by AutoML.**

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**

## Proof of cluster clean up
**If you did not delete your compute cluster in the code, please complete this section. Otherwise, delete this section.**
**Image of cluster marked for deletion**
