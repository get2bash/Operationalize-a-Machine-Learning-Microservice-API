# docker-container


##Docker container for running dockerfiles

1: creating a python3 vartual environment = python3 -m venv ~/.<ENVIRONMENT NAME>
2: activating the vertual environment = source ~/.<ENVIRONMENT NAME>/bin/activate
3: creating automated alias = nano ~/.bashrc ==>> alias <ENVIRONMENT NAME> = "cd /home/ec2-user/environment/<FOLDER NAME> && source ~/.<ENVIRONMENT NAME>/bin/activate 
4: activating the alias = source ~/.bashrc
5: activate the vartual environment = <ENVIRONMENT NAME>
6: create = Makefile, Requirements.txt, Dockerfile and configure CircleCI