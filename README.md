
The special part of the project is to deploy predictive modeling as a microservice to Kubernetes 
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/TanLocc/devOps_microservices_loclpt/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/TanLocc/devOps_microservices_loclpt/tree/main)

# Project Overview
this project is a Machine Learning Microservice API.
This project aims to implement a pre-trained, sklearn model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. Model predictions (inference) about housing prices through API calls. 

## Project Tasks
Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

### Setup the Environment

* You can use a local machine or create a virtual environment by following these steps:
  - Create a virtual machine by EC2 service on AWS
  - Install python 2.7 (need to let cloud9 install the necessary packages when connecting to).
  - Install python 3.7 and nodejs with latest version (need to install packages for microservices).
  - Use cloud9 to connect to the virtual machine just created above to easily deploy and manage microservices.

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies
* Install docker
* Install minikube
* Install kubectl 

#### Running 
Note: You need modify run_docker.sh anh upload_docker.sh to push image to dockerHub repo of you.
1. Standalone:  `python app.py`
2. Run in Docker:  
    -  run `./run_docker.sh` to implement microservice as container
    -  After run `./make_prediction.sh` to make prediction, see output like content of docker_out.txt
3. Run in Kubernetes:  `./run_kubernetes.sh`
    - `./run_kubernetes.sh` to implement microservice as container in pod on kubernetes
    - Waitting few minute, After run `./make_prediction.sh` to make prediction, see output like content of kubernetes_out.txt