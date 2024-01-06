## Important note about Containers:

Containers only run as long as the service inside the container is running. If the service inside the container stops, the container will stop.

## Important note about Docker Commands:

- If we use `docker run <image-name>` command , the container will run in the foreground. If we use `docker run -d <image-name>` command, the container will run in the background.

- If we run container in foreground, we can stop the container by pressing `Ctrl + C` in the terminal.

- If we run container in background, we can stop the container by using `docker stop <container-id>` command.

- If we run container in background, we can attach the container by using `docker attach <container-id>` command.

Date of Learning: 06/01/2024