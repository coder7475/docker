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

## References

1. [official docs](https://docs.docker.com/get-started/docker-overview/#:~:text=The%20underlying%20technology,-Docker%20is%20written&text=Docker%20uses%20a%20technology%20called,provide%20a%20layer%20of%20isolation.)

2. [roadmap.sh](https://roadmap.sh/docker)
