A container can be run connected to a specific network. When multiple containers connect to the same network, the containers share the same network namespace and thus can communicate with each other by means of IP address or name.

One special network worth mentioning here is the `host`. When a container is run with `--network=host`, it runs in the same network namespace as the host does.

`docker run --rm -ti --network=host python:latest python -m http.server 80`{{execute}}

It can be another way to publish our HTTP service to the outside because the port `80` will be bound to the host's network interfaces.

But apparently we'll lose the ability to remap the port, not to mention the isolation Docker is meant to provide.
