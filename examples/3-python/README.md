# Python

Dockerfile:

```Dockerfile
FROM python:3

WORKDIR /usr/src/app

COPY hello.py ./

CMD [ "python", "./hello.py" ]

```

Build image:


```bash
docker build -t hello-docker-python .
```

Run the image as a container:

```bash
#docker run -it hello-docker-python
docker run hello-docker-python
```

Based on the official python3 image on Docker Hub: [https://hub.docker.com/_/python](https://hub.docker.com/_/python)