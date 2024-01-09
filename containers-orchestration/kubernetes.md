## Kubernetes (k8s)

- Kubernetes is also another orchestration tool like Docker Swarm.
- Kubernetes is an open-source container-orchestration system for automating application deployment, scaling, and management.
- Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation.
- Sample advantages of kubernetes:
    - kubectl scale -–replicas=2000 my-web-server used to scale the containers.
    - kubectl rolling-update my-web-server --image=web-server:2 used to update the containers.
    - kubectl rolling-update my-web-server --rollback used to rollback the containers.
- Every Kubernetes Cluster has a master node and worker nodes.
- Master node is responsible for the orchestration of the worker nodes. It is also responsible for the orchestration of the services and tasks that are running inside the worker nodes.
- Worker node is responsible for running the services and tasks that are assigned to it by the master node.
- Kubernetes Components:
    - Master Node Components:
        - API Server
        - Scheduler
        - Controller Manager
        - etcd
    - Worker Node Components:
        - Kubelet
        - Kube Proxy
        - Container Runtime
- **API Server** - The API server is a component of the Kubernetes control plane that exposes the Kubernetes API. The API server is the front end for the Kubernetes control plane.
- **Scheduler** - It will schedule the containers to the worker nodes. Which node should run which container is decided by the scheduler.
- **Controller Manager** - The Kubernetes controller manager is a daemon that embeds the core control loops shipped with Kubernetes. In applications of robotics and automation, a control loop is a non-terminating loop that regulates the state of the system.
- **etcd** - etcd is a strongly consistent, distributed key-value store that provides a reliable way to store data that needs to be accessed by a distributed system or cluster of machines. It gracefully handles leader elections during network partitions and can tolerate machine failure, even in the leader node.
- **Kubelet** - Kubelet is the primary “node agent” that runs on each node. It can register the node with the apiserver using one of: the hostname; a flag to override the hostname; or specific logic for a cloud provider.
- **Kube Proxy** - kube-proxy is a network proxy that runs on each node in your cluster, implementing part of the Kubernetes Service concept.
- **Container Runtime** - The container runtime is the software that is responsible for running containers. Kubernetes supports several container runtimes: Docker, containerd, CRI-O, and any implementation of the Kubernetes CRI (Container Runtime Interface).

### Basic Kubernetes Commands:

- **kubectl run hello-minikube** - This command will run a container in the kubernetes cluster.
- **kubectl cluster-info** - This command will give the information about the kubernetes cluster.
- **kubectl get nodes** - This command will give the information about the nodes in the kubernetes cluster.
- **kubectl run my-web-app --image=my-web-app --replicas=10** - This command will run 10 containers in the kubernetes cluster.

Date of Learning: 09/01/2024
