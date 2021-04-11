# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
In this first project, we are asked to determine if a client will make a fixed-term deposit or not ("y" label).

The highest precision we got was **0.91** after running a sk-learn model

## Scikit-learn Pipeline
Pipeline:
1. create an instance and launch a VM 'STANDARD_D2_V2' according to project specifications.
2. Once the VM is running, we run a jupyter notebook to access the workspace, create an experiment and run a cluster or create it if it does not exist.

**What are the benefits of the parameter sampler you chose?**
I chose random sampling to prevent the model from running even with errors. This sampling ends in case the model is giving unwanted values.
The values of the hyperparameters are defined by the variables **'--C'** (value of each iteration) and **'--max_iter'** (Maximum number of iterations)

**What are the benefits of the early stopping policy you chose?**
By setting the enable_early_stopping value to true, we enable early termination of the model.
BanditPolicy is used for an "hot stop".

## AutoML
Voting Ensemble was the model that generated the best performance with a 0.91

## Pipeline comparison
**Compare the two models and their performance.**
Both Hyperdrive and AutoML obtained an accuracy of about 0.91.

**What are the differences in accuracy?**
As I mentioned before, I chose the random parameter sampling so, in case of poor performance or error, an early stop can be made.

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**
Obviously I need to experiment with both autoML, scikit-learn or other ML libraries. These are being the first approaches that I make to ML libraries through Azure, so in the future I need to practice this topic more.

