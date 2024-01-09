## Docker Engine

### What is Docker Engine?

- Docker Engine is a client-server application. It has three components:
    - A server which is a type of long-running program called a daemon process (the dockerd command).
    - A REST API which specifies interfaces that programs can use to talk to the daemon and instruct it what to do.
    - A command line interface (CLI) client (the docker command).

### What is Docker Daemon?

- Docker daemon (dockerd) is a persistent process that manages Docker containers and handles container objects. The daemon listens for requests sent via the Docker Engine API.

### What is Docker Client?

- Docker client (docker) is the primary way that many Docker users interact with Docker. When you use commands such as docker run, the client sends these commands to dockerd, which carries them out. The docker command uses the Docker API. The Docker client can communicate with more than one daemon.

### What is REST API?

- REST API in Docker Engine is used to communicate between Docker Client and Docker Daemon.

### Important Note:

- We can also run docker commands on another remote machine by using the below command:
```
docker -H <ip-address-of-remote-machine>:<port-number> <docker-command>
```
- For example, `docker –H=10.123.2.1:2375 run nginx`

### How Docker Engine manage the containerization?

- Docker Engine uses Namespaces and Control Groups to manage the containerization.
- Namespace creates separate PID, Network, Mount, IPC, UTS, and User namespaces for each container.
- Control Groups limits the amount of resources that the container can use.

### Namespaces PID

- When we start our Linux machine it usually starts with root process with PID 1. And after the Booting process completes we wiil have bunch of processes running on our machine. And all these processes will have their own PID. And all these processes will be running
- This also applied to Containers. When we start a container it will have its own PID. And all the processes running inside the container will have their own PID. And all these processes will be running inside the container.
- What happens actually is Container thinks that it have its's own Process. But, What happens is the Process is running on Host Machine with Different PID.

### Control Groups

- We know that the space and resources of the host machine is shared by all the containers. So, we have to limit the amount of resources that the container can use. This is done by Control Groups.
- To limit the amount of CPU that the container can use, we have to use the below command, The below command will limit the amount of CPU that the container can use to 50%.
```
docker run --cpus=.5 ubuntu
```
- To limit memory that the container can use, we have to use the below command, The below command will limit the amount of memory that the container can use to 512MB.
```
docker run --memory=512m ubuntu
```

Date of Learning: 09/01/2024
