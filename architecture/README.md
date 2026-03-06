# System Architecture

This project demonstrates an end-to-end DevOps implementation of a microservices based voting application.

The system consists of multiple services that communicate with each other through a containerized environment orchestrated using Kubernetes.

## Components

1. Vote Service (Python)
Frontend web application that allows users to vote between two options.

2. Redis
Acts as a temporary data store for incoming votes.

3. Worker Service (.NET)
Processes votes from Redis and stores them into PostgreSQL.

4. PostgreSQL
Persistent database used to store the final vote results.

5. Result Service (Node.js)
Displays the live voting results in the browser.

6. Kubernetes
Orchestrates all services and manages scaling, networking, and deployments.

7. CI/CD Pipeline
GitHub Actions builds Docker images and deploys them to the Kubernetes cluster.

---

## Architecture Diagram
