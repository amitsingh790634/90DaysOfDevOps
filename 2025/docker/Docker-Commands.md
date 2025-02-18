# Docker Notes with All Commands

**Docker Notes with All Commands**

![image](https://github.com/user-attachments/assets/5437140d-3ca3-4a59-8323-affcee49a6c2)


## 1. Basic Docker Commands

### Check Docker Version
Displays the installed Docker version.
```bash
docker --version
```

### Check Docker System Info
Provides detailed information about the Docker installation.
```bash
docker info
```

---

## 2. Container Management

### List Running Containers
Shows currently running containers.
```bash
docker ps
```

### List All Containers
Displays all containers, including stopped ones.
```bash
docker ps -a
```

### Run a New Container
Creates and starts a new container in detached mode.
```bash
docker run -d --name container_name image_name
```

### Run a Container with an Interactive Terminal
Starts a container interactively with a shell session.
```bash
docker run -it image_name bash
```

### Start/Stop/Restart/Remove a Container
```bash
docker start container_id
docker stop container_id
docker restart container_id
docker rm container_id
```

### View Container Logs
Displays logs for a specific container.
```bash
docker logs container_id
```

### Execute Command in Running Container
Runs a command inside a running container.
```bash
docker exec -it container_id bash
```

---

## 3. Image Management

### List All Docker Images
Displays all downloaded Docker images.
```bash
docker images
```

### Pull an Image from Docker Hub
Download an image from Docker Hub.
```bash
docker pull image_name
```

### Build an Image from Dockerfile
Creates a Docker image from a Dockerfile.
```bash
docker build -t image_name .
```

### Push an Image to Docker Hub
Uploads a Docker image to a remote repository.
```bash
docker push image_name
```

---

## 4. Volumes and Data Management

### List Docker Volumes
Shows all available Docker volumes.
```bash
docker volume ls
```

### Create a New Volume
Generates a new volume for persistent storage.
```bash
docker volume create volume_name
```

### Remove a Volume
Deletes a specified volume.
```bash
docker volume rm volume_name
```

---

## 5. Networking in Docker

### List Docker Networks
Displays all Docker networks.
```bash
docker network ls
```

### Create a New Network
Establishes a new custom network.
```bash
docker network create network_name
```

---

## 6. Docker Compose

### Start Services in Docker Compose
Launches all services in detached mode.
```bash
docker-compose up -d
```

### Stop Services in Docker Compose
Shuts down all running services.
```bash
docker-compose down
```

---

## 7. Security and Debugging

### Inspect a Container
Displays low-level details about a container.
```bash
docker inspect container_id
```

### View Resource Usage of Containers
Monitors CPU and memory usage of running containers.
```bash
docker stats
```

---

## 8. Dockerfile Commands

### Dockerfile: Writing Method with Explanation
A Dockerfile is a script containing instructions that Docker uses to create a container image.

| Instruction  | Purpose |
|-------------|---------|
| FROM        | Defines the base image |
| WORKDIR     | Sets the working directory inside the container |
| COPY        | Copies files from the host to the container |
| RUN         | Executes commands inside the container |
| CMD         | Specifies the default command to run the container |
| EXPOSE      | Opens a port for communication |
| ENTRYPOINT  | Defines the executable command |
| ENV         | Sets environment variables |

### Example: Dockerfile for a Node.js Application
```dockerfile
# Step 1: Use a base image
FROM node:18-alpine

# Step 2: Set the working directory inside the container
WORKDIR /app

# Step 3: Copy package.json and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Step 4: Copy the application code
COPY . .

# Step 5: Expose the application port
EXPOSE 3000

# Step 6: Define the startup command
CMD ["node", "server.js"]
```

---

## 9. Docker Network: Create and Connect to Container

### Create a Network
```bash
docker network create dev
```

### List Networks
```bash
docker network ls
```

### Run a Container with Network Configuration
```bash
docker run -d -p 5000:5000 --network two-tear -e MYSQL_HOST=mysql -e MYSQL_USER=root -e MYSQL_PASSWORD=root -e MYSQL_DB=devops flask-backend-app:latest
```

---

## 10. Troubleshooting and Cleanup

### Exit from Database Command Line
```bash
exit
```

### Show All Container IDs
```bash
docker ps -aq
```

### Delete All Containers by ID
```bash
docker rm -v $(docker ps -aq)
```

### Show All Images List
```bash
docker images -aq
```

### Delete All Docker Images by ID
```bash
docker rmi $(docker images -aq)
```

### Create a Copy of an Image and Attach Own Account
```bash
docker image tag python-app-mini-multistage:latest username/python-app-mini-multistage:latest
```

### Push Docker Image to Docker Hub
```bash
docker push username/python-app-mini-multistage
```

---

This document provides a complete reference for Docker commands, including container management, image handling, networking, and troubleshooting. Use these commands to efficiently manage your Docker environment.


## 📢 Connect with Me

For collaboration, DevOps discussions, and networking, feel free to connect with me:

🔗 **LinkedIn:** [Amit Singh - DevOps Engineer](https://www.linkedin.com/in/amitsinghdevops/)  

📧 **Email:** amitsingh790634@gmail.com | devops.amit2000@gmail.com  

📱 **WhatsApp:** +91 9068220575  
