# Docker guide

## Table of contents

- [What is Docker](#what-is-docker)
- [Docker command-line interface](#docker-command-line-interface)
    - [Docker images](#docker-images)
    - [Docker containers](#docker-containers)
- [Dockerfile](#dockerfile)
- [References](#references)

## What is Docker

[Docker][ref-docker-overview] is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker's methodologies for shipping, testing, and deploying code, you can significantly reduce the delay between writing code and running it in production.

This guide is a minimalist guide with just some information to work with Docker. For more details regarding installation, documentation, and other information about this tool please consult the [References](#references) section of this guide.

## Docker command-line interface

Docker has an extensive list of commands that can be used when working with it via [command-line interface][ref-docker-cli]. To see the help information of any Docker command just execute the command, followed by the `--help` option, as shown on the following example using the `docker run` command:

```sh
$ docker run --help
```

Below are some Docker commands that are frequently used.

### Docker images

Build image:

```sh
$ docker build . -t <image_name>
```

List images:

```sh
$ docker images
```

Remove image:

```sh
$ docker rmi <image_name>
```

### Docker containers

Run container:

```sh
$ # Create without naming the container
$ docker run -it <image_name>
$ # Create naming the container
$ docker run -it --name <container_name> <image_name>
$ # Create and remove the container in the end
$ docker run -it --rm <image_name>
$ # Create naming the container and mount some directory in the container
$ docker run -it --name <container_name> -v <source>:<target> <image_name>
```

List containers:

```sh
$ docker ps -a
```

Start container:

```sh
$ docker start -i <container_name>
```

Stop container:

```sh
$ docker stop <container_name>
```

Execute a command inside of container:

```sh
$ docker exec -it <container_name> <command>
```

Remove container:

```sh
$ docker rm <container_name>
```

## Dockerfile

Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. Please consult the [Dockerfile reference][ref-docker-dockerfile] documentation to know all the supported instructions in a Dockerfile.

This [Dockerfile](./Dockerfile) is an example to build a Docker image, in this case more focused on C++ development environment.

## References

- [Docker Home][ref-docker-home]
- [Docker overview][ref-docker-overview]
- [Docker documentation][ref-docker-doc]
- [Docker reference documentation][ref-docker-reference-doc]
- [Docker manuals][ref-docker-manuals]
- [Docker command-line interface][ref-docker-cli]
- [Dockerfile reference][ref-docker-dockerfile]

[ref-docker-home]: https://www.docker.com/ "Docker Home"
[ref-docker-overview]: https://docs.docker.com/get-started/docker-overview/  "Docker overview"
[ref-docker-doc]: https://docs.docker.com/ "Docker documentation"
[ref-docker-reference-doc]: https://docs.docker.com/reference/ "Docker reference documentation"
[ref-docker-manuals]: https://docs.docker.com/manuals/ "Docker manuals"
[ref-docker-cli]: https://docs.docker.com/reference/cli/docker/ "Docker command-line interface"
[ref-docker-dockerfile]: https://docs.docker.com/reference/dockerfile/ "Dockerfile reference"
