## Docker Attach and Detach

### Why Docker Attach and Detach?

Normally, when we run a container, it will run in foreground. So, we can see the output of the container. But if we want to run a container in background then we have to use `-d` flag. For example, if we want to run a container in background then we have to use command like `docker run -d ubuntu`. Here, we are running a container in background. So, we can't see the output of the container. If we want to see the output of the container then we have to use `docker attach` command. For example, if we want to see the output of the container then we have to use command like `docker attach <container-id>`.

### How to use Docker Attach and Detach?

Use the below command to run a container in foreground:
```
docker attach <container-id>
```

Use the below command to run a container in background:
```
docker run -d <image-name>
```

Date of Learning: 06/01/2024


