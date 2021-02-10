# Operationalizing Machine Learning
## Project Overview
In this project, I have worked with the Bank Marketing dataset. I have used Azure to configure a cloud-based machine learning production model, deploy it, and consume it. I will also create, publish, and consume a pipeline. I have used all the starter_files for this specific project. I have created an experiment using Automated ML and retrieved the best model which was VotingEnsemble that had an accuracy of . Then deployed the best model which will allow to interact with the HTTP API service and interact with the model by sending data over POST requests. \
Dataset - https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv  \
The steps to be followed :-
* Authentication
* Automated ML Experiment
* Deploy the best model
* Enable logging
* Swagger Documentation
* Consume model endpoints
* Create and publish a pipeline \
<img width="626" alt="1" src="https://user-images.githubusercontent.com/64837491/107561712-e2763a00-6c04-11eb-8787-4f5a49b28a17.png">

## Architectural Diagram
Below one can get a glimpse of the architectural flow of the whole project :- \

## Steps Involved 
### Automated ML Experiment
I have created an experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment.


