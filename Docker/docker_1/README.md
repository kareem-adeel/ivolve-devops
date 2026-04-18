
# Lab 3: Run Java Spring Boot App in a Container 🐳
![Lab 3 Screenshot](screenshots/lab3.png)


## Objective
Run a Java Spring Boot application inside a Docker container using a Maven base image.

---

## Steps

### 1. Clone the Application
```bash
git clone https://github.com/Ibrahim-Adel15/Docker-1.git
cd Docker-1
```

The project structure:
```
.
├── pom.xml
└── src
    └── main
        └── java
            └── com
                └── example
                    └── demo
                        └── DemoApplication.java
```

![Clone & Project Structure](screenshots/screen1)

---

### 2. Write the Dockerfile
```dockerfile
FROM maven:3.9.14-eclipse-temurin-17-alpine
RUN adduser -D appuser && chown -R appuser:appuser /app
USER appuser
WORKDIR /app
COPY . .
RUN mvn package
CMD ["java","-jar","target/demo-0.0.1-SNAPSHOT.jar"]
EXPOSE 8080
```

![Dockerfile](screen2.png)

---

### 3. Build the Docker Image
```bash
docker build -t lab1 .
```

Docker pulls the base image and builds the app layer by layer.

![Docker Build](screen3.png)

---

### 4. Run the Container
```bash
docker run -d --name firstlab -p 75:8080 lab1
```

- `-d` → Run in background (detached mode)
- `--name firstlab` → Name the container
- `-p 75:8080` → Map port 75 on host to port 8080 in container

```bash
docker ps -a
```

![Docker Run](screen4.png)

---

### 5. Test the Application
```bash
docker exec -it firstlab bash
curl localhost:8080
```

Response:
```
Hello from Dockerized Spring Boot!
```

![Test App](screen5.png)

---

### 6. Stop and Delete the Container
```bash
docker stop firstlab
docker rm 1958
docker ps -a
```

![Stop & Remove](screen6.png)

---

## Summary

| Step | Command |
|------|---------|
| Clone repo | `git clone <url>` |
| Build image | `docker build -t lab1 .` |
| Run container | `docker run -d --name firstlab -p 75:8080 lab1` |
| Test app | `curl localhost:8080` |
| Stop container | `docker stop firstlab` |
| Remove container | `docker rm <id>` |
