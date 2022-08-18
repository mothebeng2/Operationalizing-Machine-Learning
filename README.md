# Project: Operationalizing Machine Learning

This project is part of the Udacity Machine Learning Engineer with Microsoft Azure Nanodegree. The goal of this project was to configure a cloud-based machine learning production model, deploy it, and consume it. We also create, publish, and consume a pipeline.

## Architectural Diagram
The architectual diagram below helps visualize the flow of project operations from start to finish with its various stages that are critical to the overall flow. 
<img width="553" alt="Project Arch" src="https://user-images.githubusercontent.com/111194883/185315666-316a5476-6b73-4187-8b04-7ef44beef3f0.PNG">

Project main steps:
Authentication
Automated ML Experiment
Deploy the best model
Enable logging
Swagger Documentation
Consume model endpoints
Create and publish a pipeline
Documentation






## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

1.Authentication: The goal of this step was to create a Security Principal (SP) which will be used to interact with the Azure Workspace. Because i was using the Udacity provided lab this step was not created.

2.Automated ML Experiment : The next step was to create a new Automated ML expirement using the registered dataset. As indicated by figure 1 the BankMarketing Dataset was registered which was then used to run the completed Automated ML Job indicated in figure 2 using a Standard_DS12_v2 for the Virtual Machine and 1 as the minimum number of nodes cluster. The Best model from the run was the Voting Emsemble which was produced using a primary metric AUC as displayed in Figure 3.

Figure 1 Registered Dataset
![Dataset](https://user-images.githubusercontent.com/111194883/185324234-ab30185b-0ed4-41a3-927e-1f752da4672f.png)

Figure 2 Completed Auto ML Experiment 
![automl run complete](https://user-images.githubusercontent.com/111194883/185325353-deea48d8-60b9-40ef-8658-da84fce5dc0b.png)

Figure 3 Best Model after expirement 
![automl showing best model](https://user-images.githubusercontent.com/111194883/185330839-110334ce-ec19-4964-b1cf-5dcfc9237b50.png)

3.Deploy the best model : THis step deployed the best model from the previous Auto ML experiement to interact with the HTTP API service . In this one we first selected the best model which was the Voting Emsemble Then the next stage was to deploy the best model using a Azure Container Instance with Authentication turned enabled which is indicated in Figure 4.

Figure 4 Best model with deploy status being succeeded
![best automl model](https://user-images.githubusercontent.com/111194883/185333608-6485085b-ab2b-42c7-bf07-880b3a0eb41c.png)

4.Enable logging : On this step we produced Logging to assist in monitoring the deployed model. This was done by running code in Python SDK and used to also enable application Insights. As displayed below in Figure 5 Endpoints section in Azure ML Studio, showing that “Application Insights enabled” says “true”. Logging was also enabled by running the provided logs.py script as seen in Figure 6

Figure 5 Showing Application Insights as True
![Application Insights True](https://user-images.githubusercontent.com/111194883/185334804-54082d91-d9e9-4e41-8356-83a4467ff1d3.png)

Figure 6 Logging
![logs](https://user-images.githubusercontent.com/111194883/185335672-0bbbd77c-5d3f-4b3a-b140-16e9e038b1af.png)
![logs1](https://user-images.githubusercontent.com/111194883/185335756-4cf49223-f07d-4f9b-9023-cd3550d0b9d4.png)
![logs3](https://user-images.githubusercontent.com/111194883/185335900-7f86aaca-f205-42d9-af06-d05fbcde65e1.png)

5.Swagger Documentation : In this step, we consume the deployed model using Swagger. This process is displayed in the following figure 7
Figure 7 Swagger Documentation
![swagger](https://user-images.githubusercontent.com/111194883/185338444-0c53c97d-5b3a-453c-8061-b06483bb7482.png)
![swagger1](https://user-images.githubusercontent.com/111194883/185338532-d811527e-a158-428c-8432-973468762ca9.png)
<img width="762" alt="swagger site" src="https://user-images.githubusercontent.com/111194883/185338630-d85693fa-5509-4c6c-a949-62b38c1464ac.PNG">
<img width="755" alt="swagger site 2" src="https://user-images.githubusercontent.com/111194883/185338779-9e3bb006-1837-497f-99a5-135e7d1e3937.PNG">

6.Consume model endpoints : After successful deployment, we consumed the model endpoints to enable us to interact with the endpoint using some test data. Once the model is deployed, use the endpoint.py script provided to interact with the trained model. This is shown in the figure 8 below

Figure 8 Consuming the Model endpoint
![Endpoint](https://user-images.githubusercontent.com/111194883/185339308-ccbdf1b1-7125-401a-8b8f-54b24d53599c.png)
![Endpoint1](https://user-images.githubusercontent.com/111194883/185339493-9f4f7b0a-2169-493b-9d0f-f776c1e4cb0f.png)

7.Create and publish a pipeline : In this step, we automate this workflow by creating a pipeline with the Python SDK.For this part of the project, we used the Jupyter Notebook provided in the starter files. The process is displayed by the screenshots below.

![Pipeline](https://user-images.githubusercontent.com/111194883/185343833-f42cf3c2-ceb0-4e35-a7c4-a1a7892a1ee0.png)
![Pipeline Endpoint](https://user-images.githubusercontent.com/111194883/185344102-b36e10f2-9dbc-466c-b12d-a7f844d1a8c2.png)
![pipeline Status and REST](https://user-images.githubusercontent.com/111194883/185343967-1137c43f-d4af-4901-a155-48166179f937.png)
![RunDetails Widget Runs](https://user-images.githubusercontent.com/111194883/185344233-22c21889-da13-4b50-8689-40d7032c923b.png)
![Pipeline showing REST and Status](https://user-images.githubusercontent.com/111194883/185344469-ed7c70d2-12b3-4acd-b7ba-5b110d7cf31f.png)

## Screen Recording
Here is a link to the Project Screencast: https://youtu.be/BRxOtYcSBes

