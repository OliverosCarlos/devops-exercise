
# Abraxas DevOps Exercise

Web server developed with python flask and backed with redis to control counter. 

Flask server and Redis DB are hosted on GCP GKE cluster, we are able to update k8s deployment through GitHub Actions.

Visit http://34.173.97.76/ in order to display main message from web server.

![App Screenshot](https://raw.githubusercontent.com/OliverosCarlos/devops-exercise/refs/heads/master/message.png)


Main message is composed of a counter which is incremented when POST method is requested, Please execute request from Postman or any other technology.

```bash
#Postman 
#Select POST method then send request.
http://34.173.97.76/

#Linux
curl -d 'data=empty' http://34.173.97.76/
```

# Reference Architecture

GitHub Actions
- **docker build:** build docker image from Dockerfile, git commit SHA was set as image tag
- **docker push:** docker image will be pushed on Docker Hub ([oliveroscarlos/basic-flask-api](https://hub.docker.com/repository/docker/oliveroscarlos/basic-flask-api/general))
- **Kubernetes Deploy:** Deploy [ks8-deployment-flask.yaml](https://github.com/OliverosCarlos/devops-exercise/blob/master/ks8-deployment-flask.yaml) file to automatically update cluster pods in order review code changes.


![App Screenshot](https://raw.githubusercontent.com/OliverosCarlos/devops-exercise/refs/heads/master/architecture.png)

## Requisitos

- git




## Run

Download GitHub repository

```bash
git clone https://github.com/OliverosCarlos/devops-exercise.git

#or

git clone git@github.com:OliverosCarlos/devops-exercise.git
```

Change Background color of main message (templates/home.html line 16)
~~background-color: #FAFAFA;~~
```bash
<!-- SET Blue background -->
16|          background-color: #0000FF;
```

commit changes and push to master branch in order to update k8s deployment automatically
you can review Github Action workflows.

