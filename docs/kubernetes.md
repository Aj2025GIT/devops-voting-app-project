# Kubernetes Deployment

The voting application was deployed on a Kubernetes cluster using K3s running on an AWS EC2 instance. Kubernetes was used to orchestrate the containerized microservices and manage networking, scaling, and service discovery.

---

## Kubernetes Cluster Setup

A lightweight Kubernetes distribution called **K3s** was used for this project. K3s simplifies cluster setup and is suitable for learning and small production environments.

The cluster was installed on an AWS EC2 Ubuntu instance.

Example installation command:

```bash
curl -sfL https://get.k3s.io | sh -
