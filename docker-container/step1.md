## A simple command

First let's run a simplest shell command: `echo "Hello Docker!"`{{execute}}

Now we run the same command again, but with Docker: `docker run alpine:latest echo "Hello Docker!"`{{execute}}

Doesn't look different in anyway, does it? That's how a container is supposed to be, just to wrap and isolate a process, without changing how the process behaves.

But what's the point of all this if running inside a container doesn't make any difference?

In the following steps we're going to run something different, to see a bit more.
