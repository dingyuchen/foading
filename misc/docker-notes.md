# Docker for Local Development Environments
#devops #swe

## Container

A container is a running instance of an image.

### Listing Images

```docker images```

### Listing Containers

```docker container ls -a```

### Removing Containers

```docker rm <container_name>```

### Removing Images

```docker rmi <image_name>```

### Pulling a new Image

```docker pull <image_name>```

### Creating a new container

```docker create -it --name <myfirstcontainer> <image_name>```

`-it` creates an interactive container that can be accessed by the terminal

> Comparable to `docker run -it --name ..` which creates and starts the container in 1 command

### Starting a container

```docker start <myfirstcontainer>```

Conversely,

```docker stop <myfirstcontainer>```

> Attach directly with `docker start -ai <container_name>`

### Accessing (attach) into the container

```docker attach <myfirstcontainer>```

### Building a Container based on Dockerfile

```bash
#!/bin/bash
# this sets up the IMAGE
docker build \
--file=http_server.Dockerfile \
--tag="http_server:0.1" \
. # directory context

docker create \
--interactive \
--tty \
--rm \ # remove container as soon as we exit
--name="http_server" \
--publish-all \ # assign exposed port to an available host port
--mount type=bind, source="$(pwd)/src", target="/home/http_server_user/src" \ # reflect project files in the image, source being host, target being image
http_server:0.1
```

### Running a Custom Container

Append to `deploy.sh` bash file

```bash
docker start http_server
docker port http_server # print port mapping
docker attach http_server # enter container command line
```


