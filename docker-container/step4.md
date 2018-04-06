Last but not least, the network.

For comparison, run `hostnamectl`{{execute}} to see our current host name, although I think you already see it in the command line prompt.

Then we take a look at how it is in a container: `docker run alpine:latest hostname`{{execute}}

A container has its own host name, which by default is a random hash string (a unique ID of the container). That sounds like an isolated network namespace, doesn't it? Here's how you can see more evidences of that:

`ip add`{{execute}}

`docker run alpine:latest ip add`{{execute}}

`netstat`{{execute}}

`docker run alpine:latest netstat`{{execute}}

(From Wikipedia)

> Network namespaces virtualize the network stack. On creation a network namespace contains only a loopback interface.

> Each namespace will have a private set of IP addresses, its own routing table, socket listing, connection tracking table, firewall, and other network-related resources.

[Read more about network namespaces][wiki-netns]

[wiki-netns]: https://en.wikipedia.org/wiki/Linux_namespaces#Network_(net)
