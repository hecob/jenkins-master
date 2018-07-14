# jerkins-master

## Docker image
```
[link](https://hub.docker.com/_/jenkins/)
```

## Secret key
```
7bdca2074e6c4300ae4f3565d6faef30

This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
```
## Cheatsheet
```
docker run -i -t jenkins:latest /bin/bash 
docker exec -i -t jenkins:latest /bin/bash (if container launched)
```
## How to use this image
```
cd ~
mkdir data
mkdir jenkins-master

docker run --name jenkins-master -p 9080:8080 -p 51000:50000 -v ~/data/jenkins-master:/var/jenkins_home jenkins:latest

```
## Add new node
```
agent: jenkins-slave
```
