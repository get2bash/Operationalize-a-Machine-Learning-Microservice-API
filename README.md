[![CircleCI](https://dl.circleci.com/status-badge/img/gh/get2bash/Operationalize-a-Machine-Learning-Microservice-API/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/get2bash/Operationalize-a-Machine-Learning-Microservice-API/tree/main)

# Operationalize a Machine Learning Microservice API

### The goal of this project is to Operationalize a working, machine learning microservice using kubernetes, which is an open-source system for automating the management of containerized applications. Docker container was used to containarize the app and upladed to docker hub, which was later orchestrated by kubernetes cluster.






#### Environment creation and activation
- Creating a python3 vartual environment = `python3 -m venv ~/.<ENVIRONMENT NAME> `
- Activating the vertual environment = `source ~/.<ENVIRONMENT NAME>/bin/activate`
- Creating automated alias = nano ~/.bashrc ==>> `alias <ENVIRONMENT NAME>="cd /home/ec2-user/environment/<FOLDER NAME> && source ~/.<ENVIRONMENT NAME>/bin/activate"`
- Activating the alias = `source ~/.bashrc`
- Activate the vartual environment = `<ENVIRONMENT NAME>`
- Create = Makefile, Requirements.txt, Dockerfile and configure CircleCI

#### Package installation
- Install docker on the instance = `sudo apt install podman-docker (Ubuntu)`
- Install packages in the requirements.txt = `make install`
- Install hadolint = `sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3/hadolint-Linux-x86_64 && sudo chmod +x /bin/hadolint`
- Download minikube = `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
- Install minikube = `sudo install minikube-linux-amd64 /usr/local/bin/minikube`
- Download kubectl = `curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"`
- Install kubectl = `sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl`


#### Building and Pushing Docker image to DockerHub
- Building image = `docker build --tag=<IMAGE NAME> .`
- Checking if the image exist on local = `docker image ls`
- Running the image and opening port = `docker run -p 8000:80 <IMAGE NAME>`
- Assign path = `dockerpath="<DOCKER ID>/<IMAGE NAME>"`
- Login = `docker login && docker tag <IMAGE NAME> $dockerpath`
- Push from path = `docker push $dockerpath`

#### Starting Minikube
- Starting minikube to start a cluster
```bash
minkube start
```

#### Running kubernetes 
- Docker ID/path = `dockerpath="<DOCKER ID>/<IMAGE NAME>"`
- Run the Docker Hub container with kubernetes = `kubectl run <IMAGE NAME> --image=<DOCKER ID>/<IMAGE NAME> --port=80 --labels app=<IMAGE NAME>`
- List kubernetes pods = `kubectl get pods`
- Forward the container port to a host = `kubectl port-forward <IMAGE NAME> 8000:80`

    
#### Details and uses of the files
- Dockefile = contains code for creating and copying the app to a working directory, exposing the required port and starting the application
- Makefile = includes instructions on environment setup and lint tests
- requirement.txt = contains the required dependencies for running the app
- run_docker.sh = contains shell command for running a docker image
- upload_docker.sh = contains shell command to upload docker image to DockerHub
- run_kubernetes.sh = contains shell command to run Kubernetes cluster
- App.py = contains the application sofware code
- make_prediction.sh = contains shell command used in making prediction on the application
