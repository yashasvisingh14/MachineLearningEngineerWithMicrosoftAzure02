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
After the experiment run completes, a summary of all the models and their metrics are shown, including explanations. We have chose the best model i.e VotingEnsemble to deploy using Azure Container Instance(ACI) and enable Authentication. 
![(21)endpt](https://user-images.githubusercontent.com/64837491/107569299-2a4d8f00-6c0e-11eb-9582-6b8c065dc308.png)
### Enable Logging
After the Best Model is deployed, we have enabled Application Insights and retrieved logs using code.
![20210211_020526](https://user-images.githubusercontent.com/64837491/107569073-e195d600-6c0d-11eb-9a0e-282aac5b1e05.jpg)
![20210211_021819](https://user-images.githubusercontent.com/64837491/107570482-94b2ff00-6c0f-11eb-9041-32dfd5c2f0bf.jpg)
![(22)insight](https://user-images.githubusercontent.com/64837491/107570099-1a827a80-6c0f-11eb-90fd-6d552afff9d1.png)
![(10)req](https://user-images.githubusercontent.com/64837491/107570736-f2dfe200-6c0f-11eb-8bcc-ac9806ae0f5d.png)
### Swagger Documentation
In this step, we have consumed the deployed model using Swagger. Azure provides a Swagger JSON file for deployed models. The swagger runs on localhost:9000 showing the HTTP API methods and responses for the model.
![(17)swaggerdocs](https://user-images.githubusercontent.com/64837491/107571670-3ab33900-6c11-11eb-92f7-6dc71c4b15fa.png)
![20210211_022819](https://user-images.githubusercontent.com/64837491/107571483-f6279d80-6c10-11eb-91d6-3c0ba171cd9c.jpg)
![20210211_023646](https://user-images.githubusercontent.com/64837491/107572384-3a676d80-6c12-11eb-9809-8d18673ec9ba.jpg)
![20210211_023633](https://user-images.githubusercontent.com/64837491/107572356-2e7bab80-6c12-11eb-8f15-f826656d6dab.jpg)
### Consume Model Endpoints
Once the model is deployed, we have uses the endpoint.py script provided to interact with the trained model. The endpoint.py script runs against API producing JSON output(data.json) for model.
![20210211_024551](https://user-images.githubusercontent.com/64837491/107573335-6a634080-6c13-11eb-8082-eb111568caf3.jpg)
### Create, Publish and Consume Pipeline
The Jupyter Notebook is uploaded to Azure ML studio and the pipleline has been created. We got a bankmarketing dataset with AutoML module with status completed.
![(25)run](https://user-images.githubusercontent.com/64837491/107573690-dc3b8a00-6c13-11eb-9311-a70339f4b369.png)
![(27)piperun](https://user-images.githubusercontent.com/64837491/107573762-fbd2b280-6c13-11eb-9cbd-36375df446ba.png)
![(26)automldataset](https://user-images.githubusercontent.com/64837491/107573878-173dbd80-6c14-11eb-9942-9bb0fe2d2223.png)
![(28)published](https://user-images.githubusercontent.com/64837491/107574242-7dc2db80-6c14-11eb-92ff-5a9ebcb9900c.png)
![(30)runwidget](https://user-images.githubusercontent.com/64837491/107574321-99c67d00-6c14-11eb-8e9f-1a51525d2525.png)
![(32)final](https://user-images.githubusercontent.com/64837491/107574424-b367c480-6c14-11eb-86f2-c0676b0dfab9.png)









