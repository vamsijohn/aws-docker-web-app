# 🚀 Containerized Web Application Deployment on AWS EC2

[![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazon-aws)](https://aws.amazon.com/)
[![Docker](https://img.shields.io/badge/Docker-Container-blue?style=for-the-badge&logo=docker)](https://www.docker.com/)
[![Nginx](https://img.shields.io/badge/Nginx-Web%20Server-green?style=for-the-badge&logo=nginx)](https://nginx.org/)
[![Linux](https://img.shields.io/badge/Linux-Ubuntu-red?style=for-the-badge&logo=ubuntu)](https://ubuntu.com/)

---

## 📌 Project Overview
This project showcases the end-to-end containerization of a lightweight static web application using **Docker** and deploying it live on an **AWS EC2 Instance**. It covers Dockerfile optimization using Alpine Linux, remote SSH access, port mapping (`80:80`), AWS Security Group configurations, and live web access.

---

## 🎯 Key Topics & Concepts Covered
- **Infrastructure Provisioning:** AWS EC2 Instance setup & Security Group management (Port 22 for SSH, Port 80 for HTTP).
- **Containerization:** Writing custom Dockerfiles and building lightweight Docker images using Nginx Alpine.
- **Web Administration:** Hosting and serving web content inside isolated container environments.
- **Port Management:** Mapping host system ports to Docker container ports (`80:80`).
- **Troubleshooting & Maintenance:** Container cleanup, force rebuilds without cache (`--no-cache`), and container status monitoring.

---

## 🏗️ Project Architecture
`Local Source Code` ➔ `Build Docker Image` ➔ `AWS EC2 (Ubuntu)` ➔ `Run Docker Container` ➔ `Public Web Access (Port 80)`

---

## 🛠️ Tech Stack & Tools

| Component | Technology Used |
| :--- | :--- |
| **Cloud Infrastructure** | AWS EC2 (Ubuntu 22.04 LTS / 24.04 LTS) |
| **Containerization** | Docker, Dockerfile |
| **Web Server Engine** | Nginx (Alpine Base Image) |
| **Version Control** | Git & GitHub |
| **Terminal / CLI** | Git Bash & Linux Command Line |

---

## ⚙️ Step-by-Step Implementation

### 1️⃣ Application & Dockerfile Setup
* Created static web application file (`index.html`).
* Authored an optimized `Dockerfile` leveraging lightweight `nginx:alpine`.

### 2️⃣ Cloud Infrastructure Setup
* Launched an AWS EC2 Ubuntu instance.
* Configured Security Group Inbound Rules:
  * **SSH (Port 22):** Remote management access.
  * **HTTP (Port 80):** Public web traffic from anywhere (`0.0.0.0/0`).

### 3️⃣ Docker Server Configuration & Deployment
* Installed and started Docker Engine on the EC2 server.
* Built the application Docker image and executed the container in detached mode with port mapping (`80:80`).

---

## 🔧 Essential Commands Executed

```bash
# Update Server & Install Docker
sudo apt update -y
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ubuntu
newgrp docker

# Create Project Directory
mkdir project1 && cd project1

# Build Docker Image without Cache
docker build --no-cache -t my-web-app .

# Run Container Live
docker run -d -p 80:80 --name my-container-v2 my-web-app

# Verify Running Status
docker ps
```

---

## 🌐 Live Application Verification
Access the running web application live through any browser using the AWS EC2 Public IP:

**Live URL:** http://107.22.151.229
