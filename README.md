# Docker

- Docker is an open platform for developing, shipping, and running applications.

- Docker enables you to separate your applications from your infrastructure so you can deliver software quickly.

## Containers and the Docker platform

Docker is a platform that simplifies the process of creating, deploying, and managing containers. It provides developers and administrators with a set of tools and APIs to manage containerized applications.

With Docker, you can build and package application code, libraries, and dependencies into a **container image**, which can be distributed and run consistently in any environment that supports Docker.

## What are Containers?

Containers are lightweight, portable, and isolated software environments that allow developers to run and package applications with their dependencies, consistently across different platforms. They help to streamline application development, deployment, and management processes while ensuring that applications run consistently, regardless of the underlying infrastructure.

### How do containers work?

Unlike traditional virtualization, which emulates a complete operating system with its hardware resources, containers share the host’s OS kernel and leverage lightweight virtualization techniques to create isolated processes. This approach leads to several benefits, including:

- **Efficiency**: Containers have less overhead and can share common libraries and executable files, making it possible to run more containers on a single host compared to virtual machines (VMs).
- **Portability**: Containers encapsulate applications and their dependencies, so they can easily be moved and run across different environments and platforms consistently.
- **Fast startup**: Since containers don’t need to boot a full OS, they can start up and shut down much faster than VMs.
- **Consistency**: Containers provide a consistent environment for development, testing, and production stages of an application, reducing the “it works on my machine” problem.

## Docker Tooling

Docker provides tooling and a platform to manage the lifecycle of your containers:

- Develop your application and its supporting components using containers.

- The container becomes the unit for distributing and testing your application.

- When you're ready, deploy your application into your production environment, as a container or an orchestrated service. This works the same whether your production environment is a local data center, a cloud provider, or a hybrid of the two.

## Docker Use cases

1. Fast, consistent delivery of your application
2. Responsive deployment and scaling
3. Running more workload on the same hardware

## Docker Architecture

- Client - Server Architecture
- Docker Client - Docker Daemon

### Docker daemon

- Listen's for docker api requests and manages **docker objects**
- Communicates with other daemon to manage docker services.

### Docker Client

- simply `docker` sends docker commands to `dockerd` the docker daemon which carries them out.

- `docker` uses docker API

- can communicate with more that one daemon

## Docker Desktop

- An application that enables to build and share containerized application and microservices.

- Includes the Docker daemon (`docker), the Docker client (`docker`), Docker Compose, Docker Content trust, Kubernetes and Credential Helps.

## Docker Registries

- A registry to store Docker images.

- Public Registry: Docker Hub

- You can run your own private registry

- Command used: `docker pull` and `docker run`

## Docker objects

### Images

- An image is a read-only template with instruction for creating a Docker container.

- Often, an image is based on another image, with some additional customization.

- You can create and publish images to a registry

- Creating image is done by **Dockerfile** with simple syntax.
  - Each instruction in a Dockerfile creates a layer in the image
  - when changing Dockerfile and rebuilding an image, only those layers which have changed are rebuilt
  - This is why images are so lightweight, small and fast

### Containers

- A container is a runnable instance of an image.

- We can create, start, stop, move or delete a container using Docker API or CLI.

- Docker container can be connected to one or more networks, attack storage to it or even create a new image based on in its current state.

- By default, containers are isolated from other containers and its host machine.

- A container is defined by its image as well as any configuration options you provide to it when you create or start it. When a container is removed, any changes to its state that aren't stored in persistent storage disappear.

## The Underlying Technology

- Docker is written in Go

- It takes advantage of several features of the Linux kernel to deliver its functionality.

- Docker Engine is similar to LXC

- The Linux Techonlogy it uses are

  - **LXC**: Linux Containers (LXC) enables running multiple independent Linux systems on a single computer. Acting as isolated spaces, LXC containers share host resources like memory and processing power, without needing their own full operating system copy, ensuring lightweight and fast startup. Portable across compatible Linux systems, they find utility in diverse tasks such as running separate applications, testing software, or deploying cloud services. With user-friendly management tools available, LXC simplifies container creation, monitoring, and management.

  - **Control Groups (cgroups)**: Control Groups (cgroups) is a Linux kernel feature that allows the allocation and management of resources like CPU, memory, and I/O to a set of processes. Docker leverages cgroups to limit the resources used by containers and ensure that one container does not monopolize the resources of the host system.

  - **Union File Systems (UnionFS)**: UnionFS is a file system service that allows the overlaying of multiple file systems in a single, unified view. Docker uses UnionFS to create a layered approach for images and containers, which enables better sharing of common files and faster container creation.

  - **Namespaces**: Namespaces are another Linux kernel feature that provides process isolation. They allow Docker to create isolated workspaces called containers. Namespaces ensure that processes within a container cannot interfere with processes outside the container or on the host system. There are several types of namespaces, like PID, NET, MNT, and USER, each responsible for isolating a different aspect of a process.

## References

- [official docker doc](https://docs.docker.com/get-started/docker-overview/#:~:text=The%20underlying%20technology,-Docker%20is%20written&text=Docker%20uses%20a%20technology%20called,provide%20a%20layer%20of%20isolation.)

- [docker roadmap](https://roadmap.sh/docker)
