## Network isolation

Start an HTTP server in a container:

`docker run --rm -ti python:latest python -m http.server 80`{{execute}}

> Note how Docker pulls an image when its not found locally.

Switch to the *Web Preview* tab, try to access port `80`.

It's no surprise that it failed because we know our HTTP server is running in a network namespace that is inaccessible from outside.

That sounds secure, very much. But wait, that also sounds a bit... useless. Why would I start a service no one can reach?

## Port publishing

Now kill the container (`Ctrl-C`) and start a new one. This time we publish the service to the outer world.

`docker run --rm -ti --publish 80:80 python:latest python -m http.server 80`{{execute}}

Try accessing port `80` again in the *Web Preview* tab. You should see a list of directories inside the container.

The port publishing allows the port to be remapped upon running, while the program itself doesn't need to know about it.

`docker run --rm -ti --publish 8080:80 python:latest python -m http.server 80`{{execute}}
