# Docker commands basic to Advance:
```
# creating a docker image
docker build -t <image_name> .
```
#### Options: 
-t, --tag  "Name and optionally a tag (format: name:tag)
```
# creating a docker container
docker run -d -p 80:80 --name Nginx-appp nginx-app:latest
```
#### Options:
* -d, --detach  Run container in background and print container ID
* -p,   option is used for port mapping between container and Host machine.
* --name, Option is used to assign a name to the container.



#### Command to run to export a Docker image as a Archive?
```
docker save -o  <output_file_name>.tar 	<image_name>
```

####  Command to run to import a Pre-exported Docker images Into Another Docker Host? 
```
docker load -i  <output_file_name>.tar 	
```

#### Paused Container be removed form Docker?
```
docker rm <container_id> 
```

#### Containers running, paused and stopped ? 
```
docker ps -q | wc -l

docker ps -aq -f   “status=paused” | wc -l
	
docker ps -aq -f “status=exited” | wc -l 
```
* **start  command** # "docker start < container_name>" 

* **stop  command** # "docker stop < container_name>" 

* **kill  command** # "docker kill < container_name>" 

#### docker volumes stored in Docker?
```
Docker volume will be stored on the host machine in the directory “/var/lib/docker/volumes”.
```

#### The Dockerfile supports the following instructions:

**Instruction Description:**
```
ADD			Add local or remote files and directories.

ARG			Use build-time variables.

CMD			Specify default commands.

COPY			Copy files and directories.

ENTRYPOINT	Specify default executable.

ENV			Set environment variables.

EXPOSE		Describe which ports your application is listening on.

FROM			Create a new build stage from a base image.

HEALTHCHECK	Check a container's health on startup.

LABEL		Add metadata to an image.

MAINTAINER	Specify the author of an image.

ONBUILD		Specify instructions for when the image is used in a build.

RUN			Execute build commands.

SHELL		Set the default shell of an image.

STOPSIGNAL	Specify the system call signal for exiting a container.

USER			Set user and group ID.

VOLUME		Create volume mounts.

WORKDIR		Change working directory.

```
### Docker commads;
```
docker save -o  <output_file_name>.tar 	<image_name>     ( Image as an Archieve)
			
docker load -i  <input_file_name>.tar 				     ( Import the image)

**start command** docker start < container_name> 

**stop  command** docker stop < container_name> 

**kill  command** docker kill < container_name> 

# docker run –restart		     (  restart image )				               

# docker rm <container_name>     (  remove image )	

#  docker inspect <image_name>  ( inspect image with details )
```  

#### Docker commands: 

docker ps -a

docker ps -a status=exited

docker rm $(docker ps -qa -f status=exited -q)


Remove all containers:

# docker ps -a

# docker stop $(docker ps -a -q)

# docker rm $(docker ps -a -q) 

********************************************************************************

### Q: Name the Essential Docker Commands: 
```
$ docker version:

$ docker search:

$ docker pull:

$ docker restart: 

$ docker ps

$ docker kill

$ docker login

$ docker commit 

$ docker push

$ docker commit

$ docker network

$ docker history

$ docker rmi 

$ docker ps -a

$ docker logs

$ docker copy

$ docker volume

$ docker logout

$ docker build:        This command will buld the docker image using Dockerfile 	
 
$ docker run:	       This command is used to run the docker iamges as a container 

$ docker ps:           This command will list the running containers in the docker

$ docker exec:         Its helps to execute the commands in running container 

$ docker stop:	       Running container will be stop using this command. 

$ docker system prune:  removel of unused data on inclusion of stopped containers. 
```

