See the differences when running something in a container than running it "normally".

A process running in a container is isolated in many perspectives:
* Cgroup
* File system
* Network namespace
* etc.

In this scenario we're going to use a docker image called `alpine`.

We'll come to the real meaning of a *image* in a later scenario. For now it should be enough knowing that everything starts with "`docker run alpine:latest`" is run inside a container.
