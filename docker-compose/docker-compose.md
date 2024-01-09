## Docker-Compose

### What is Docker-Compose?
Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application's services. Then, with a single command, you create and start all the services from your configuration.

### Why Docker-Compose?
- Let's Consider a scenario of stack of services like a web application using a database, cache, and a web front end.
- Multiple isolated environments on a single host.
- So, If we Create Containers for each service, It means we run conatiners separately for each service.
- In this case, How services communicate with each other?
- How to manage all these containers?
- So, we have to link all these Conatainers.
- We can link conatainers using this Command `docker run --link <container_name>:<alias>`.
- But, This is not a good way to link containers.
- So, Docker-Compose is a tool we can use to link containers.

### Docker-Compose Commands

#### docker-compose up
- This command is used to start the containers.
- If the containers are not present, It will create the containers and start them.
- If the containers are already present, It will start the containers.
- If we want to start the containers in detached mode, We can use `-d` flag.
- If we want to start the containers in detached mode and build the images, We can use `-d --build` flag.

#### docker-compose down
- This command is used to stop the containers.
- If we want to stop the containers and remove the containers, We can use `-v` flag.
- If we want to stop the containers and remove the containers and remove the images, We can use `-v --rmi all` flag.

#### docker-compose ps
- This command is used to list the containers.

#### docker-compose logs
- This command is used to view the logs of the containers.
- If we want to view the logs of the containers in detached mode, We can use `-f` flag.

#### docker-compose exec
- This command is used to execute commands in the containers.
- If we want to execute commands in the containers in detached mode, We can use `-d` flag.

#### docker-compose config
- This command is used to view the docker-compose.yml file.

#### docker-compose images
- This command is used to view the images of the containers.

#### docker-compose top
- This command is used to view the processes of the containers.

#### docker-compose pause
- This command is used to pause the containers.

#### docker-compose unpause
- This command is used to unpause the containers.

#### docker-compose restart
- This command is used to restart the containers.

#### docker-compose start
- This command is used to start the containers.

#### docker-compose stop
- This command is used to stop the containers.

#### docker-compose kill
- This command is used to kill the containers.

#### docker-compose rm
- This command is used to remove the containers.

#### docker-compose pull
- This command is used to pull the images of the containers.

#### docker-compose build
- This command is used to build the images of the containers.

#### docker-compose up --scale
- This command is used to scale the containers.

#### docker-compose events
- This command is used to view the events of the containers.

#### docker-compose port
- This command is used to view the ports of the containers.

#### docker-compose version
- This command is used to view the version of the docker-compose.

#### docker-compose help
- This command is used to view the help of the docker-compose.

### Docker-Compose File
- Docker-Compose file is a YAML file.
- Docker-Compose file is used to configure the services.
- Docker-Compose file is used to manage the containers, networks, volumes, and images.

### Docker-Compose File Syntax

#### version 1

```yaml
version: '1'
web:
  image: nginx:latest
  ports:
   - "5000:5000"
  volumes:
   - .:/code
  links:
   - redis
redis:
    image: redis:latest
```

#### version 2

- In version 2, We can use `services` instead of `web` and `redis`.

```yaml
version: '2'
services:
  web:
    image: nginx:latest
    ports:
     - "5000:5000"
    volumes:
     - .:/code
    links:
     - redis
  redis:
      image: redis:latest
```

#### version 3

- In version 3, We don't need to use `links` because it automatically creates a network for the services.

```yaml
version: '3'
services:
  web:
    image: nginx:latest
    ports:
     - "5000:5000"
    volumes:
     - .:/code
    links:
     - redis
  redis:
      image: redis:latest
```

### If the Images are not availables in Docker Hub, we have to create our own images.

- In this case, we have to create a separate folder and create a application files, Dockerfile in that folder.
- Then, we can use build option in docker-compose file to build the images.

```yaml
version: '3'
services:
  web:
    build: ./web
    ports:
     - "5000:5000"
    volumes:
     - .:/code
    links:
     - redis
  redis:
      image: redis:latest
```

### Networking in Docker-Compose

- In Docker-Compose, We can create a network for the services.

```yaml
version: '3'
services:
  web:
    build: ./web
    ports:
     - "5000:5000"
    volumes:
     - .:/code
    networks:
     - my-network
  redis:
      image: redis:latest
      networks:
       - my-network
networks:
    my-network:
```

Date of Learning: 07/01/2024