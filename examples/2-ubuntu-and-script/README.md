# Ubuntu and script

Dockerfile:

```Dockerfile
FROM ubuntu:latest

CMD while true; do echo 'Hello world'; sleep 1; done
```

Now, we will try to add some code to the image. When using the `ubuntu` image, whatever you type under CMD will by 
executed by `bash` as a command when you run the image. Here, we are using a small bash-script snippet, which you
could also execute in bash on your own computer (try it). 

```bash
while true; do echo 'Hello world'; sleep 1; done
```

```bash
# Build image
docker build -t hello-docker-ubuntu-and-script .
```

Now, you can create a running container from the "hello-docker-ubuntu-only" image and start an interactive shell (default bash):

```bash
docker run hello-docker-ubuntu-and-script
```

You should now see some output in the terminal where you ran the docker command..

To stop the container, type Ctrl-c. To remove the image from your local Docker system, run the following command:

```bash
docker rmi hello-docker-ubuntu-and-script
```

