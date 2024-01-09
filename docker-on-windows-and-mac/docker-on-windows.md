## Docker on Windows:

There is two options to run Docker on Windows:

1. Docker Toolbox
2. Docker for Windows

### Docker Toolbox:

- Docker Toolbox is a legacy desktop solution for older Windows systems that do not meet the requirements of [Docker for Windows](https://docs.docker.com/docker-for-windows/install/). We recommend updating to the newer applications, if possible.

- Docker Toolbox includes the following Docker tools:

  - Docker CLI client for running Docker Engine to create images and containers
  - Docker Machine so you can run Docker Engine commands from Windows terminals
  - Docker Compose for running the `docker-compose` command
  - Kitematic, the Docker GUI
  - a shell preconfigured for a Docker command-line environment
  - Oracle VM VirtualBox

- Docker tool box -> Create a default virtual box VM with docker-machine -> Linux VM -> Containers Run

### Docker on Windows:

- Docker for Windows is a native Windows application with a native user interface and auto-update capability, compared to Docker Toolbox which uses Oracle Virtual Box to run the Docker virtual machine. Docker for Windows uses Hyper-V to virtualize the Docker Engine environment and Linux kernel-specific features for the Docker daemon.

- Docker for Windows requires 64bit Windows 10 Pro, Enterprise and Education (1511 November update, Build 10586 or later) and Microsoft Hyper-V. Please see What to know before you install for a full list of prerequisites.

- Docker for Windows is currently not supported on Windows 10 Home, or on Windows Server. Please see What to know before you install for a full list of prerequisites.

- Docker on Windows -> Hyper-V -> Linux VM -> Containers Run

- Docker For Windows supports Linux Containers (Default) and Windows Containers

- Docker For Windows Container Types:

    - Windows Server Core: Windows container on native windows server core

    - Hyper-V Isolation: Windows container on an isolated hyper-v kernel


Date of Learning: 09/01/2024
