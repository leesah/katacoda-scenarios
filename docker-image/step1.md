Start a shell in a container that doesn't die immediately: `docker run -ti alpine:latest ash`{{execute}}

Mind the change of the prompt, you're inside the container now.

Let's make some changes in there, for instance, create a user: `adduser -D johndoe`{{execute}}

We should see Jonh in our `/etc/shadow`: `grep johndoe /etc/shadow`{{execute}}

If everything looks fine, exit the shell (`exit`{{execute}}). This will put the container to `stopped` status, shown as `Exited` if you run `docker ps -l`{{execute}}

Now that we have an ID of the container where we have just made some changes, a docker image can be created as such:

`CONTAINER_ID=$(docker ps -lq)
docker commit ${CONTAINER_ID} johnsimage`{{execute}}

What we just did was "consolidating" the changes we made in that container into a new image, and naming it `johnsimage`,

To list all images available to the Docker daemon, run `docker images`{{execute}}. You should see `alpine` and `johnsimage` sit besides each other.

> Pay attention to the size difference of the two images.
