# 🚀 Containerized Web Application Deployment on AWS EC2

[![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazon-aws)](https://aws.amazon.com/)
[![Docker](https://img.shields.io/badge/Docker-Container-blue?style=for-the-badge&logo=docker)](https://www.docker.com/)
[![Nginx](https://img.shields.io/badge/Nginx-Web%20Server-green?style=for-the-badge&logo=nginx)](https://nginx.org/)
[![Linux](https://img.shields.io/badge/Linux-Ubuntu-red?style=for-the-badge&logo=ubuntu)](https://ubuntu.com/)

---

## 📌 Project Overview
This project showcases end-to-end containerization of a web application using **Docker** and deploying it live on an **AWS EC2 Instance**. It covers local Docker image construction, SSH remote connectivity, and real-time cloud instance execution.

---

## 🏗️ Project Architecture
`Local Source Code` ➔ `Build Docker Image` ➔ `AWS EC2 (Ubuntu)` ➔ `Run Docker Container` ➔ `Public Web Access (Port 80)`

---

## 🛠️ Tech Stack & Tools

| Component | Technology Used |
| :--- | :--- |
| **Cloud Infrastructure** | AWS EC2 (t2.micro / Ubuntu 22.04 LTS) |
| **Containerization** | Docker, Dockerfile |
| **Web Server Engine** | Nginx (Alpine Base Image) |
| **Version Control** | Git & GitHub |
| **Terminal / CLI** | Git Bash & SSH Client |

---

## ⚙️ Step-by-Step Implementation

### 1️⃣ Local Development
* Created static web application files (`index.html`).
* Written an optimized `Dockerfile` leveraging `nginx:alpine`.

### 2️⃣ Cloud Infrastructure Provisioning
* Launched an AWS EC2 Ubuntu instance with active Security Group inbound rules:
  * **SSH (Port 22):** Remote terminal configuration.
  * **HTTP (Port 80):** Inbound web traffic accessibility.

### 3️⃣ Docker Server Configuration & Deployment
* Provisioned Docker Engine on the cloud server.
* Built the application image and executed the container in detached mode with port mapping (`80:80`).

---

## 🔧 Essential Commands Executed

```bash
# Update Server & Install Docker
sudo apt update -y
sudo apt install docker.io -y

# Build Docker Image
docker build -t my-web-app .

# Run Container Live
docker run -d -p 80:80 --name my-web-container my-web-app

# Verify Running Status
docker ps
