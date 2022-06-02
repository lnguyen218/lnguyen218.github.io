---
title: Build Docker Image and Push to Container Registry
date: 2021-08-11 11:29:00 -500
categories: [docker]
tags: [docker,build]
---
Docker build should include the docker container registry within its tag
```shell
docker build . \
  -t $DOCKER_CONTAINER_REGISTRY/$APP_NAME:latest \
  -t $DOCKER_CONTAINER_REGISTRY/$APP_NAME:$(git rev-parse --short HEAD) \
  --build-arg NODE_ENV=production
```
Push image to container registry
```shell
docker push $DOCKER_CONTAINER_REGISTRY/$APP_NAME:$(git rev-parse --short HEAD)
```
