## Docker Container Volume Mount:

### How it helps?
If we want to store the data of the container in the host machine then we have to use volume mount. For example, if we want to store the data of the container in the host machine then we have to use command like `docker run -v /home/ubuntu:/data ubuntu`. Here, we are storing the data of the container in the host machine. So, we can access the data of the container from the host machine.

### How to use it?
Use the below command to store the data of the container in the host machine:
```
docker run -v <path-of-host-machine>:<path-of-container> <image-name>
```

Date of Learning: 06/01/2024