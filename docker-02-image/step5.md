Images are built to be shared. Docker Registry is where images are hosted.

1. Register yourself on *[Docker Hub](https://hub.docker.com)*
2. Authenticate with `docker login && DOCKER_ID$(docker info | awk '/^Username:/{print $2}'); `{{execute}}
3. Tag your image properly: `docker tag johnsimage:latest ${DOCKER_ID}/johnsimage:latest`{{execute}}
4. And push your image for sharing: `docker push ${DOCKER_ID}/johnsimage:latest`{{execute}}

Would you like to try someone else's image?

`docker pull <docker-id>/johnsimage:latest`{{execute}}

*Docker Hub* also hosts a lot of official images which are good choices as the base image for your next Dockerized project.
