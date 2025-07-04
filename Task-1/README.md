#  Kubernetes Cluster Setup using Minikube on Windows

This project demonstrates how to create and configure a local Kubernetes cluster on a Windows machine using **Minikube** with the **Docker driver**.

---

##  Prerequisites

Ensure the following tools are installed and properly configured:

-  [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)
-  [Chocolatey Package Manager](https://chocolatey.org/install)
-  Windows PowerShell (Run as Administrator)

---

##  Installation Steps

### 1. Install Kubernetes CLI (`kubectl`)

```powershell
choco install kubernetes-cli -y
```

 **Verify installation:**
```powershell
kubectl version --client
```

---

### 2. Install Minikube

```powershell
choco install minikube -y
```

 **Verify installation:**
```powershell
minikube version
```

---

### 3. Start Kubernetes Cluster Using Docker Driver

If you previously used another driver (like `hyperv`), delete the existing cluster:

```powershell
minikube delete
```

Now, start a fresh cluster with the Docker driver:

```powershell
minikube start --driver=docker
```

 This command will download required images and configure a local Kubernetes cluster inside a Docker container.

---

##  Verify Cluster Status

```powershell
minikube status
kubectl get nodes
```

 **Expected Output:**
```
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   Xs    v1.33.1
```

---

##  Notes

-  **Docker Desktop** must be running before executing `minikube start`.
-  If you face image pull issues, check Docker proxy/network settings.
-  You can now deploy apps using `kubectl` to this local Kubernetes cluster.

---

##  Resources

- [Kubernetes Official Documentation](https://kubernetes.io/docs/home/)
- [Minikube Official Documentation](https://minikube.sigs.k8s.io/)
- [YouTube: AKS & Kubernetes Architecture](https://www.youtube.com/watch?v=c4nTKMU6fBU)

---

##  Author

**Vaishnavi Borase**  
B.Tech CSE (Data Science), RCPIT  
 *Minikube Kubernetes Lab - July 2025*
