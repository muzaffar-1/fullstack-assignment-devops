# Full-Stack DevOps Deployment on AWS

This repository contains a containerized Next.js and Django application, fully automated with Ansible and a CI/CD pipeline.

## 🛠 Tech Stack
- **Frontend:** Next.js (Dockerized)
- **Backend:** Django REST Framework (Dockerized)
- **Infra:** AWS EC2 (t2.micro)
- **Configuration:** Ansible
- **CI/CD:** GitHub Actions & Docker Hub

## 🚀 What I Accomplished
1. **Server Provisioning:** Configured an Ubuntu 24.04 EC2 instance.
2. **Containerization:** Wrote Dockerfiles for both services and linked them using Docker Compose.
3. **Security:** Configured Security Groups for ports 3000, 8000, and 22.
4. **Automation:** Created a CI/CD pipeline that builds and deploys code changes automatically.

## 📦 How to Run
```bash
docker-compose up -d
The app will be available at http://<EC2-IP>:3000
