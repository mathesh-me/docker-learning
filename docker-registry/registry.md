## Docker Registry
- Docker Registry is a storage system for Docker images.
- When we use `docker pull nginx` command, It pulls the nginx image from the Docker Registry.
- Docker Registry is a repository for Docker images.
- The Naming convention of Image in registry is username/imagename:tag.
- If we use `docker pull nginx` command, It is actually search as nginx/nginx image in the Docker Registry.
- If the username is not specified, It will search as library/nginx image in the Docker Registry.
- If we use only nginx as image name the docker will asume as nginx/nginx image.

### Private Registry
- We can create our own private registry.
- We can use GCCR(Google Cloud Container Registry) or ECR(Elastic Container Registry) or ACR(Azure Container Registry) or Docker Hub Registry.

### Other Option for Private Registry
- We can also create our own private registry using docker registry image.
- We can use `docker run -d -p 5000:5000 --restart=always --name registry registry:2` command to create a private registry.
- We can use `docker tag nginx localhost:5000/nginx` command to tag the nginx image.
- We can use `docker push localhost:5000/nginx` command to push the nginx image to the private registry.
- We can use `docker pull localhost:5000/nginx` command to pull the nginx image from the private registry.

Date of Learning: 08/01/2024