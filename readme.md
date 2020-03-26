## Buildpacks tutorial

### About this project

This project is cloned from [Spring Pet Clinic](https://github.com/spring-projects/spring-petclinic) and it's purpose is to showcase how [Buildpacks](https://buildpacks.io/) works.

### Requirements

* [`pack` CLI](https://buildpacks.io/docs/install-pack/)
* Docker daemon

### Getting started

First, choose one of the suggested builder from the output of this command:

```
pack suggest-builders
```

As this is a Java application, choose one with a buildpack for Java, for example `cloudfoundry/cnb:bionic`. You could choose a builder from another source or even build your own ([Create a buildpack](https://buildpacks.io/docs/buildpack-author-guide/create-buildpack/) and [Create a builder](https://buildpacks.io/docs/operator-guide/create-a-builder/)).

Once you've chosen a builder, you can build it as follows:

```
pack build <image-name> --builder <builder-name>
```

For example:

```
pack build petclinic:buildpack --builder cloudfoundry/cnb:bionic
```

From the command output you can determine which buildpacks where involved and which layers where rebuilt. Once your image is built, use `docker images` to see it and `docker run -p 8080:8080 --rm <image-name>:<tag>` to run it.

### Documentation

You can access the official Buildpacks documentation [here](https://buildpacks.io/docs/).