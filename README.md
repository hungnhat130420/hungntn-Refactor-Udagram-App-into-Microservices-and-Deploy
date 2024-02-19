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

### Screenshot of DockerHub shows the images: can access through public url: https://hub.docker.com/r/0936064271/hungntn/tags on tags tab

![Screenshot](./screenshots/Screenshot_9.png)