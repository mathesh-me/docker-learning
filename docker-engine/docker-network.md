## Docker Networking

### Three types of Networks in Docker:

- Bridge Network
- Host Network
- None Network

### Bridge Network:

- Bridge Network is the default network in Docker.
- When we install Docker, Docker will create a bridge network called as docker0.
- When we create a container, Docker will create a virtual ethernet interface called as veth pair.
- One end of the veth pair will be attached to the docker0 bridge network and the other end will be attached to the container.
- In Bridge network, Since it's a private network, Docker will assign a private IP address to the container.
- So containers in the same bridge network can communicate with each other using the private IP address.
- If we want to communicate with the container from outside the host machine then we have to use port forwarding.
- We can create our own bridge network by using the below command:
```
docker network create --driver bridge my_bridge_network
```
- Another way of communicate with conatiners from outside the host machine is to associate the container with the host network.
- We can associate the container with the host network by using the below command:
```
docker run --network host nginx
```
- If we associate the container with the host network then the container will use the host network and it will not have its own network.
- We can check the network of the container by using the below command:
```
docker inspect <container-name> | grep -i network
```
- We can check the IP address of the container by using the below command:
```
docker inspect <container-name> | grep -i ipaddress
```

### None Network:

- None Network is used to create a container without any network.
- We can create a container without any network by using the below command:
```
docker run --network none nginx
```

### Host Network:

- Host Network is used to associate the container with the host network.
- We can associate the container with the host network by using the below command:
```
docker run --network host nginx
```

### Docker user defined network:

- We can create our own user defined network by using the below command:
```
docker network create --driver bridge my_bridge_network
```
- We can check the network by using the below command:
```
docker network ls
```

### How Containers Communicate with each other?

- Normally containers use the containers name to communicate with each other.
- Since, there is a chance of having different ip address for conatainers after boot-up, Docker uses container name to communicate with each other.
- This is done with the help of DNS Server.
- Docker has a built-in DNS Server of IP address 127.0.0.11
- When we create a container, Docker will create a DNS entry for the container in the DNS Server.
- When we ping the container name, Docker will resolve the container name to the IP address of the container.
- We can check the DNS entry of the container by using the below command:
```
docker exec -it <container-name> cat /etc/hosts
```
- We can check the DNS Server by using the below command:
```
docker inspect -f '{{.HostConfig.DNS}}' <container-name>
```

Date of Learning: 09/01/2024