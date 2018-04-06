This time we cat the contents in our `/etc/passwd` file: `cat /etc/passwd`{{execute}}

Then we do the same in a container: `docker run alpine:latest cat /etc/passwd`{{execute}}

You guessed right, the results differ. A container has its own file system, again, isolated:

`df`{{execute}}

`docker run alpine:latest df`{{execute}}

Generally speaking, changes we make in a container won't affect the state on the host. This is with some exception, for instance the Volume feature, which we'll cover later.
