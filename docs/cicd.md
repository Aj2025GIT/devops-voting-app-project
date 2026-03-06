# CI/CD Pipeline

In this project, a Continuous Integration (CI) pipeline was implemented using **GitHub Actions**. The pipeline automatically builds Docker images and pushes them to Docker Hub whenever changes are pushed to the repository.

This ensures that the application is always built and packaged automatically without manual intervention.

---

## CI/CD Workflow

The CI/CD pipeline follows this workflow:

Developer pushes code to GitHub  
↓  
GitHub Actions pipeline is triggered  
↓  
Docker image is built  
↓  
Docker image is pushed to Docker Hub  
↓  
Kubernetes pulls the latest image during deployment

---

## GitHub Actions

GitHub Actions was used to automate the build process.

Each microservice repository contains a GitHub Actions workflow file located in:


.github/workflows/docker-build.yml


The workflow performs the following steps:

1. Checks out the repository code
2. Logs into Docker Hub
3. Builds the Docker image
4. Pushes the image to Docker Hub

---

## Example CI Pipeline Steps

Typical pipeline stages include:

**Checkout Code**


uses: actions/checkout@v3


**Login to Docker Hub**


docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD


**Build Docker Image**


docker build -t aj1297/vote-app .


**Push Docker Image**


docker push aj1297/vote-app


---

## Docker Hub Registry

Docker Hub was used as the container image registry for storing built images.

Images used in this project:

- aj1297/vote-app
- aj1297/result-app
- aj1297/worker-app

Kubernetes deployments pull these images directly from Docker Hub.

---

## GitHub Secrets

Sensitive credentials such as Docker Hub login details were stored securely using GitHub Secrets.

Secrets used:

- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

This ensures credentials are not exposed in the workflow files.

---

## Benefits of CI/CD in This Project

Implementing CI/CD provides several advantages:

- Automated build process
- Faster development workflow
- Reduced manual deployment errors
- Consistent container image generation
- Seamless integration with Kubernetes deployments

---

## Summary
# CI/CD Pipeline

In this project, a Continuous Integration (CI) pipeline was implemented using **GitHub Actions**. The pipeline automatically builds Docker images and pushes them to Docker Hub whenever changes are pushed to the repository.

This ensures that the application is always built and packaged automatically without manual intervention.

---

## CI/CD Workflow

The CI/CD pipeline follows this workflow:

Developer pushes code to GitHub  
↓  
GitHub Actions pipeline is triggered  
↓  
Docker image is built  
↓  
Docker image is pushed to Docker Hub  
↓  
Kubernetes pulls the latest image during deployment

---

## GitHub Actions

GitHub Actions was used to automate the build process.

Each microservice repository contains a GitHub Actions workflow file located in:


.github/workflows/docker-build.yml


The workflow performs the following steps:

1. Checks out the repository code
2. Logs into Docker Hub
3. Builds the Docker image
4. Pushes the image to Docker Hub

---

## Example CI Pipeline Steps

Typical pipeline stages include:

**Checkout Code**


uses: actions/checkout@v3


**Login to Docker Hub**


docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD


**Build Docker Image**


docker build -t aj1297/vote-app .


**Push Docker Image**


docker push aj1297/vote-app


---

## Docker Hub Registry

Docker Hub was used as the container image registry for storing built images.

Images used in this project:

- aj1297/vote-app
- aj1297/result-app
- aj1297/worker-app

Kubernetes deployments pull these images directly from Docker Hub.

---

## GitHub Secrets

Sensitive credentials such as Docker Hub login details were stored securely using GitHub Secrets.

Secrets used:

- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

This ensures credentials are not exposed in the workflow files.

---

## Benefits of CI/CD in This Project

Implementing CI/CD provides several advantages:

- Automated build process
- Faster development workflow
- Reduced manual deployment errors
- Consistent container image generation
- Seamless integration with Kubernetes deployments

---

## Summary
The CI pipeline ensures that every code change automatically results in a new Docker image being built and pushed to Docker Hub. This enables reliable and repeatable deployments to the Kubernetes cluster.


The CI pipeline ensures that every code change automatically results in a new Docker image bei
