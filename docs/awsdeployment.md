# AWS Deployment

The Kubernetes cluster for this project was deployed on an AWS EC2 instance. AWS provides scalable cloud infrastructure which allows applications to run reliably in a production-like environment.

---

## EC2 Instance Setup

An Ubuntu-based EC2 instance was launched to host the Kubernetes cluster.

Configuration used:

Instance Type: t2.medium  
Operating System: Ubuntu Server  
Storage: 20 GB  
Security Groups:  
- SSH (22)  
- HTTP (80)  
- HTTPS (443)  
- NodePort Range (30000–32767)

This instance was used to install and run the Kubernetes cluster.

---

## Connecting to the EC2 Instance

After launching the instance, it was accessed using SSH.

Example command:

```bash
ssh -i voting-key.pem ubuntu@<EC2-PUBLIC-IP>

This allows secure remote access to the cloud server.

Kubernetes Cluster Installation

A lightweight Kubernetes distribution called K3s was installed on the EC2 instance.

Installation command:

curl -sfL https://get.k3s.io | sh -

K3s simplifies Kubernetes installation and is ideal for small clusters and learning environments.

Verifying the Cluster

After installation, the cluster was verified using:

kubectl get nodes

This confirms that the Kubernetes control plane and worker node are functioning correctly.

Deploying the Application

Once the Kubernetes cluster was ready, the application services were deployed using Kubernetes manifests.

Deployment steps:

kubectl apply -f vote-deployment.yaml
kubectl apply -f result-deployment.yaml
kubectl apply -f worker-deployment.yaml
kubectl apply -f redis-deployment.yaml
kubectl apply -f db-deployment.yaml

This created the required pods and services inside the Kubernetes cluster.

Exposing the Application

To allow external access to the application, an Ingress controller was used.

K3s includes Traefik Ingress Controller by default.

Ingress was configured to route incoming traffic to the appropriate services.

Example routing:

/ → vote service
/result → result service

Users can access the application through the EC2 public IP.

Example:

http://<EC2-PUBLIC-IP>
Monitoring Deployment

The following commands were used to monitor the deployment.

Check running pods:

kubectl get pods

Check services:

kubectl get svc

Check ingress:

kubectl get ingress

These commands help verify that the application is running correctly in the Kubernetes cluster.

Summary

AWS EC2 provided the cloud infrastructure required to host the Kubernetes cluster. By deploying the application on EC2, the project simulates a real-world production deployment environment where containerized applications are orchestrated using Kubernetes.
