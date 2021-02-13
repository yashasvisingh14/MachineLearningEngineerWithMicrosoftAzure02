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
![AD](https://user-images.githubusercontent.com/64837491/107640181-ea32ee80-6c97-11eb-8c5a-611818ddd706.jpeg)

## Steps Involved 
### Automated ML Experiment
I have created an experiment using Automated ML, configured a compute cluster, and used that cluster to run the experiment. The best model summary shows that VotingEnsemble has the highest accuracy of 91.806% compared to others.
The screenshot below shows "Registered Dataset" in ML studio showing the Bankmarketing dataset.
![(1)Dataset](https://user-images.githubusercontent.com/64837491/107563962-b7d9b080-6c07-11eb-9b3a-3c50a0937585.png) 
This picture below depicts the Details tab AutoML experiment status is shown completed. It also has a brief summary of the model which performed well during the run.  
![voting](https://user-images.githubusercontent.com/64837491/107564305-3e8e8d80-6c08-11eb-9ecc-b2facde541df.png)
Here, we can get a detailed description of the best model and various metrics like accuracy, sampling etc.
![voting2](https://user-images.githubusercontent.com/64837491/107564403-5fef7980-6c08-11eb-9c7c-b47cf86833b0.png)
### Deploy The Best Model
After the experiment run completes, a summary of all the models and their metrics are shown, including explanations. We have chose the best model i.e VotingEnsemble to deploy using Azure Container Instance(ACI) and enable Authentication. In Endpoints section, we can check our model's deployment state which shows "healthy" state once the deployment has been successfully done and compute type(ACI) on which it was performed.
![(21)endpt](https://user-images.githubusercontent.com/64837491/107569299-2a4d8f00-6c0e-11eb-9582-6b8c065dc308.png)
### Enable Logging
After the Best Model is deployed, we have enabled Application Insights(=True) and retrieved logs using code.
![20210211_020526](https://user-images.githubusercontent.com/64837491/107569073-e195d600-6c0d-11eb-9a0e-282aac5b1e05.jpg)
The screenshot below shows the scenario after running logs.py script which was edited to enable "Application Insights" through code.
![20210211_021819](https://user-images.githubusercontent.com/64837491/107570482-94b2ff00-6c0f-11eb-9041-32dfd5c2f0bf.jpg)
In details tab of endpoint "Application Insights" has been enabled with REST endpoint.
![(22)insight](https://user-images.githubusercontent.com/64837491/107570099-1a827a80-6c0f-11eb-90fd-6d552afff9d1.png) \
We can also access Application Insights URL to get more insights of the model. After clicking the URL, was can see failed requests, server response time , server requests and availability showing data according to the time.
![(10)req](https://user-images.githubusercontent.com/64837491/107570736-f2dfe200-6c0f-11eb-8bcc-ac9806ae0f5d.png)
### Swagger Documentation
In this step, we have consumed the deployed model using Swagger. Azure provides a Swagger JSON file for deployed models present in same directory. The swagger runs on localhost:9000 showing the HTTP API methods i.e GET and POST and responses for the model. Below, we can see GET method and its responses.
![(17)swaggerdocs](https://user-images.githubusercontent.com/64837491/107571670-3ab33900-6c11-11eb-92f7-6dc71c4b15fa.png)
This is the POST method and its reponses for the model.
![20210211_022819](https://user-images.githubusercontent.com/64837491/107571483-f6279d80-6c10-11eb-91d6-3c0ba171cd9c.jpg)
The swagger runs on the localhost after running swagger.sh and serve.py. Below screenshots gives an overview when both files were running. The swagger.sh downloads the latest swagger container and was running on port 9000.
![20210211_023633](https://user-images.githubusercontent.com/64837491/107572356-2e7bab80-6c12-11eb-8f15-f826656d6dab.jpg)
The serve.py will start a Python server on port 8000.
![20210211_023646](https://user-images.githubusercontent.com/64837491/107572384-3a676d80-6c12-11eb-9809-8d18673ec9ba.jpg)
### Consume Model Endpoints
Once the model is deployed, we have used the endpoint.py script provided to interact with the trained model. The endpoint.py script runs against API producing JSON output(data.json) for model.
![20210211_024551](https://user-images.githubusercontent.com/64837491/107573335-6a634080-6c13-11eb-8082-eb111568caf3.jpg)
### Create, Publish and Consume Pipeline
The Jupyter Notebook is uploaded to Azure ML studio and the pipleline has been created. We got a bankmarketing dataset with AutoML module in graph section. The steps runs was shown by 'Use RunDetails Widget' in the notebook. Below we have pipeline section of ML studio showing that pipeline has been created.
![(25)run](https://user-images.githubusercontent.com/64837491/107573690-dc3b8a00-6c13-11eb-9311-a70339f4b369.png)
In the same pipeline section we can find the pipeline endpoint.
![(27)piperun](https://user-images.githubusercontent.com/64837491/107573762-fbd2b280-6c13-11eb-9cbd-36375df446ba.png)
This shows graph where bankmarketing dataset is connected with AutoML module.
![(26)automldataset](https://user-images.githubusercontent.com/64837491/107573878-173dbd80-6c14-11eb-9942-9bb0fe2d2223.png)
In Endpoint section, we have pipeline endpoint where we can find published pipeline overview.
![new6](https://user-images.githubusercontent.com/64837491/107860142-a8ef3a00-6e63-11eb-974b-ff5fd7ad5208.png)
![new4](https://user-images.githubusercontent.com/64837491/107860095-75141480-6e63-11eb-8bbc-976e51cb8077.png)
![new1](https://user-images.githubusercontent.com/64837491/107859533-2c0e9100-6e60-11eb-8282-14b7ad7a6156.png)
![(32)final](https://user-images.githubusercontent.com/64837491/107574424-b367c480-6c14-11eb-86f2-c0676b0dfab9.png)
## Improvements in Future
For this particular project, I have used certain configuration settings for computer cluster and specific parameters for model given in the lab. By changing certain parameters and settings we can get more effective models resulting in much better accuracy. I believe that we can observe and explore the dataset also to yield better results. 
## Screen Recording
[Screen Recording](https://www.youtube.com/watch?v=ygbqysfLBRo&t=7s) \
NOTE - I was not able to directly screen cast so I recorded it






