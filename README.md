# canya-node-build-container

NodeJS and npm container image setup to deploy CanYa angular 5+ applications with GitLab CI/CD

## Create a new Docker image

#### Prerequesites

- [Docker](https://docs.docker.com/install/#releases)

#### Build

```
docker build --squash . -t registry.gitlab.com/canyacoin/node-build-container:X.X # <----- set the tag version plus one
```

Take note of the built imageID

#### Push

```
docker push registry.gitlab.com/canyacoin/node-build-container:X.X <----- set the tag version from the squash step
```

## Running locally

```
docker run -it --entrypoint /bin/bash <imageID>
```
