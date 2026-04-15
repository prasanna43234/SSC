# 🐳 Docker Commands

## 1. Download Images from Docker Hub

```
docker pull imagename
```

➡️ Pulls latest image (default tag)

```
docker pull imagename:version
```

➡️ Pulls specific version

---

## 2. Docker Image Commands

```
docker images
```

➡️ Lists all local Docker images

```
docker rmi imagename
```

➡️ Removes image

---

## 3. Docker Build Commands (Custom Image)

### (i) If Dockerfile is in same location

```
docker build -t imagename .
```

➡️ Creates image with latest tag

```
docker build -t my-app:v1.0 .
```

➡️ Creates image with v1.0 tag

### (ii) If Dockerfile is in different location

```
docker build -f app/Dockerfile -t my-app:latest .
docker build -f app/Dockerfile -t my-app:v1.0 .
```

---

## 4. Running Docker Containers

### (i) Detached mode (background)

```
docker run -d imagename
```

### (ii) Interactive mode (terminal access)

```
docker run -it imagename /bin/bash
```

### (iii) Run with custom name

```
docker run -d --name my-container imagename
```

### (iv) Port mapping

```
docker run -d -p 8080:80 imagename
```

### (v) Environment variables

```
docker run -d -e ENV=dev imagename
```

### (vi) Remove container

```
docker rm containerid
```

---

## 5. Container Monitoring

```
docker ps
```

➡️ Lists running containers

```
docker ps -a
```

➡️ Lists all containers

```
docker ps -a | grep "reverse"
```

➡️ Filter containers

---

## 6. Container Lifecycle Commands

```
docker start containerid
docker stop containerid
docker restart containerid
```

---

## 7. Docker Log Commands
## 📄 **View All Logs**

```bash
docker logs <containerid>
```

➡️ Shows complete logs of container

---

## 📡 **Live Logs (Real-Time)**

```bash
docker logs -f <containerid>
```

➡️ Continuously shows logs as they are generated

---

## 🔢 **Last Few Lines**

```bash
docker logs --tail 100 <containerid>
```

➡️ Shows only last 100 lines

---

## ⏱️ **Logs with Timestamp**

```bash
docker logs -t <containerid>
```

➡️ Shows logs with time

---

