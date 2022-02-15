# hello-docker
Here we cover some basics of using docker with some simple [examples](./examples).

The conceptual life cycle of Docker:

```
┌─────────────┐              ┌─────────────┐              ┌─────────────┐
│             │              │             │              │             │
│ Dockerfile  │────build────▶│    Image    │─────run─────▶│  Container  │
│             │              │             │              │             │
└─────────────┘              └─────────────┘              └─────────────┘
```

- A *Dockerfile* is just a normal text file, that you can edit with any editor. It's the specification for building an image.
- An *image* is a built version of your Dockerfile prepared for running in Docker. It's a read-only template with instructions for creating a Docker container. Think of it as a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings. It may be based upon other images that provide the basis for extention, e.g. an image for the Ubuntu operating system.
- A *container* is a running instance of an image. From one image you can spin up as many containers as you want

You can think of an image as a layered cake. The bottom layer could be the Ubuntu Linux OS. The middle layer could be some libraries that your application needs to run, but are not included in Ubuntu. The final layer could be your application.

```
# Three-layer Docker image
┌─────────────────────────────┐
│    You application code     │
└─────────────────────────────┘
┌─────────────────────────────┐
│    Additional libraries     │
└─────────────────────────────┘
┌─────────────────────────────┐
│           Ubuntu            │
└─────────────────────────────┘
```

Every line (or command) in your Dockerfile, adds another layer to the cake. 

## Essential commands

Build and tag docker image from `Dockerfile` in same directory:

```bash
# example becomes the tag or name of the image
docker build -t example .
```

Run image in foreground, ctrl-c to quit:

```bash
# You can run local images and remote images (e.g. from Docker Hub)
docker run example
```

List locally stored images:

```bash
docker images
```

List locally running containers:

```
docker ps
```

Get logs from running container:

```bash
docker logs <container ID>
```
