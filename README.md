# canya-node-build-container

**Mirror**

This repo is mirrored from the Gitlab master as a backup. Please commit to this:

https://gitlab.com/canyacoin/canyacore/devops/node-build-container
---

NodeJS and npm container image setup to deploy CanYa angular 5+ applications with GitLab CI/CD

## Create a new Docker image

#### Prerequesites

- [Docker](https://docs.docker.com/install/#releases)

Run and start docker locally (using the GUI)

Navigate to the local repo. 

Login to Gitlab: 
```
docker login registry.gitlab.com <--- Enter your gitlab credentials
```
 
<!--Update your $HOME/.docker/config.json to enable experimental mode (for `--squash` feature)-->

<!--```-->
<!--{-->
<!--        "experimental": "enabled"-->
<!--}-->
<!--```-->

#### Build

```
docker build . -t registry.gitlab.com/canyacoin/node-build-container:X.X # <----- set the tag version plus one
```

Take note of the built imageID `X.X`

#### Push

```
docker push registry.gitlab.com/canyacoin/node-build-container:X.X <----- set the tag version from the squash step
```

## Running locally

```
docker run -it --entrypoint /bin/bash <imageID>
```

## Help

https://docs.gitlab.com/ee/user/project/container_registry.html

