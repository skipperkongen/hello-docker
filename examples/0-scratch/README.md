# Scratch

Dockerfile:

```Dockerfile
FROM scratch
```

There is not much to see here, because `scratch` image is the most basic image that you could possibly build your own Dockerfile from. It is a completely empty image. That means that there is no operating system or nothing inside that can run. To run it, you would need to copy in some machine-executable code that can run without an operating system. We will not be covering how to do that now. Instead we will use this example to cover some Docker command basics.



Here you see arguably the most important Docker command, `FROM`, which tells Docker what other image your image is based on. In this example you have told Docker that your image is based on nothing and so it is essentially a completely empty image. Not super useful. However, you can still build it.

Build the image

```bash
docker build -t hello-docker-scratch .
```

You can see you image with the `docker images` command:

```bash
docker images | grep hello-docker-scratch
```

You can remove the image from your system with the `docker rmi command`:

```
docker rmi hello-docker-scratch
```

Rerun the `docker images` command to see that it is gone:

```bash
docker images | grep hello-docker-scratch
```