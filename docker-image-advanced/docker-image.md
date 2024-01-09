## Docker Image

### What is a Docker Image?

A Docker Image is a file that contains all the necessary dependencies and configurations to run a Docker container. It is a read-only template that is used to create Docker containers. Docker images are built using a Dockerfile.

### What is a Dockerfile?

A Dockerfile is a text file that contains all the commands a user could call on the command line to assemble an image. Using docker build, users can create an automated build that executes several command-line instructions in succession.

### How to create a Dockerfile?

- A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. Using docker build, users can create an automated build that executes several command-line instructions in succession.
- Dockerfile consists of instructions and arguments. Instructions are the commands that are executed by the command line interpreter. Arguments are the values that are passed to the instructions.
- Instructions are not case-sensitive. However, convention is to use uppercase letters for instructions and lowercase letters for arguments.
- Dockerfile must start with the FROM instruction. FROM instruction specifies the base image from which you are building.

#### Dockerfile Instructions

- FROM: Sets the base image for subsequent instructions. You can use a public image or create your own base image.
- MAINTAINER: Sets the author field of the generated images.
- RUN: Executes a command and creates a new layer as a result. RUN instructions are executed when the image is built.
- CMD: Sets the default command to execute when running the container. Only the last CMD instruction executes.
- EXPOSE: Informs Docker that the container listens on the specified network ports at runtime. EXPOSE instructions are not actually published.
- ENV: Sets environment variables.
- ADD: Copies new files, directories, or remote file URLs from <src> and adds them to the filesystem of the image at the path <dest>.
- ENTRYPOINT: Configures a container that will run as an executable.
- VOLUME: Creates a mount point for externally mounted volumes or other containers.
- USER: Sets the user name for following RUN / CMD / ENTRYPOINT commands.
- WORKDIR: Sets the working directory.
- ONBUILD: Adds a trigger instruction when the image is used as the base for another build.
- COPY: Copies new files or directories from <src> and adds them to the filesystem of the image at the path <dest>.
- LABEL: Adds metadata to an image.
- STOPSIGNAL: Sets the system call signal that will be sent to the container to exit.
- ARG: Defines a variable that users can pass at build-time to the builder with the docker build command using the --build-arg <varname>=<value> flag.
- SHELL: Allows the default shell used for the shell form of commands to be overridden.

#### Dockerfile Arguments

- Arguments are values that are passed to the instructions.

#### Example Dockerfile

```dockerfile
FROM ubuntu:latest

RUN apt-get update 
RUN apt-get install -y nginx

CMD ["nginx", "-g", "daemon off;"]
```

#### Dockerfile Working

- Each instruction creates one layer in the image. When you change the Dockerfile and rebuild the image, only those layers which have changed are rebuilt. This is part of what makes images so lightweight, small, and fast, when compared to other virtualization technologies.

- Once, We have created a Dockerfile, we can build an image from it using the docker build command.
```
docker build -t <image_name> <path_to_Dockerfile>
```

- Once, We have created an image, we can run a container from it using the docker run command.
```
docker run -d -p 80:80 <image_name>
```

- Or, We can push the image to Docker Hub using the docker push command.
```
docker push <image_name>
```

Date of Learning: 07/01/2024