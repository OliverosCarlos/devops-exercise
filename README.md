# Abraxas DevOps Exercise

Web server developed with python flask and backed with redis to control counter. 

Flask server and Redis DB are hosted on GCP GKE cluster, we are able to update k8s deployment through GitHub Actions.

# Reference Architecture

GitHub Actions
- **docker build:** build docker image from Dockerfile, git commit SHA was set as image tag
- **docker push:** docker image will be pushed on Docker Hub ([oliveroscarlos/basic-flask-api](https://hub.docker.com/repository/docker/oliveroscarlos/basic-flask-api/general))
- **Kubernetes Deploy:** Deploy [ks8-deployment-flask.yaml](https://github.com/OliverosCarlos/devops-exercise/blob/master/ks8-deployment-flask.yaml) file to automatically update cluster pods in order review code changes.
## Get your environment ready

You'll need:

1. A Github account
2. A docker hub account
3. Access to a kubernetes cluster for testing purposes (It can be Minikube or any other public or private option)
4. Fork this repository, then clone it locally.

## Ready for action?

Great!!
As a DevOps we need you to create a mechanism to deploy nanoservices. You'll be in charge of deploy, monitor, scale applications and promote the DevOps culture with the development team. But let's start by the begining, below you'll find the requirements for this test.

### Dockerize services

Dockerize the given service at [app.py](app.py), including all it's required dependencies installed and ready to rock.

### CI/CD

Implement a Github Actions workflow to build and publish your docker image on [docker hub](https://hub.docker.com/).

### Deployment

Create a service configuration file to deploy the service on your kubernetes cluster and expose it to the world.

### Extra Points

- Improve the given python service so it maintains a counter of the amount of **POST** requests it served, and return it on **GET** requests.

## Deliverables

- A link to the public docker registry where the image is published.

- A link to your repository containing:

    1. The Dockerfile(s) for the image(s).
    2. The kubernetes file(s) for the service deployment(s). The deployment should be replicable on our kubernetes cluster.
    3. Optionally the code for the improved version of the service.

## General Guidelines

Your code should be as simple as possible, yet well documented and robust.
Spend some time on designing your solution. Think about operational use cases from the real world. Few examples:

1. What happens if a service crashes?
2. How much effort will it take to create a new service? D.R.Y!

## Reference

- [Run a Stateless Application Using a Deployment](https://kubernetes.io/docs/tasks/run-application/run-stateless-application-deployment/)

