# Refactor-Udagram-App-into-Microservices-and-Deploy

## /feed and /user backends are separated into independent projects:

![Screenshot](./screenshots/Screenshot_1.png)

![Screenshot](./screenshots/Screenshot_2.png)

## Project includes Dockerfiles to successfully create Docker images for /feed, /user backends, project frontend, and reverse proxy:

### Create images successfully from Dockerfiles include:

![Screenshot](./screenshots/Screenshot_5.png)

### And run containers from images:

![Screenshot](./screenshots/Screenshot_6.png)

### On browser:

-FE:

![Screenshot](./screenshots/Screenshot_7.png)

-BE: 

![Screenshot](./screenshots/Screenshot_8.png)

### Screenshot of DockerHub shows the images using CircleCI to run CI/CD instead of TravisCI:

- Screenshot of DockerHub shows the images: 

![Screenshot](./screenshots/Screenshot_10.png)

#### Can access repo docker hub through public url:

-  udagram-frontend : https://hub.docker.com/r/0936064271/udagram-frontend
-  udagram-reverseproxy : https://hub.docker.com/r/0936064271/reverseproxy
-  udagram-udagram-api-feed : https://hub.docker.com/r/0936064271/udagram-api-feed
-  udagram-udagram-api-user : https://hub.docker.com/r/0936064271/udagram-api-user

- CircleCI showing a successful build job:

![Screenshot](./screenshots/Screenshot_11.png)

## A screenshots of kubectl commands show the Frontend and API projects deployed in Kubernetes:

![Screenshot](./screenshots/Screenshot_12.png)


## The output of kubectl get pods indicates that the pods are running successfully with the STATUS value Running:

![Screenshot](./screenshots/Screenshot_13.png)

## The output of kubectl describe services:

- backend-feed:

![Screenshot](./screenshots/Screenshot_14.png)

- backend-user:

![Screenshot](./screenshots/Screenshot_15.png)

- publicfrontend:

![Screenshot](./screenshots/Screenshot_17.png)

- publicreverseproxy:

![Screenshot](./screenshots/Screenshot_18.png)

- kubectl get svc:

![Screenshot](./screenshots/Screenshot_19.png)

## Kubernetes services are replicated. At least one of the Kubernetes services has replicas: defined with a value greater than 1 in itsdeployment.yml file:

- api-feed-deployment:

![Screenshot](./screenshots/Screenshot_20.png)

- api-user-deployment:

![Screenshot](./screenshots/Screenshot_21.png)

- frontend-deployment:

![Screenshot](./screenshots/Screenshot_22.png)

- reverseproxy-deployment:

![Screenshot](./screenshots/Screenshot_23.png)

## Screenshot of Kubernetes cluster of command kubectl describe hpa has autoscaling configured with CPU metrics:

![Screenshot](./screenshots/Screenshot_24.png)