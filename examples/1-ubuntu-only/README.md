# Ubuntu only

Dockerfile:

```Dockerfile
FROM ubuntu:latest
```

The Dockerfile in this directory is based on the public Ubuntu image (latest version) but adds nothing to it. This single line means that this Docker image based on the latest version of the Ubuntu Linux OS image, but without anything else added. 

To run the image, you first need to build and name it. 

Next, you build an image from the Dockerfile and name it "hello-docker-ubuntu-only", so we can run it in the following step:

```bash
# Build image
docker build -t hello-docker-ubuntu-only .
```

Now, you can create a running container from the "hello-docker-ubuntu-only" image and start an interactive shell (default bash):

```bash
docker run -it hello-docker-ubuntu-only
```

This is like running an instance of Linux locally inside your computer's Docker system. Before you quit, try a few basic Linux commands like `ls`, `ps aux` and `top` and see what happens. You can also navigate around the filesystem with `cd`.

To exit the container again, type Ctrl-d.

To remove the image from your local Docker system, run the following command:

```bash
docker rmi hello-docker-ubuntu-only
```

[Next](../2-ubuntu-and-script/)