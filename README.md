# Containerized Web Application Deployment on AWS EC2

## 🚀 Project Overview
This project demonstrates how to package a lightweight web application into a Docker container using Nginx Alpine and deploy it live on an AWS EC2 instance.

## 🛠️ Tech Stack
- **Cloud Provider:** AWS (EC2 Ubuntu 22.04 LTS)
- **Containerization:** Docker, Dockerfile
- **Web Server:** Nginx Alpine
- **Tools:** Git, Git Bash

## 📌 Steps Executed
1. Created application files (`index.html` and `Dockerfile`).
2. Built and tested the Docker container locally.
3. Provisioned an AWS EC2 instance with HTTP (Port 80) and SSH (Port 22) security group rules.
4. Installed Docker on Ubuntu server and deployed the container.

## 🔧 Key Commands Used
```bash
# Build Docker Image
docker build -t my-web-app .

# Run Container
docker run -d -p 80:80 --name my-container my-web-app
