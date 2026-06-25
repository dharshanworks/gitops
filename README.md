# GitOps Platform Using ArgoCD

## 📌 Objective

Implement a GitOps deployment platform using **ArgoCD** to automatically deploy applications from a Git repository to a Kubernetes cluster.

---

## 🏗️ Architecture

```
Git Commit
     │
     ▼
GitHub Repository
     │
     ▼
ArgoCD
     │
     ▼
Kubernetes Cluster (EKS / Minikube)
```

---

## 📂 Repository Structure

```
gitops/
├── dev/
│   ├── deployment.yaml
│   └── service.yaml
│
├── qa/
│   ├── deployment.yaml
│   └── service.yaml
│
└── prod/
    ├── deployment.yaml
    └── service.yaml
```

Each folder represents an independent deployment environment.

- **dev** – Development Environment
- **qa** – Quality Assurance Environment
- **prod** – Production Environment

---

## 🛠️ Technologies Used

- Kubernetes
- ArgoCD
- Git
- GitHub
- Docker
- Minikube / Amazon EKS
- kubectl

---

## 🚀 Features

- GitOps-based Deployment
- Automatic Synchronization
- Self Healing
- Resource Pruning
- Environment-wise Deployment
- Declarative Kubernetes Manifests

---

## ⚙️ Prerequisites

- Docker Desktop
- Kubernetes Cluster (Minikube or Amazon EKS)
- kubectl
- Git
- ArgoCD Installed
- GitHub Repository

---

## 📦 Installation

### Clone Repository

```bash
git clone https://github.com/<username>/gitops.git
cd gitops
```

---

### Install ArgoCD

```bash
kubectl create namespace argocd
```

```bash
kubectl apply -n argocd \
-f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

---

### Access ArgoCD

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Open

```
https://localhost:8080
```

---

## 🔑 Login Credentials

Username

```
admin
```

Password

```bash
kubectl -n argocd get secret argocd-initial-admin-secret
```

---

## 📁 Kubernetes Manifests

Each environment contains

```
deployment.yaml
service.yaml
```

These manifests are automatically deployed by ArgoCD.

---

## 🔄 GitOps Workflow

```
Developer
     │
Git Commit
     │
Git Push
     │
GitHub Repository
     │
ArgoCD detects changes
     │
Automatic Synchronization
     │
Kubernetes Cluster
```

---

## ✅ Auto Sync

Whenever a new commit is pushed to GitHub,

ArgoCD automatically synchronizes the Kubernetes cluster with the latest manifests.

---

## ✅ Self Heal

If any Kubernetes resource is manually modified or deleted,

ArgoCD automatically restores it to the desired state stored in Git.

---

## ✅ Pruning

If a manifest is removed from Git,

ArgoCD automatically removes the corresponding resource from the Kubernetes cluster.

---

## 📸 Demo Flow

```
Git Commit
      │
      ▼
Git Push
      │
      ▼
GitHub
      │
      ▼
ArgoCD
      │
      ▼
Automatic Deployment
      │
      ▼
Kubernetes Cluster
```

---

## 📈 Advantages of GitOps

- Single Source of Truth
- Automated Deployments
- Version Controlled Infrastructure
- Easy Rollback
- Faster Recovery
- Improved Collaboration
- Secure Deployment Process

---

## 📚 Learning Outcomes

After completing this exercise, you will understand:

- GitOps Principles
- ArgoCD Installation
- Kubernetes Manifest Management
- Continuous Deployment
- Environment-based Deployment
- Auto Sync
- Self Healing
- Resource Pruning

---

## 👨‍💻 Author

**Dharshan R**

B.Tech Information Technology

DevOps & Cloud Enthusiast
