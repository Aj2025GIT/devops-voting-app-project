# Project Overview

This project demonstrates an end-to-end DevOps implementation of a microservices based voting application. The goal of this project is to showcase containerization, Kubernetes orchestration, CI/CD automation, and cloud deployment using AWS.

The application allows users to vote between two options (Cats vs Dogs) and displays real-time voting results.

---

## Application Workflow

1. Users submit votes through a web interface.
2. Votes are stored temporarily in Redis.
3. A worker service consumes votes from Redis and processes them.
4. The worker service stores processed votes in PostgreSQL.
5. A result service reads the database and displays the results in real time.

---

## Microservices Used

The application consists of the following services:

| Service | Technology | Purpose |
|------|------|------|
| Vote Service | Python | Frontend voting application |
| Redis | In-memory DB | Temporary vote storage |
| Worker Service | .NET | Processes votes from Redis |
| PostgreSQL | Database | Persistent vote storage |
| Result Service | Node.js | Displays voting results |

---

## DevOps Implementation

This project demonstrates several DevOps practices including:

- Containerization using **Docker**
- Multi-container application management
- Kubernetes orchestration using **K3s**
- Infrastructure deployment on **AWS EC2**
- CI/CD automation using **GitHub Actions**
- Container image management using **Docker Hub**
- Kubernetes manifests for deployments, services, ingress, and autoscaling

---

## Tools & Technologies

| Category | Tools |
|------|------|
| Containerization | Docker |
| Container Registry | Docker Hub |
| Orchestration | Kubernetes (K3s) |
| CI/CD | GitHub Actions |
| Cloud Platform | AWS EC2 |
| Networking | Kubernetes Services & Ingress |
| Monitoring | Kubernetes Metrics Server |

---

## Key Features Implemented

- Microservices architecture
- Docker-based containerized services
- Kubernetes deployments and services
- Horizontal Pod Autoscaling
- Kubernetes RBAC and Service Accounts
- Ingress-based routing
- CI/CD automation pipeline
- Cloud deployment on AWS

---

## Project Goal

The main objective of this project is to simulate a real-world DevOps workflow by:

- Building containerized microservices
- Deploying them to Kubernetes
- Automating build and deployment pipelines
- Running the application in a cloud environment

This project demonstrates practical DevOps skills including infrastructure management, container orchestration, and CI/CD automation.
