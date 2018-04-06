Start a background task, for instance `dd if=/dev/zero of=/dev/null &`{{execute}}.

Then list all processes with `ps -ef`{{execute}}, as expected, you should see the task running.

Now if we list all processes in a container, will you still see it? `docker run alpine:latest ps -ef`{{execute}}

This ability of process isolation is achieved by means of the cgroups feature. A process running inside a container is isolated in its own group, meaning it cannot see processes outside the group.

(From Wikipedia)

> **cgroups** (abbreviated from **control groups**) is a Linux kernel feature that limits, accounts for, and isolates the resource usage (CPU, memory, disk I/O, network, etc.) of a collection of processes.

[Read more about cgroups][wiki-cgroups]

[Read more about PID namespaces][wiki-pidns]

[wiki-cgroups]: https://en.wikipedia.org/wiki/Cgroups
[wiki-pidns]: https://en.wikipedia.org/wiki/Linux_namespaces#Process_ID_(pid)
