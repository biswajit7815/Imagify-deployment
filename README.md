# 🚀 Imagify – Production-Ready AI Image Platform

<p align="center">
  <b>End-to-End production level  Dockerized and Docker-compose-yml MERN Application with Nginx Reverse Proxy & AWS Deployment</b>
</p>

---

## 🌍 Live System

🔗 http://3.110.86.139

---

## 🧠 System Architecture

```id="arch123"
Client (React + Vite)
        │
        ▼
   Nginx (Reverse Proxy)
        │
        ▼
Backend (Node.js + Express API)
        │
        ▼
 MongoDB (Database)
```

---

## ⚙️ DevOps Highlights

* 🐳 **Containerized Architecture (Docker)**
* 🔄 **Multi-Service Orchestration (Docker Compose)**
* 🌐 **Nginx Reverse Proxy (Production Routing)**
* 🔐 **Environment-based Configuration (.env)**
* ⚡ **Zero-downtime Deployment Ready**
* 📦 **Isolated Services (Frontend, Backend, DB)**
* 🔗 **Internal Docker Networking (Service Discovery)**

---

## 🏗️ Infrastructure Setup

| Layer            | Technology        |
| ---------------- | ----------------- |
| Compute          | AWS EC2           |
| Reverse Proxy    | Nginx             |
| Containerization | Docker            |
| Orchestration    | Docker Compose    |
| Backend          | Node.js + Express |
| Database         | MongoDB           |
| Frontend         | React (Vite)      |

---

## 📂 Project Structure

```id="struct456"
imagify/
│
├── client/              # Frontend (React)
├── server/              # Backend API
├── nginx/               # Reverse proxy config
├── docker-compose.yml   # Multi-container setup
└── .env                 # Environment variables
```

---

## 🔄 Service Communication Flow

```id="flow789"
User Request
    ↓
Nginx (Port 80)
    ↓
Route /api → Backend Container
    ↓
Business Logic Execution
    ↓
MongoDB (Data Layer)
    ↓
Response → Nginx → Client
```

---



---

## 🔐 Environment Configuration

```env id="env999"
MONGO_URI=mongodb://user:pass@mongodb:27017/db
JWT_SECRET=your_secret
CLIPDROP_API=your_api_key
```

---

## 🚀 Deployment Steps

### 1️⃣ Clone Repository

```bash id="cmd1"
https://github.com/biswajit7815/Imagify-deployment.git
cd imagify-deployment
```

### 2️⃣ Configure Environment

```bash id="cmd2"
nano .env
```

### 3️⃣ Build & Run Containers

```bash id="cmd3"
docker-compose up -d --build
```

---

## 📡 API Gateway (Nginx)

```nginx id="nginx001"
location /api/ {
    proxy_pass http://server:4000;
}
```

---

## 📊 Observability & Debugging

* `docker ps` → container status
* `docker logs <container>` → runtime logs
* `docker exec` → container shell access
* `curl` → API testing

---

## 🛡️ Security Considerations

* 🔐 JWT Authentication
* 🔒 Environment variables (no secrets in code)
* 🚫 Direct DB exposure blocked
* 🌐 Reverse proxy controlled access

---

## 🚀 Future Enhancements

* 🔐 HTTPS (Let's Encrypt SSL)
* 🔁 CI/CD Pipeline (GitHub Actions)
* 📊 Monitoring (Prometheus + Grafana)
* 📦 Kubernetes Migration
* ⚡ Auto Scaling

---

## 👨‍💻 Author

**Biswajit Behera**
📧 [biswajitbehera1868@gmail.com](mailto:biswajitbehera1868@gmail.com)

---

## ⭐ DevOps Impact

> Designed and deployed a scalable, containerized full-stack system with production-grade networking and reverse proxy architecture.

---
