## Entrypoint and CMD

- Entrypoint and CMD are instructions that are used to configure a container that will run as an executable.
- Entrypoint and CMD are used together.
- CMD is used to provide default arguments for the entrypoint.
- CMD can be overridden by providing arguments to the docker run command.
- CMD is optional.
- If CMD is not specified, then the default command will be used as arguments to the entrypoint.
- If CMD is specified, then the specified command will be used as arguments to the entrypoint.
- If CMD is specified multiple times, then only the last CMD will take effect.

## CMD

- CMD is used to specify the process that will run when a container is created from the image.
- Example:
    - CMD ["nginx", "-g", "daemon off;"]
    - CMD ["python", "app.py"]
- CMD can be overridden by providing arguments to the docker run command.

## Entrypoint

- Entrypoint is used to specify the executable that will run when a container is created from the image.
- Example:
    - ENTRYPOINT ["nginx", "-g", "daemon off;"]
    - ENTRYPOINT ["python", "app.py"]
- Entrypoint cannot be overridden by providing arguments to the docker run command.

## Use Case Example

- Let's say we run a container from the ubuntu image using the following command:
```
docker run ubuntu sleep 5
```
- The container will run for 5 seconds and then exit.
- **What if whenver we run run container we always want our container to goes to sleep for 5 seconds and then exit?**
- We can use CMD to specify the default command to execute when running the container.
- We can create a Dockerfile as below:
```
FROM ubuntu
CMD ["sleep", "5"]
```
- **What if we want to change the sleep time dynamically?**
- We can entrypoint to specify the executable that will run when a container is created from the image.
- We can create a Dockerfile as below:
```
FROM ubuntu
ENTRYPOINT ["sleep"]
```
- So, We can run the container as below:
```
docker run ubuntu 15
```
- **What if we don't Specify 15 in above Command?**
- It will give error.
- So, In that case We can use entrypoint and CMD together.
- We can create a Dockerfile as below:
```
FROM ubuntu
ENTRYPOINT ["sleep"]
CMD ["5"]
```
- So, We can run the container as below:
```
docker run ubuntu
```
- Entrypoint will append the command `docker run ubuntu` to the command line arguments `ENTRYPOINT ["sleep"]` and then execute the command.
- CMD is used to provide default arguments for the entrypoint.
- CMD can be overridden by providing arguments to the docker run command.

Date of Learning: 07/01/2024