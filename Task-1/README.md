# Kubernetes Cluster Setup using Minikube on Windows

This project demonstrates how to create and configure a local Kubernetes cluster on a Windows machine using **Minikube** with the **Docker driver**.

---

## Prerequisites

Ensure the following are installed and working properly:

- [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)
- [Chocolatey Package Manager](https://chocolatey.org/install)
- Windows PowerShell (Run as Administrator)

---

##  Installation Steps

### 1. Install Kubernetes CLI (`kubectl`)
```powershell
choco install kubernetes-cli -y
Verify installation:

powershell
Copy
Edit
kubectl version --client
2. Install Minikube
powershell
Copy
Edit
choco install minikube -y
Verify installation:

powershell
Copy
Edit
minikube version
Start Kubernetes Cluster Using Docker Driver
If you previously started Minikube with a different driver like hyperv, delete the old cluster first:

powershell
Copy
Edit
minikube delete
Now start a fresh cluster using Docker:

powershell
Copy
Edit
minikube start --driver=docker
This will download necessary images and create a local Kubernetes cluster in a Docker container.

Verify Cluster Status
powershell
Copy
Edit
minikube status
kubectl get nodes
Expected output:

pgsql
Copy
Edit
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   Xs    v1.33.1

Notes
Docker must be running before starting Minikube.

If you face image pull issues inside the container, check Docker networking or proxy settings.

You can now use kubectl to deploy applications on your local Kubernetes cluster.

Resources
Kubernetes Official Docs

Minikube Documentation

YouTube Tutorial on AKS & Architecture

Author
Vaishnavi Borase
B.Tech CSE (Data Science), RCPIT
Minikube Kubernetes Lab - July 2025
