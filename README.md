
# 🚀 Three-Tier Web Application Challenge  

**Get The Challenge Here** 🏁  

---

## 🧩 Prerequisites
- 🐳 Basic knowledge of **Docker** and **AWS Services**  
- ☁️ An **AWS Account** with necessary permissions  

---

## 🧭 Challenge Steps
- [📦 Application Code](#application-code)
- [⚙️ Jenkins Pipeline Code](#jenkins-pipeline-code)
- [🏗️ Jenkins Server Terraform](#jenkins-server-terraform)
- [☸️ Kubernetes Manifests Files](#kubernetes-manifests-files)
- [📘 Project Details](#project-details)

---

## 📦 Application Code
The **`Application-Code`** directory contains the source code for the **Three-Tier Web Application**.  
Dive into this directory to explore the **frontend** and **backend** implementations.

---

## ⚙️ Jenkins Pipeline Code
Inside the **`Jenkins-Pipeline-Code`** directory, you'll find **Jenkins pipeline scripts** that automate the **CI/CD process**, ensuring smooth integration and deployment of your application.

---

## 🏗️ Jenkins Server Terraform
Explore the **`Jenkins-Server-TF`** directory to find **Terraform scripts** for setting up the **Jenkins Server on AWS**.  
These scripts simplify the infrastructure provisioning process.

---

## ☸️ Kubernetes Manifests Files
The **`Kubernetes-Manifests-Files`** directory holds **Kubernetes manifests** for deploying your application on **AWS EKS**.  
Understand and customize these files to suit your project needs.

---

## 📘 Project Details

### 🛠️ Tools Explored
- 🧱 **Terraform** & **AWS CLI** for AWS infrastructure  
- 🔁 **Jenkins**, **SonarQube**, **Terraform**, **Kubectl**, and more for CI/CD setup  
- 📊 **Helm**, **Prometheus**, and **Grafana** for Monitoring  
- 🚀 **ArgoCD** for GitOps practices  

---

### 🚢 High-Level Overview
- 👤 IAM User setup & Terraform magic on AWS  
- ⚙️ Jenkins deployment with AWS integration  
- ☸️ EKS Cluster creation & Load Balancer configuration  
- 🐳 Private ECR repositories for secure image management  
- 📈 Helm charts for efficient monitoring setup  
- 🌈 GitOps with ArgoCD — the cherry on top!  

📈 **This journey covers everything from setting up tools to deploying a full Three-Tier app**, ensuring **data persistence** and a **complete CI/CD pipeline**.

---

## 🏁 Getting Started

To get started, check this **[comprehensive guide](https://amanpathakdevops.medium.com/advanced-end-to-end-devsecops-kubernetes-three-tier-project-using-aws-eks-argocd-prometheus-fbbfdb956d1a)**.  
It walks you through:
- IAM user setup  
- Infrastructure provisioning  
- CI/CD pipeline configuration  
- EKS cluster creation  
and more.

---

### 🔹 Step 1: IAM Configuration
```bash
# Create a user eks-admin with AdministratorAccess
# Generate Access Key & Secret Key
