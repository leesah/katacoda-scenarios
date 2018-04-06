Start an HTTP server in a container `docker run --rm -ti python:latest python -m http.server 80`{{execute}}, and visit port `80` on the host ([click here](https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/)).

> Note how Docker pulls an image when its not found locally.

It's no surprise that it failed because we know our HTTP server is running in a network namespace that is inaccessible from outside.

That sounds secure, very much. But wait, that also sounds a bit... useless. Why would I start a service no one can reach?
