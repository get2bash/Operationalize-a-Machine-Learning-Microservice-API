# Operationalize a Machine Learning Microservice API

[![CircleCI](https://dl.circleci.com/status-badge/img/gh/get2bash/Operationalize-a-Machine-Learning-Microservice-API/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/get2bash/Operationalize-a-Machine-Learning-Microservice-API/tree/main)

## Final Project for Udacity Cloud DevOps Nanodegree!
### The goal of this project is to Operationalize a working, machine learning microservice using kubernetes, which is an open-source system for automating the management of containerized applications

    - Environment creation and activation
    1: creating a python3 vartual environment = python3 -m venv ~/.<ENVIRONMENT NAME>
    2: activating the vertual environment = source ~/.<ENVIRONMENT NAME>/bin/activate
    3: creating automated alias = nano ~/.bashrc ==>> alias <ENVIRONMENT NAME>="cd /home/ec2-user/environment/<FOLDER NAME> && source ~/.<ENVIRONMENT NAME>/bin/activate"
    4: activating the alias = source ~/.bashrc
    5: activate the vartual environment = <ENVIRONMENT NAME>
    6: create = Makefile, Requirements.txt, Dockerfile and configure CircleCI
    
    - Package installation
    1: install packages in the requirements.txt = make install
    2: install hadolint = sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3/hadolint-Linux-x86_64 && sudo chmod +x /bin/hadolint
    3: download minikube = curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    4: install minikube = sudo install minikube-linux-amd64 /usr/local/bin/minikube
    5: download kubectl = curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
    6: install kubectl = sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

