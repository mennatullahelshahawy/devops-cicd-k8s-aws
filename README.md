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


### 2 Load Image into Kind Cluster
```bash
kind load docker-image devops-app:latest

### 3 Deploy to kubernetes
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml


### 3 Check pods status
```bash
kubectl get pods

### 5 Expose App:
```bash
kubectl port-forward service/devops-service 8080:80 --address 0.0.0.0

Then open http://localhost:8080