## Jenkins

#### 1. Open terminal and Run the following command
```
dariamartinovskaya@MacBook-Air-Daria ~ %  docker run -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts 
09657c0a327eff7a37857255d09297ace5696d534a3c535a019a6e64b13c4ec1
```
#### 2. Run the DOCKER PS command to list the process ID
```
dariamartinovskaya@MacBook-Air-Daria ~ % docker ps 
CONTAINER ID   IMAGE                 COMMAND                  CREATED          STATUS          PORTS                                              NAMES
09657c0a327e   jenkins/jenkins:lts   "/usr/bin/tini -- /u…"   36 seconds ago   Up 35 seconds   0.0.0.0:8080->8080/tcp, 0.0.0.0:50000->50000/tcp   suspicious_panini
```

