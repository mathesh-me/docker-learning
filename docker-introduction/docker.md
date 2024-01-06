## What is Docker?
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package. By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code.

## Why Docker?
Docker is a tool that is designed to benefit both developers and system administrators, making it a part of many DevOps (developers + operations) toolchains. For developers, it means that they can focus on writing code without worrying about the system that it will ultimately be running on. It also allows them to get a head start by using one of thousands of programs already designed to run in a Docker container as a part of their application. For operations staff, Docker gives flexibility and potentially reduces the number of systems needed because of its small footprint and lower overhead.

## Docker Editions
Docker comes in two editions: Community Edition (CE) and Enterprise Edition (EE). Docker CE is ideal for individual developers and small teams looking to get started with Docker and experimenting with container-based apps. Docker EE is designed for enterprise development and IT teams who build, ship, and run business-critical applications in production at scale.

## Docker Installation
### Windows
* [Docker Desktop for Windows](https://docs.docker.com/docker-for-windows/install/)

### Mac
* [Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/)

### Linux
* [Docker Engine](https://docs.docker.com/engine/install/)

## How Containers are different from Virtual Machines?
Containers and virtual machines have similar resource isolation and allocation benefits, but function differently because containers virtualize the operating system instead of hardware. Containers are more portable and efficient.

![Containers vs VMs](https://www.docker.com/sites/default/files/d8/2018-11/docker-containerized-and-vm-transparent-bg.png)

## What is Docker Image?
A Docker image is a file, comprised of multiple layers, that is used to execute code in a Docker container. An image is essentially built from the instructions for a complete and executable version of an application, which relies on the host OS kernel. When the Docker user runs an image, it becomes one or multiple instances of that container.

## What is Docker Container?
A Docker container is a runtime instance of a Docker image. Containers are isolated from each other and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels. All containers are run by a single operating system kernel and therefore use fewer resources than virtual machines.

## What is Docker Registry?
A Docker registry is a storage and content delivery system, holding named Docker images, available in different tagged versions.DockerHub is a hosted registry used by default when installing the Docker engine. DockerHub is a public registry that anyone can use, and Docker is configured to look for images on DockerHub by default. DockerHub is a great resource to find images of many popular open source applications, and more are being added daily.

## Docker Architecture
Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface.

![Docker Architecture](https://docs.docker.com/engine/images/architecture.svg)

To know more about Docker, please visit [Docker Documentation](https://docs.docker.com/).

Date of Learning: 05/01/2024