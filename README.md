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
🔹 Step 2: EC2 Setup
bash
Copy code
# Launch Ubuntu instance
# SSH into instance
🔹 Step 3: Install AWS CLI v2
bash
Copy code
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo apt install unzip
unzip awscliv2.zip
sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin --update
aws configure
🔹 Step 4: Install Docker
bash
Copy code
sudo apt-get update
sudo apt install docker.io
docker ps
sudo chown $USER /var/run/docker.sock
🔹 Step 5: Install kubectl
bash
Copy code
curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin
kubectl version --short --client
🔹 Step 6: Install eksctl
bash
Copy code
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
eksctl version
🔹 Step 7: Setup EKS Cluster
bash
Copy code
eksctl create cluster --name three-tier-cluster --region us-west-2 --node-type t2.medium --nodes-min 2 --nodes-max 2
aws eks update-kubeconfig --region us-west-2 --name three-tier-cluster
kubectl get nodes
🔹 Step 8: Run Manifests
bash
Copy code
kubectl create namespace workshop
kubectl apply -f .
kubectl delete -f .
🔹 Step 9: Install AWS Load Balancer
bash
Copy code
curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json
aws iam create-policy --policy-name AWSLoadBalancerControllerIAMPolicy --policy-document file://iam_policy.json
eksctl utils associate-iam-oidc-provider --region=us-west-2 --cluster=three-tier-cluster --approve
eksctl create iamserviceaccount --cluster=three-tier-cluster --namespace=kube-system --name=aws-load-balancer-controller --role-name AmazonEKSLoadBalancerControllerRole --attach-policy-arn=arn:aws:iam::626072240565:policy/AWSLoadBalancerControllerIAMPolicy --approve --region=us-west-2
🔹 Step 10: Deploy AWS Load Balancer Controller
bash
Copy code
sudo snap install helm --classic
helm repo add eks https://aws.github.io/eks-charts
helm repo update eks
helm install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system --set clusterName=my-cluster --set serviceAccount.create=false --set serviceAccount.name=aws-load-balancer-controller
kubectl get deployment -n kube-system aws-load-balancer-controller
kubectl apply -f full_stack_lb.yaml
🧹 Cleanup
bash
Copy code
# Delete EKS Cluster
eksctl delete cluster --name three-tier-cluster --region us-west-2

# Clean up resources to avoid costs
# - Stop or Terminate EC2 instance
# - Delete Load Balancer
# - Delete Security Groups created during setup
⭐ Project Completed Successfully — Three-Tier App with CI/CD, Monitoring, and GitOps!

yaml
Copy code

---

Would you like me to make a **second version** of this README — keeping the same content but adding **
