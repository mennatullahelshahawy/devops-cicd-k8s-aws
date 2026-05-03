# 🚀 Node.js CI/CD + Docker + Kubernetes DevOps Project

This project demonstrates a complete DevOps workflow including application development, containerization using Docker, and deployment on a Kubernetes cluster using Kind.

---

## 📌 Project Overview

A simple Node.js Express application that is:
- Containerized using Docker
- Deployed on a local Kubernetes cluster (Kind)
- Exposed using Kubernetes Service (NodePort)
- Tested using port-forwarding

---

## 🛠️ Tech Stack

- Node.js (Express)
- Docker
- Kubernetes (Kind)
- kubectl
- Git & GitHub

---

## ⚙️ How to Run the Project

### 1️ Build Docker Image
```bash
docker build -t devops-app:latest .
```

### 2 Load Image into Kind Cluster
```bash
kind load docker-image devops-app:latest
```
### 3 Deploy to kubernetes
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

### 4 Check pods status
```bash
kubectl get pods
```

### 5 Expose App:
```bash
kubectl port-forward service/devops-service 8080:80 --address 0.0.0.0
```
Then open http://localhost:8080


# 🚀 API Endpoints

- /-> Main endpoint (Hello message)
- /health -> Health check endpoint


# 📌 Kubernetes Architecture

- Deployment: Manages application pods
- Service: Express application internally/externally
- Kind Cluster: Local Kubernetes environment


# Key Learnings

- Docker image creation and containerization
- Kubernetes deployment and service configuration
- Debugging ImagePullBackOff issue
- Using kind for local kubernetes clusters
- Port-forwarding for local access

# Author Note

This project was built as a DevOps learning excercise to simulate a real-world CI/CD and container orchestration workflow.