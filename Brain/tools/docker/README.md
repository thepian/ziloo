Building & Testing with Docker
==============================

The following can be done from the top talki project directory.

> docker build -f ../../tools/docker/rust.Dockerfile -t thepia/talki-firmware-builder:1.0  -t thepia/talki-firmware-builder:latest --target rust --build-arg TARGETPLATFORM=linux/arm/v7 .

> docker buildx build -f ../tools/docker/rust.Dockerfile --platform linux/arm/v7 .

To build an app like subcognition

> cd awareness/subcognition
> docker run --rm -it -v ../../`PWD`:/opt/talki --name talki-firmware-builder -p 8080:80/tcp thepia/talki-firmware-builder:latest

To run the helloworld do:

> docker cp talki-firmware-builder:/opt/talki/subcognition .


> cd tools/docker
> docker compose build --build-arg TARGETPLATFORM=linux/arm/v7
> docker compose up

> cd .
> docker run --rm -it -v `PWD`:/opt/talki --name talki-firmware-builder -p 8080:80/tcp /bin/sh


```
docker buildx create --name v831-builder --platform linux/arm/v7
docker buildx use v831-builder
docker buildx inspect --bootstrap
```