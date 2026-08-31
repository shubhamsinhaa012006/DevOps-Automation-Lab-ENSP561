# Experiment 03: Docker Containerization

## Objective
Containerize a sample web application using Docker, demonstrating the ability to build images, manage containers, and understand Docker architecture.

## Software Required
- Docker Desktop / Docker Engine
- Web Browser (Chrome / Safari / Firefox)
- Command Line Interface (Terminal/Command Prompt)

## Prerequisites
- Docker installed and running locally.
- Basic understanding of command-line operations and web servers.

## Theory

### Docker Architecture
Docker uses a client-server architecture. The Docker client (`docker` CLI) communicates with the Docker daemon (`dockerd`), which does the heavy lifting of building, running, and distributing Docker containers. The client and daemon communicate using a REST API over UNIX sockets or a network interface.

### Difference between Image and Container
- **Docker Image:** An inert, immutable, read-only template containing instructions for creating a Docker container. It includes the application code, runtime, libraries, environment variables, and configuration files.
- **Docker Container:** A live, running instance of an image. It executes the application in an isolated environment. You can think of an image as a class in object-oriented programming, and a container as an instance of that class.

### Image Layers
Docker images are constructed from a series of layers. Each instruction in a `Dockerfile` (like `FROM`, `COPY`, `RUN`) creates a new layer. These layers are stacked, and each one is a delta of the changes from the previous layer. This layered architecture makes Docker lightweight and fast, as layers can be cached and shared across different images.

### The Docker Build Process
When you run `docker build`, the Docker daemon reads the `Dockerfile` line-by-line. For each instruction, it creates a temporary container, executes the instruction, commits the change as a new image layer, and then removes the temporary container. The final layer forms the complete image.

### Why `nginx:alpine`?
The `nginx:alpine` image was chosen as the base image because Alpine Linux is a highly minimized Linux distribution. An Alpine-based image is significantly smaller (often around 5-20MB) compared to Debian or Ubuntu-based images. This leads to:
- Faster download and build times.
- Reduced storage space requirements.
- A smaller attack surface, improving security.

### Port Mapping
Containers run in their own isolated network namespace. To access an application running inside a container from the host machine, you must map a port on the host to a port on the container using the `-p <host-port>:<container-port>` flag (e.g., `-p 8080:80`). This bridges the host's network interface to the container's internal port.

## Step-by-Step Procedure
1. Create a directory named `03-Docker-Containerization`.
2. Develop a static website (`index.html` and `style.css`) to serve as the application.
3. Create a `.dockerignore` file to exclude unnecessary files from the build context.
4. Write a `Dockerfile` using `nginx:alpine` as the base image.
5. Build the Docker image using the `docker build` command.
6. Verify the image creation and inspect its layers using `docker images` and `docker history`.
7. Start a container from the image using `docker run`, mapping port 80 to the host.
8. Check the status of the running container with `docker ps`.
9. Inspect the container using `docker inspect`.
10. View the container's execution logs using `docker logs`.
11. Open a web browser to verify the application is accessible on localhost.
12. Stop, start, and finally remove the container and image to understand the lifecycle.

## Commands Used

### Image Management
- `docker build -t <image-name> .`: Builds a Docker image from the Dockerfile in the current directory (`.`), tagging it with `<image-name>`.
- `docker images`: Lists all local Docker images.
- `docker history <image-name>`: Displays the layers that make up a Docker image.
- `docker image rm <image-name>`: Removes a specific Docker image from the local system.

### Inspection
- `docker inspect <container-name>`: Displays detailed configuration, networking, mounted volumes, environment variables, and runtime information of a Docker container.

### Container Management
- `docker run -d -p 80:80 --name <container-name> <image-name>`: 
  - `-d`: Runs the container in detached mode (background).
  - `-p 80:80`: Maps port 80 of the host to port 80 in the container.
  - `--name`: Assigns a specific name to the container.
- `docker ps`: Lists currently running containers.
- `docker ps -a`: Lists all containers (running and stopped).
- `docker logs <container-name>`: Fetches the logs of a container.
- `docker stop <container-name>`: Gracefully stops a running container.
- `docker start <container-name>`: Starts a stopped container.
- `docker rm <container-name>`: Removes a stopped container.

## Expected Output
- The `docker build` command should complete successfully, creating the image layers.
- `docker run` should return a container ID.
- `docker inspect` should display detailed container information successfully.
- The web browser at `http://localhost` should display the professional landing page without errors.
- `docker logs` should show Nginx access logs reflecting the browser visits.

*(Insert Docker Build Screenshot Here)*

*(Insert Docker Run and PS Screenshot Here)*

*(Insert Docker History Screenshot Here)*

*(Insert Web Browser Output Screenshot Here)*

*(Insert Docker Logs Screenshot Here)*

## Learning Outcome
- Understood Docker architecture, images, and containers.
- Learned to write a robust `Dockerfile` using best practices.
- Mastered essential Docker CLI commands for image and container lifecycle management.
- Successfully containerized and deployed a static web application.

## Conclusion
This experiment successfully demonstrates the principles of containerization. By encapsulating a web application and its Nginx server environment within a Docker container, we ensure that the application is portable, isolated, and scalable. This eliminates environmental inconsistencies and streamlines deployment processes.

## References
- [Docker Official Documentation](https://docs.docker.com/)
- [Nginx Docker Hub Page](https://hub.docker.com/_/nginx)
- [Alpine Linux](https://www.alpinelinux.org/)
