`ADD` and `COPY` instructions are used to add files to the image.

Create a text file: `echo "Sex laxar i en lackask." > lackask.txt`{{execute}}

Then update our `Dockerfile` and re-build:

`cat << EOF > ./Dockerfile
FROM alpine:latest
RUN adduser -D johndoe
ADD lackask.txt /home/johndoe/
USER johndoe
WORKDIR /home/johndoe/
CMD cat lackask.txt
EOF
docker build -t johnsimage:auto .`{{execute}}

Let's start a container again and see if it works:

`docker run --rm johnsimage:auto`{{execute}}

> Notice how Docker overwrites an image with the same tag.

Automatic builds are done by the Docker daemon which sometimes run on a remote host. So before the build starts, Docker has to transfer everything in the context directory (specified in `docker build` command) to the daemon.

To avoid unnecessary data transfer, it is recommended to employ `.dockerignore`.

`echo "Herbstskts." > herb.txt
echo lackask.txt > .dockerignore
cat << EOF > ./Dockerfile
FROM alpine:latest
RUN adduser -D johndoe
ADD . /home/johndoe/
USER johndoe
WORKDIR /home/johndoe/
CMD cat *.txt
EOF
docker build -t johnsimage:auto .`{{execute}}
