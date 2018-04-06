In Docker, an image serves as a template for creating a container.

With the new image we just created, we can start a container that has all the changes we committed:

`docker run johnsimage grep johndoe /etc/shadow`{{execute}}

We can also start a shell as `johndoe` since it's a valid user in our image: `docker run -ti -u johndoe johnsimage ash`{{execute}}

Why not explore a bit more in this container:

`hostname`{{execute}}

`whoami`{{execute}}

Note where `johnsimage` replaces `alpine:latest`. The `docker run` command takes a Docker image name as the argument, creates a container using it as the template, and passes everything following (`grep johndoe /etc/shadow` in this case) as shell command to the container created. In the previous steps, we've been creating containers from an image called `alpine` (the `latest` revision of it).

Alpine is a Linux distribution that is very popular in the Docker universe. It is chosen as the base image by various Dockerized projects for its simplicity and lightweightness.

(From Wikipedia)

> **Alpine Linux** is a Linux distribution based on musl and BusyBox, ...

[Read more about Alpine Linux][wiki-alpine]

[wiki-alpine]: https://en.wikipedia.org/wiki/Alpine_Linux
