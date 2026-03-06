# Troubleshooting and Issues Faced

During the implementation of this project, several issues were encountered while deploying and configuring the application. These issues helped in understanding real-world DevOps troubleshooting scenarios.

---

## 1. Docker Image Pull Errors

### Issue
Pods failed to start with the following error:

ImagePullBackOff  
ErrImagePull

### Cause
Kubernetes was unable to pull the Docker images due to incorrect image names or missing images in Docker Hub.

### Resolution
- Verified images were pushed to Docker Hub
- Updated deployment manifests with correct image names
- Redeployed the applications

Example command used:

kubectl describe pod <pod-name>

---

## 2. Kubernetes API Timeout

### Issue
kubectl commands became very slow or timed out.

### Cause
The EC2 instance was running with insufficient resources which caused the Kubernetes API server to become unresponsive.

### Resolution
- Checked system resource usage
- Recreated the EC2 instance with better resources
- Reinstalled the K3s cluster

---

## 3. Redis and PostgreSQL Not Deployed

### Issue
Application pods were running but Redis and PostgreSQL services were missing.

### Cause
Kubernetes manifests for Redis and PostgreSQL were not initially deployed.

### Resolution
Created deployment and service manifests for:

- Redis
- PostgreSQL

Then deployed them using:

kubectl apply -f redis-deployment.yaml  
kubectl apply -f db-deployment.yaml

---

## 4. Service Connectivity Issues

### Issue
Services inside the cluster were unable to communicate.

Example:

wget http://vote

Resulted in connection errors.

### Cause
Incorrect service configuration or networking restrictions.

### Resolution
Verified service configuration using:

kubectl get svc

Tested internal connectivity using a temporary debugging pod:

kubectl run test --rm -it --image=busybox -- /bin/sh

---

## 5. Ingress Routing Problems

### Issue
The vote application was accessible but the result service returned:

Bad Gateway

### Cause
Incorrect ingress routing configuration.

### Resolution
Verified ingress rules using:

kubectl describe ingress

Updated routing configuration to ensure correct service mapping.

---

## 6. DNS Resolution Issues Inside Cluster

### Issue
Pods were unable to resolve service names.

Example:

nslookup vote

### Cause
Cluster DNS communication was restricted.

### Resolution
Verified CoreDNS functionality and adjusted network policies to allow DNS traffic.

---

## Summary

Troubleshooting during this project involved:

- Debugging container image issues
- Resolving Kubernetes networking problems
- Fixing service discovery errors
- Diagnosing cluster resource limitations
- Correcting ingress routing configurations

These troubleshooting steps helped simulate real-world DevOps deployment challenges.
