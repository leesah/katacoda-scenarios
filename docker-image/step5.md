Images are built to be shared. Docker Registry is where images are hosted.

1. Register yourself on *[Docker Hub](https://hub.docker.com)*
2. Authenticate with `docker login`{{execute}}
3. Tag your image properly: `docker tag johnsimage:latest <docker-id>/johnsimage:latest`{{execute}}
4. And push your image for sharing: `docker push <docker-id>/johnsimage:latest`

Would you like to try someone else's image?

`docker pull <docker-id>/johnsimage:latest`

*Docker Hub* also hosts a lot of official images which are good choices as the base image for your next Dockerized project.
