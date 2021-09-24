# Introduction 

A sample project using grade and SpirnBoot. Deployed to target kubernetes cluster using Azure DevOps Pipelines

# Steps

1.	Changes Needed

- Create Azure Service Connection named 'Docker_Hub' -> points to docker hub repo (used in azure-pipelines.yml)
- In azure-pipelines.yml, adjust values for Repo, RepoOrg
- In docker-build-push.yml, adjust values for Repo, RepoOrg
- In /postman_collection/env/DEV.postman_environment.json, adjust value for key BASE_URL -> this should point to URL of deployed services   

2.	Azure DevOps Pipelines

Create following pipelines - 
- Pipeline name 'Digital_EKS' using azure-pipelines.yml -> If a differen name, update azure-pipelines-CD.yml as it should be triggered after this first pipeline
- Another pipeline (any name e.g. CustomerService_Deploy) using azure-pipelines-CD.yml 

This will create a NodePort service at port 30080 e.g. http://<host>:30080/greeting 


3.	To Do

- This project contains Kubernetes configuration file i.e. config. It should be made secure using Azure File Connection 

