# Docker Implementation

In this project, all application services were containerized using Docker. Each microservice was packaged into a Docker image, allowing the application to run consistently across different environments.

Docker was used to build images for each service and push them to Docker Hub for deployment in Kubernetes.

---

## Services Containerized

The application consists of the following containerized services:

| Service | Technology | Purpose |
|------|------|------|
| Vote Service | Python | Frontend voting application |
| Result Service | Node.js | Displays real-time voting results |
| Worker Service | .NET | Processes votes from Redis and stores them in PostgreSQL |
| Redis | Official Image | Temporary in-memory data store |
| PostgreSQL | Official Image | Persistent database |

---

## Docker Images

Custom Docker images were created for the following services:

- Vote Service
- Result Service
- Worker Service

Official Docker images were used for:

- Redis
- PostgreSQL

All custom images were pushed to Docker Hub.

Example:
