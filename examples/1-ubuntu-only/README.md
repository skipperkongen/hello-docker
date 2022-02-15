# Ubuntu only

Dockerfile:

```Dockerfile
FROM ubuntu:latest
```

The Dockerfile in this directory is based on the public Ubuntu image (latest version). `FROM ubuntu:latest` means that this Docker image is based on the latest version of the Ubuntu Linux OS image. We have not added anything else to it. 

Next, build the image from the Dockerfile and name it "hello-docker-ubuntu-only", so we can subsequently run it:

```bash
# Build image
docker build -t hello-docker-ubuntu-only .
```

Now, we can run the image "hello-docker-ubuntu-only" image which start an interactive shell (default bash):

```bash
docker run -it hello-docker-ubuntu-only
```

> Puzzle: why does it automatically start `bash` when you run the image? You will get a hint in the next exercise, so hang tight.

When we run the image as a container, it's like running an instance of Linux on your computer's Docker system. Try a few basic Linux commands like `ls`, `ps aux` and `top` and see what happens. You can also navigate around the filesystem with `cd`.

When you are ready to exit the container, type Ctrl-d (or execute the command `exit`).

To remove the image from your local Docker system, run the following command:

```bash
docker rmi hello-docker-ubuntu-only
```

[Next](../2-ubuntu-and-script/)