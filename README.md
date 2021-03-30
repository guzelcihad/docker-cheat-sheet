# Basic Commands
### Run a container
```
docker run <image-name>:<version>
```
### List containers
```
docker ps
```

List all running as well as previously stopped containers.
```
docker ps -a
```

### Stop a container
```
docker stop <container-name-or-id> 
```

### Remove a container
```
docker rm <container-name-or-id> 
```

### Remove all containers at once
```
docker rm $(docker ps -aq)
```

### List images
```
docker images 
```

### Remove images
You should be ensure the container is not running using this image.
```
docker rmi <image-name>
```

### Remove an image if there are multiple versions available
```
docker rmi <repository-name>:<version>
```

### Pull the image
Pulls nginx image without run.
```
docker pull nginx 
```

### Run containers for a while
Some containers don't run forever. For ex: ubuntu image. 
<br>
Run a container for a 5 seconds.
```
docker run ubuntu sleep 5
```

### Execute a command inside the container
Prints the etc/hosts file inside the container
```
docker exec <container-name-or-id> cat /etc/hosts 
```

### Run container attach mode
```
docker run <container-name-or-id>
```

### Run container detach mode
```
docker run -d <container-name-or-id>
```
# Docker Run Commands
### Run a container based on an image and give it a explicit name
```
docker run --name <explicit-name> <image-name>
```

### Port mapping
This command maps traffic comes from port 80 to 5000 port in docker host. We can also create more instances on the same container
```
docker run -p 80:5000 redis
```

### Volume mapping
This commands mount the var/lib/mysql folder to the /opt/datadir folder which exist in the docker host. 
```
docker run -v /opt/datadir:/var/lib/mysql mysql
```

### More info about container
```
docker inspect <container-name-or-id>
```

### Container logs
```
docker logs <container-name-or-id>
```

# Docker Images
### Build docker file
```
docker build . -f Dockerfile -t <image-name>
```
### Push image to registry
```
docker push <image-name>
```

### Environment Variables
We can pass an environment variable to the source code lives in container.
```
docker run -e ENV-VAR-NAME=value <image-name>
```
We can now inspect the variable with:
```
docker inspect <container-name-or-id>
```

# Docker Compose
```
docker compose up
```

