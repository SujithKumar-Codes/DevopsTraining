# 🚀 Docker Basics & Microservices Deployment

Hi! 👋 This repo is my learning journey with **Docker** — from basics to deploying **Spring Boot Microservices** with **tracing** and **networking**.

---

## ✅ What I Learned

- Traditional vs Docker deployment  
- Docker architecture (Daemon, CLI, Images, Containers)  
- Writing a Dockerfile & building images  
- Running containers & managing them  
- Volumes for saving data  
- Custom Docker networks  
- Deploying microservices  
- Tracing with Sleuth + Zipkin  

---

## 🐳 Common Docker Commands

```bash
# Run a container (REST API)
docker run -p 5000:5000 muralisocial123/training/rest-api:1.0.0.RELEASE

# Run in background with restart
docker run -d -p 5000:5000 --restart=always muralisocial123/training/rest-api:1.0.0.RELEASE

# View containers
docker container ls        # Running
docker container ls -a     # All

# Start/stop containers
docker container stop <id>
docker container start <id>

# Clean up stopped containers
docker container prune

FROM openjdk:17
COPY target/app.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]

docker build -t yourname/app .

# Create volume
docker volume create mydata

# Use it in container
docker run -it --rm -v mydata:/data ubuntu
