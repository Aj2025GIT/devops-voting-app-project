docs/kubernetes.md
# Kubernetes Deployment

The voting application was deployed on a Kubernetes cluster using K3s running on an AWS EC2 instance. Kubernetes was used to orchestrate the containerized microservices and manage networking, scaling, and service discovery.

---

## Kubernetes Cluster Setup

A lightweight Kubernetes distribution called **K3s** was used for this project. K3s simplifies cluster setup and is suitable for learning and small production environments.

The cluster was installed on an AWS EC2 Ubuntu instance.

Example installation command:

```bash
curl -sfL https://get.k3s.io | sh -

After installation, the cluster was verified using:

kubectl get nodes
Kubernetes Resources Used

The following Kubernetes resources were implemented in this project.

Deployments

Deployments were created for all application services.

Services deployed:

Vote Service

Result Service

Worker Service

Redis

PostgreSQL

Deployments ensure:

Pod replication

Automatic pod recovery

Rolling updates

Example:

kubectl get deployments
Services

Kubernetes Services were used to provide stable networking between pods.

Services created:

vote

result

redis

db

Example:

kubectl get svc

Services allow internal communication between microservices using DNS names.

Example communication flow:

vote → redis
worker → redis
worker → postgres
result → postgres
Ingress Controller

An Ingress Controller was used to expose services externally.

The project used Traefik Ingress Controller, which is included with K3s.

Ingress was configured to route traffic from the external IP to the appropriate services.

Example routing:

/ → vote service
/result → result service

Ingress allows multiple services to be accessed using a single external entry point.

Example command:

kubectl get ingress
Horizontal Pod Autoscaler (HPA)

Horizontal Pod Autoscaling was configured to automatically scale pods based on CPU usage.

Example configuration:

Minimum pods: 1

Maximum pods: 5

CPU threshold: 50%

Example command:

kubectl get hpa

This ensures the application can scale during increased traffic.

RBAC (Role Based Access Control)

RBAC was implemented to restrict Kubernetes API access.

Resources used:

ServiceAccount

Role

RoleBinding

RBAC ensures that pods have only the minimum permissions required to perform their tasks.

Pod Disruption Budget

Pod Disruption Budgets were configured to ensure application availability during node maintenance or pod eviction.

Example configuration:

minAvailable: 1

This guarantees that at least one pod remains available.

Resource Limits

CPU and memory limits were configured for containers to prevent resource exhaustion.

Example:

cpu: 250m
memory: 256Mi

This ensures stable cluster performance.

Verifying Deployment

The following commands were used to verify that all components were running correctly.

Check pods:

kubectl get pods

Check services:

kubectl get svc

Check ingress:

kubectl get ingress

Check autoscaling:

kubectl get hpa
