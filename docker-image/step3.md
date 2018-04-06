A lot information is available through the `inspect` command of Docker, for instance, where the `root` file system of our `johnsimage` is stored: `docker inspect johnsimage:latest`{{execute}}

Let's take a deeper look at what's stored in there:

`JOHNSROOT=$(docker inspect -f {{.GraphDriver.Data.RootDir}} johnsimage:latest)
ls ${JOHNSROOT}/etc/`{{execute}}

There are three pairs of files that are interesting to see:

`diff ${JOHNSROOT}/etc/shadow ${JOHNSROOT}/etc/shadow-`{{execute}}

`diff ${JOHNSROOT}/etc/passwd ${JOHNSROOT}/etc/passwd-`{{execute}}

`diff ${JOHNSROOT}/etc/group ${JOHNSROOT}/etc/group-`{{execute}}

> If you run into `command not found` error when running `diff`, install it with `pacman --sync --noconfirm diffutils`{{execute}}.

These are the changes we made when we built this image.
