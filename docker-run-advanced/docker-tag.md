## Docker Image Tag:

- If we use command like `docker run ubuntu` then it will pull the latest version of ubuntu image from docker hub and run it. 
- But if we want to run a specific version of ubuntu image then we have to use tag. For example, if we want to run ubuntu 14.04 then we have to use command like `docker run ubuntu:14.04`. 
- Here `ubuntu` is the image name and `14.04` is the tag name. If we don't specify the tag name then it will pull the latest version of the image.

### Use case of image tag:

- If we want to run multiple containers of same image then we have to use tag. For example, if we want to run 3 containers of ubuntu 14.04 then we have to use command like `docker run ubuntu:14.04` 3 times.

### How we can find version of ubuntu:

- Use the below command to find the version of ubuntu:
```
docker run ubuntu cat /etc/*release*
```

Date of Learning: 06/01/2024