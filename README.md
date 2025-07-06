# WordPress Deployment in Kubernetes with 2 Replicas

This project contains Kubernetes manifests to deploy a WordPress site with **2 replicas**, using a **MySQL database** as backend. The deployment uses `PersistentVolumeClaims` and `Services` to ensure reliable storage and communication.

## 🧾 Requirements

- [Minikube](https://minikube.sigs.k8s.io/docs/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- Docker or container runtime
- Internet access to pull official images

---
## How to deploy

### Start Minikube
minikube start

### Clone the repo and acces the folder 


### Apply MySQL and WordPress
kubectl apply -f mysql-deployment.yaml
kubectl apply -f wordpress-deployment.yaml
kubectl apply -f wordpress-service.yaml

### Access the WordPress site
minikube service wordpress

### Verify the status 
kubectl get pods
kubectl get svc

### Stop without deleting

kubectl scale deployment wordpress --replicas=0
kubectl scale deployment mysql --replicas=0

### Or delete everything

kubectl delete -f .
