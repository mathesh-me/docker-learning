## Docker Storage

### Where does Docker store the data?

- Docker stores the data in the below location:
```
/var/lib/docker
```
- Inside the above location, we have the below folders:
```
aufs
containers
image
network
volumes
```
- Docker stores container related data in /var/lib/docker/containers folder.
- Similarly, Docker stores image related data in /var/lib/docker/image folder.

### Docker Layered Architecture:

- When we create a Image docker create Each Layer for Ecah Instruction in Docker file.
- Each layer will have its own size.
- This layers are called as Image Layers.
- When we create a container from the image, Docker will create a container layer on top of the image layer.
- This container layer is called as Container Layer.
- Image layer is read-only layer. Whereas, Container layer is read-write layer.
- When we want to change the data, Let'say to modify our application code, Before save the canges , Docker will create a duplicate of this file in the container layer. All the Modification will be done in the file in container layer.

### How Image Layer Caches the Data?

- When we want to create another image, But it's is very similar to Previous Image the application code is the only change. So, Docker will create a new image layer with the application code and it will use the previous image layer for the remaining data.
- This is how Docker caches the data.
- But, remember that if we have a 10 layers in our image and if we change date in fifth layer docker only uses the data cache until fourth layer. It will not use the data cache from fifth layer.

### Problem in Container Layer:

- Docker stores all the data in conatiner layer. So, If the Container is deleted then all the data will be lost.
- So, If we want to store the data in the host machine then we have to use Volume Mount.

### What is Volume Mount?

- We have to create a folder in the host machine and we have to mount that folder to the container.
- Use the below command, it will create data_volume folder insiide the /var/lib/docker/volumes folder.
```
docker volume create data_volume
```
- Use the below command to mount the data_volume folder to the container:
```
docker run -v data_volume:/var/lib/mysql mysql 
#This is called as Volume Mount
```
- If we didn't create the data_volume folder in the host machine then Docker will create the data_volume folder in the host machine by running the above command.
- If we already have some data of our application in host and we want to store that data in the container then we have to use the below command:
```
docker run -v /data/mysql:/var/lib/mysql mysql
#This is called as Bind Mount
```

### Instead of -v we can use --mount:

- We can use --mount instead of -v.
- Use the below command to mount the data_volume folder to the container:
```
docker run --mount source=data_volume,target=/var/lib/mysql mysql
```

### Storage Driver:

- Docker uses storage driver to manage the storage.
- We can check the storage driver by using the below command:
```
docker info | grep -i storage
```
- We can change the storage driver by using the below command:
```
dockerd --storage-driver=devicemapper
```
- Different types of storage drivers are:
```
aufs
devicemapper
overlay
overlay2
ZFS
BTRFS
vfs
```

Date of Learning: 09/01/2024



