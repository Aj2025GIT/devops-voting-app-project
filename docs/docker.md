# Docker Implementation

In this project, all microservices were containerized using Docker to ensure consistent environments across development and deployment stages.

Each service was packaged as a Docker image and pushed to Docker Hub. These images were later pulled by the Kubernetes cluster during deployment.

---

## Services Containerized

The application consists of the following containerized services:

| Service | Technology | Purpose |
|------|------|------|
| Vote Service | Python | Frontend voting application |
| Result Service | Node.js | Displays voting results |
| Worker Service | .NET | Processes votes from Redis |
| Redis | Official Image | Temporary vote storage |
| PostgreSQL | Official Image | Persistent vote storage |

---

## Docker Images Used

Custom images were built and pushed to Docker Hub:

- docker.io/aj1297/vote-app
- docker.io/aj1297/result-app
- docker.io/aj1297/worker-app

Official images used:

- redis:alpine
- postgres:alpine

---

## Docker Build Commands

Images were built locally using the following commands:

```bash
docker build -t aj1297/vote-app .
docker build -t aj1297/result-app .
docker build -t aj1297/worker-app .
