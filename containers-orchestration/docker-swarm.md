## Docker Swarm

- Docker Swarm is a clustering and scheduling tool for Docker containers. With Swarm, IT administrators and developers can establish and manage a cluster of Docker nodes as a single virtual system. Swarm mode also provides a fault-tolerant mechanism in which services can continue running uninterrupted if a node fails.

- Docker Swarm is a container orchestration tool, meaning that it allows the user to manage multiple containers deployed across multiple host machines. Docker Swarm pools together several Docker hosts and exposes them as a single virtual Docker host. It serves the standard Docker API, so any tool that already communicates with a Docker daemon can use Swarm to transparently scale to multiple hosts.

- We have two create two types of nodes in Docker Swarm:
    - Manager Node
    - Worker Node

- Manager node is responsible for the orchestration of the worker nodes. It is also responsible for the orchestration of the services and tasks that are running inside the worker nodes.

- Worker node is responsible for running the services and tasks that are assigned to it by the manager node.

- We have to run the following command to initialize the swarm mode:

    ```bash
    docker swarm init
    ```
- We have to run the following command to create a worker node:

    ```bash

    docker swarm join --token <token> <ip>:<port>
    ```
- We have to run the following command to create a manager node:

    ```bash

    docker swarm join-token manager
    ```

- If we want to crate 100s of Containers, Use the below command on Docker Swarm Manager Node:

    ```bash

    docker service create --replicas 100 <image-name> ## This will create 100 containers and run them in the worker nodes.
    ```

Date of Learning: 09/01/2024