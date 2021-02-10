# Operationalizing Machine Learning
## Project Overview
In this project, I have worked with the Bank Marketing dataset. I have used Azure to configure a cloud-based machine learning production model, deploy it, and consume it. I will also create, publish, and consume a pipeline. I have used all the starter_files for this specific project. I have created an experiment using Automated ML and retrieved the best model which was VotingEnsemble that had an accuracy of 91.806%. Then deployed the best model which will allow to interact with the HTTP API service and interact with the model by sending data over POST requests. \
Dataset - https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv  \
The steps to be followed :-
* Authentication
* Automated ML Experiment
* Deploy the best model
* Enable logging
* Swagger Documentation
* Consume model endpoints
* Create and publish a pipeline 
<img width="626" alt="1" src="https://user-images.githubusercontent.com/64837491/107561712-e2763a00-6c04-11eb-8787-4f5a49b28a17.png">

## Architectural Diagram
Below one can get a glimpse of the architectural flow of the whole project :- 

## Steps Involved 
### Automated ML Experiment
I have created an experiment using Automated ML, configured a compute cluster, and used that cluster to run the experiment. The best model summary shows that VotingEnsemble has the highest accuracy of 91.806% compared to others.
![(1)Dataset](https://user-images.githubusercontent.com/64837491/107563962-b7d9b080-6c07-11eb-9b3a-3c50a0937585.png)
![voting](https://user-images.githubusercontent.com/64837491/107564305-3e8e8d80-6c08-11eb-9ecc-b2facde541df.png)
![voting2](https://user-images.githubusercontent.com/64837491/107564403-5fef7980-6c08-11eb-9c7c-b47cf86833b0.png)
### Deploy The Best Model



