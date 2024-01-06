## Basic Docker Commands

### Docker Version
```
docker version
```
**Explanation:** This command is used to check the version of Docker installed on your machine.

### Docker Info
```
docker info
```
**Explanation:** This command is used to check the information of Docker installed on your machine.

### Docker Help
```
docker help
```
**Explanation**: This command is used to check the help section of Docker.

### Docker Images
```
docker images
```
**Explanation**: This command is used to check the images of Docker.

### Docker Search
```
docker search <image-name>
```
**Explanation**: This command is used to search for an image on DockerHub.

### Docker Pull
```
docker pull <image-name>
```
**Explanation**: This command is used to pull an image from DockerHub.

### Docker Run
```
docker run <image-name>
```
**Explanation**: This command is used to run an image.

### Docker PS
```
docker ps
```
**Explanation**: This command is used to check the running containers.

### Docker PS -a
```
docker ps -a
```
**Explanation**: This command is used to check all the containers.

### Docker Stop
```
docker stop <container-id>
```
**Explanation**: This command is used to stop a container.

### Docker Start
```
docker start <container-id>
```
**Explanation**: This command is used to start a container.

### Docker Attach
```
docker attach <container-id>
```
**Explanation**: This command is used to attach a container.

### Docker Remove Container
```
docker rm <container-id>
```
**Explanation**: This command is used to remove a container.

### Docker Remove Image
```
docker rmi <image-id>
```
**Explanation**: This command is used to remove an image.

### Docker Remove All Containers
```
docker rm $(docker ps -a -q)
```
**Explanation**: This command is used to remove all the containers.

### Docker Remove All Images
```
docker rmi $(docker images -q)
```
**Explanation**: This command is used to remove all the images.

### Docker Remove All Images and Containers
```
docker rm $(docker ps -a -q) && docker rmi $(docker images -q)
```
**Explanation**: This command is used to remove all the images and containers.

### Docker Exec
```
docker exec -it <container-id> bash
```
**Explanation**: This command is used to execute a container.

Date of Learning: 06/01/2024