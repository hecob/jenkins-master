# jerkins-master

## Docker image
```
[https://hub.docker.com/_/jenkins/]
```

##Secret key
```
7bdca2074e6c4300ae4f3565d6faef30

This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
```
##Shell
```
docker run -i -t jenkins:latest /bin/bash 
docker exec -i -t jenkins:latest /bin/bash (if container launched)
```
##How to use this image
```
docker run -p 9080:8080 -p 51000:50000 jenkins:latest
This will store the workspace in /var/jenkins_home. All Jenkins data lives in there - including plugins and configuration. You will probably want to make that a persistent volume (recommended):

docker run -p 9080:8080 -p 51000:50000 -v /var/jenkins_home jenkins:latest
This will store the jenkins data in /your/home on the host. Ensure that /your/home is accessible by the jenkins user in container (jenkins user - uid 1000) or use -u some_other_user parameter with docker run.

You can also use a volume container:

docker run --name jenkins-master -p 9080:8080 -p 51000:50000 -v ~/data/jenkins-master:/var/jenkins_home jenkins:latest
Then myjenkins container has the volume (please do read about docker volume handling to find out more).
```

