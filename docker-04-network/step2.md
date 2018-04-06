Kill the container (`Ctrl-C`), and start a new one. This time we publish the service to the outer world:

`docker run --rm -ti --publish 80:80 python:latest python -m http.server 80`{{execute}}

Now visit port `80` on the host again ([click here](https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/)).

You should see a list of directories inside the container, which is the default behavior of the HTTP server.

The `--publish` argument of `docker run` publish a container’s port to the host.

Further more, the `--publish` argument allows the port to be remapped upon running, while the program itself doesn't need to know about it.

Try `docker run --rm -ti --publish 8080:80 python:latest python -m http.server 80`{{execute}} and this time visit port `8080` ([click here](https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/)).
