# Ubuntu and script

Dockerfile:

```Dockerfile
FROM ubuntu:latest

ENTRYPOINT /bin/bash

CMD while true; do echo 'Hello world'; sleep 1; done
```

Now, we will try to add some code to the image. The `ubuntu` image comes with `bash` preinstalled and by default uses `bash` as the entrypoint when you run the image. Here, we have included the `ENTRYPOINT` command for clarity and so you can understand what happens. But actually, it is not necessary.

The next line after `ENTRYPONT` begins with `CMD`. This is the argument passed to whatever executable is listed under the entrypoint. In combination,
the two commands mean that the following will be executed by Docker when it run the image in a container:

- Run container
- Start `bash`
- Run the command `while true; do echo 'Hello world'; sleep 1; done` (forever)

You can try to type the following in your computer's terminal, assuming you're running Mac OS X or Linux:

```bash
while true; do echo 'Hello world'; sleep 1; done
```

To build the image, run the `docker build` command in terminal:

```bash
# Build image
docker build -t hello-docker-ubuntu-and-script .
```

Now, run the image you just created:

```bash
docker run hello-docker-ubuntu-and-script
```

You now should now see the words "Hello world" repeated again and again in the terminal where you ran the docker command.

To stop running the container, hit Ctrl-c and to remove the image from your local Docker system, run the following command:

```bash
docker rmi hello-docker-ubuntu-and-script
```

