# Ubuntu and script

Dockerfile:

```Dockerfile
FROM ubuntu:latest

CMD while true; do echo 'Hello world'; sleep 1; done
```

Now, we will try to add some code to the image. The `ubuntu` image comes with `bash` preinstalled and by default executes `bash` when you run the image. You can confirm this by looking at the [Dockerfile](https://github.com/tianon/docker-brew-ubuntu-core/blob/8984e91c47abd923cf214fb7232b044106b39337/xenial/Dockerfile#L47) behind the Ubuntu.

Essentially what happens when you run the image is the following:

- Start the container
- Run `bash`
- Execute the command `while true; do echo 'Hello world'; sleep 1; done` (forever)

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

