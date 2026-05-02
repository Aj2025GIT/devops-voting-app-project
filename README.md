# 🚀 DevOps Voting App – CI/CD with Kubernetes

## 🧩 Project Overview
This project demonstrates an end-to-end DevOps pipeline for deploying a microservices-based voting application using Docker, Kubernetes, and CI/CD automation. It showcases containerization, orchestration, automated deployments, and monitoring.

---

## 🏗️ Architecture
The application follows a microservices architecture:

- Developer pushes code to GitHub  
- GitHub Actions triggers CI/CD pipeline  
- Docker images are built and deployed  
- Application is deployed on Kubernetes (K3s cluster)  
- Monitoring is enabled using Prometheus and Grafana  

---

## ⚙️ Tech Stack
- **Docker** → Containerization of services  
- **Kubernetes (K3s)** → Container orchestration & scaling  
- **GitHub Actions** → CI/CD automation  
- **Prometheus & Grafana** → Monitoring and alerting  

---

## 🔄 CI/CD Workflow
1. Code push triggers GitHub Actions pipeline  
2. Application is built and containerized using Docker  
3. Deployment manifests are applied to Kubernetes  
4. Application is deployed automatically  
5. Monitoring captures metrics and alerts  

---

## 🚀 Key Features
- Automated CI/CD pipeline for build and deployment  
- Containerized microservices using Docker  
- Kubernetes deployment with **Horizontal Pod Autoscaler (HPA)**  
- Implemented **RBAC and Network Policies** for security  
- Integrated **Prometheus and Grafana** for monitoring  
- Enabled **rolling updates** for zero-downtime deployments  

---

## 🧪 Failure Handling & Debugging
- Simulated pod failures to validate Kubernetes self-healing  
- Used:
  ```bash
  kubectl logs <pod-name>
  kubectl describe pod <pod-name>
