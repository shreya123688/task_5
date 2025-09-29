# 🚀 Kubernetes Minikube Node.js Deployment

This project demonstrates how to deploy a simple **Node.js web server** on a **Kubernetes cluster using Minikube**. It includes a Dockerized Node.js app, Kubernetes Deployment, and Service configuration.

---

## 📁 Project Structure
```
kubernetes-minikube-node-demo/
│── README.md
│── deployment.yaml
│── service.yaml
│── screenshots/ # (to be added manually)
│── src/
│ ├── Dockerfile
│ ├── package.json
│ └── server.js
```
---

## 🛠 Prerequisites

- ✅ Docker
- ✅ Minikube
- ✅ kubectl
- ✅ Git

---

## 🧱 1. Build & Push Docker Image

```bash
cd src
docker build -t kube-node-demo .
docker tag kube-node-demo <your-dockerhub-username>/kube-node-demo
docker push <your-dockerhub-username>/kube-node-demo
```
![Install Dependencies](screenshots/docker_desktop.png)
![Install Dependencies](screenshots/docker_hub.png)
## 📦 2. Deploy to Kubernetes
```
minikube start
```
![Install Dependencies](screenshots/start.png)
```
kubectl apply -f deployment.yaml
```
![Install Dependencies](screenshots/deployment.png)
```
kubectl apply -f service.yaml
```
![Install Dependencies](screenshots/service.png)
## Check status:
```
kubectl get pods
kubectl get svc
```
![Install Dependencies](screenshots/pods.png)
## 🌐 3. Access the App
```
minikube service node-service
```
![Install Dependencies](screenshots/node_service.png)
![Install Dependencies](screenshots/website.png)
## 📈 4. Scale the Deployment
```
kubectl scale deployment node-deployment --replicas=3
kubectl get pods
```
![Install Dependencies](screenshots/scale.png)
## Notes
We have a fully working Kubernetes deployment with a Node.js application running on Minikube. This demonstrates Dockerization, Kubernetes objects, scaling, and service exposure.
