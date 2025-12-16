🚀 Two-Tier Flask Application Deployment using Kubernetes & Helm

This project demonstrates the end-to-end DevOps workflow for deploying a two-tier web application using Flask (frontend) and MySQL (backend) with modern cloud-native tools such as Docker, Kubernetes, Helm, and AWS.

The focus of this project is containerization, orchestration, Helm packaging, and scalable deployment following DevOps best practices.

📌 Architecture Overview

Frontend: Flask Web Application
Backend: MySQL Database
Containerization: Docker & Docker Compose
Orchestration: Kubernetes (Minikube / Kubeadm)
Packaging: Helm Charts
Cloud Platform: AWS EC2 (Local setup) / AWS EKS (Future enhancement)

🧱 Project Architecture
User
  │
  ▼
LoadBalancer / NodePort
  │
  ▼
Flask Application (Kubernetes Deployment)
  │
  ▼
MySQL Database (Kubernetes StatefulSet / Deployment)

🔧 Tools & Technologies Used

Docker

Docker Compose

Kubernetes

Helm

AWS EC2

Minikube

kubectl

Git & GitHub

Linux (Ubuntu)

🐳 Step 1: Dockerizing the Application

Created Dockerfiles for:

Flask application

MySQL database

Built Docker images locally

Pushed images to Docker Hub for version control

docker build -t <docker-username>/flask-app .
docker push <docker-username>/flask-app

☸️ Step 2: Kubernetes Setup

Created a local Kubernetes cluster using Minikube

Verified cluster status using kubectl

minikube start
kubectl get nodes

📦 Step 3: Kubernetes Manifests

Created Kubernetes YAML files for:

Flask Deployment

MySQL Deployment / StatefulSet

Services (ClusterIP / NodePort)

ConfigMaps and Secrets

kubectl apply -f k8s/

🧭 Step 4: Helm Packaging

Created a Helm chart to package all Kubernetes manifests

Parameterized values using values.yaml

Enabled easy upgrades and rollbacks

helm create two-tier-app
helm install two-tier-app ./two-tier-app

🔄 Step 5: Application Deployment

Deployed the application using Helm

Verified running pods and services

kubectl get pods
kubectl get svc

📈 Key Features

Modular and reusable Helm charts

Scalable Kubernetes deployment

Separation of frontend and backend services

Cloud-ready architecture

Supports easy migration to AWS EKS

📊 Result

Successfully deployed a two-tier Flask application on Kubernetes

Enabled scalability, high availability, and easier configuration management

Reduced deployment complexity using Helm packaging

🚀 Future Enhancements

Migrate setup to AWS EKS

Add CI/CD pipeline using GitHub Actions

Implement Ingress Controller

Add Horizontal Pod Autoscaler (HPA)

Integrate Monitoring & Logging (Prometheus + Grafana)

📂 Project Structure
two-tier-flask-app-devops/
│
├── app.py
├── requirements.txt
├── message.sql
│
├── Dockerfile
├── Dockerfile-multistage
├── docker-compose.yml
│
├── Jenkinsfile
├── Makefile
│
├── templates/
│   └── index.html
│
├── k8s/
│   ├── mysql-deployment.yml
│   ├── mysql-pv.yml
│   ├── mysql-pvc.yml
│   ├── mysql-svc.yml
│   ├── two-tier-app-deployment.yml
│   ├── two-tier-app-pod.yml
│   ├── two-tier-app-svc.yml
│   └── README.md
│
├── eks-manifests/
│   ├── mysql-configmap.yml
│   ├── mysql-secrets.yml
│   ├── mysql-deployment.yml
│   ├── mysql-svc.yml
│   ├── two-tier-app-deployment.yml
│   └── two-tier-app-svc.yml
│
└── README.md


🤝 Connect With Me

👤 Iram Khan
🎓 Computer Science Engineering | Cloud & DevOps Enthusiast
🔗 LinkedIn: https://github.com/iramk596

⭐ If you like this project, don’t forget to star the repository!# two-tier-flask-app-devops
