# Week 1 of #90DaysOfDevOps2025 Docker completed


# Mastering Docker: A Complete Guide for DevOps 🚀

![1](https://github.com/user-attachments/assets/e20daa13-20dd-48a2-8c58-77aac337c358)


## What is Docker?
Docker is a powerful tool designed to simplify the creation, deployment, and management of applications using containers. These containers bundle all required dependencies—code, runtime, libraries, and system tools—ensuring consistency across different environments. 

---

## 🚀 Why Use Docker?

- **Portability:** Run applications seamlessly across different environments.
- **Efficiency:** Containers are lightweight and start quickly.
- **Scalability:** Easily scale applications up or down.
- **Isolation:** Each container runs independently, preventing conflicts.

---

## 🔧 Simple Docker Workflow

1️⃣ **Write a Dockerfile** - Define how your application should be built.
2️⃣ **Build an Image** - Convert your Dockerfile into an image using `docker build`.
3️⃣ **Run a Container** - Use `docker run` to launch your application in a container.
4️⃣ **Manage Containers** - Use commands like `docker ps`, `docker stop`, and `docker logs`.
5️⃣ **Push to Docker Hub** - Share your image using `docker push`.

![Docker for Beginners](./1.jpg)

---

## 🏗️ Example Dockerfile (Node.js App)

```dockerfile
# Use an official Node.js image
FROM node:16

# Set the working directory
WORKDIR /app

# Copy dependencies and install them
COPY package*.json ./
RUN npm install

# Copy application code
COPY . .

# Expose a port
EXPOSE 3000

# Start the app
CMD ["npm", "start"]
```

---

## 🔥 Essential Docker Commands

- **Build an Image:**
  ```sh
  docker build -t my-app .
  ```
- **List Images:**
  ```sh
  docker image ls
  ```
- **Run a Container:**
  ```sh
  docker run -d -p 3000:3000 --name my-container my-app
  ```
- **Stop a Container:**
  ```sh
  docker stop my-container
  ```
- **Check Logs:**
  ```sh
  docker logs my-container
  ```

---

## 🚀 Docker Compose: Multi-Container Applications

![2](https://github.com/user-attachments/assets/b690692e-490b-4e61-8fbc-8d7b962a20fc)

Docker Compose is used to manage multi-container applications using a single file.

### Example `docker-compose.yml` for a Node.js App with MongoDB

```yaml
version: '3'
services:
  backend:
    build: .
    container_name: backend-app
    ports:
      - "3000:3000"
    environment:
      - MONGO_URI=mongodb://mongodb1:27017/mydb
    depends_on:
      - mongodb1

  mongodb1:
    image: mongo:latest
    container_name: mongodb1
    ports:
      - "27017:27017"
```

### Steps to Use Docker Compose:

✅ **Start Services:**
```sh
docker-compose up --build -d
```
✅ **Stop Services:**
```sh
docker-compose down
```
✅ **List Running Containers:**
```sh
docker ps
```

![Docker Deployment](./2.png)

---

## 🌐 Docker Networking

Docker allows containers to communicate using networks.

- **Create a Network:**
  ```sh
  docker network create my-network
  ```
- **Run a Container in a Network:**
  ```sh
  docker run -d --network=my-network my-app
  ```
- **List Networks:**
  ```sh
  docker network ls
  ```

---

## 🚀 Optimizing Your Docker Workflow

✅ **Use Multi-Stage Builds** for smaller images.
✅ **Leverage Docker Volumes** to persist data between container restarts.
✅ **Enable Auto-Restart Policies** to ensure uptime.
✅ **Use Environment Variables** for configuration flexibility.

![Docker Multistage Builds](./3.png)

---

## 🚀 Advanced Docker for DevOps: Multi-Stage Builds, Docker Hub, and Image Cleanup

### Multi-Stage Docker Builds: Build Small, Deploy Faster

![multi](https://github.com/user-attachments/assets/3e537766-5954-41f3-a347-62e244b08c26)


**What is a Multi-Stage Build?**
Multi-stage builds allow us to build large applications with all dependencies but deploy only what is necessary. This reduces the final image size, improves security, and speeds up deployment.

**Optimized Dockerfile for Python Flask App:**
```dockerfile
# ==========================
# Stage 1: Build Environment
# ==========================
FROM python:3.9-slim AS builder  
WORKDIR /app  
COPY requirements.txt .  
RUN pip install -r requirements.txt --target=/app/deps

# ==========================
# Stage 2: Runtime Environment
# ==========================
FROM gcr.io/distroless/python3-debian12  
WORKDIR /app  
COPY --from=builder /app/deps /app/deps  
COPY --from=builder /app .  
ENV PYTHONPATH="/app/deps"  
EXPOSE 80  
CMD ["python", "app.py"]
```

✅ **Benefits:**
✔ Smaller image size
✔ Faster deployment
✔ Better security

---

## 🏆 Why Every Developer Should Learn Docker

Mastering Docker unlocks opportunities in DevOps, cloud computing, and modern app deployment. Whether you're a developer or a system administrator, Docker is an essential tool in today’s software industry.

🔗 **Let’s Discuss!** What’s your favorite Docker use case? Drop your thoughts in the comments! 💬

#Docker #DevOps #Containers #SoftwareDevelopment #CloudComputing #TrainWithShubham #bhaiya 

🚀 **Huge thanks to DevOps Zero to Hero by TrainWithShubham & Shubham Londhe bhaiya for the guidance and training!** 🙌



## 📢 Connect with Me

For collaboration, DevOps discussions, and networking, feel free to connect with me:

🔗 **LinkedIn:** [Amit Singh - DevOps Engineer](https://www.linkedin.com/in/amitsinghdevops/)  

📧 **Email:** amitsingh790634@gmail.com | devops.amit2000@gmail.com  

📱 **WhatsApp:** +91 9068220575  

