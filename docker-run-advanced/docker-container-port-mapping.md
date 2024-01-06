## Docker container Port Mapping:

- Normally, We have two options to access the container one is to access within the container and another one is to access from outside the container. If we want to access the container from outside the container then we have to use port mapping. For example, if we want to access the container from outside the container then we have to use command like `docker run -p 8080:80 nginx`. Here, we are mapping port 80 of the container to port 8080 of the host machine. So, we can access the container from outside the container using port 8080. If we want to access the container within the container then we have to use command like `docker run -it nginx`. Here, we are accessing the container within the container. So, we can access the container using port 80.

### For accessing the service within the container:

- To find the ip-address of the container, use the below command:
```
docker inspect <container-id> | grep "IPAddress"
```

- Format
```
ip-address of your container:port-number
```

### For accessing the service from outside the container:

- First we have to map the port of the container to the port of the host machine. To map the port of the container to the port of the host machine, use the below command:
```
docker run -p <port-of-host-machine>:<port-of-container> <image-name>
```

- Format:
```
ip-address of your host machine:port-number
```

Date of Learning: 06/01/2024

