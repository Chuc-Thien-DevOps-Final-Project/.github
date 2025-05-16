# ☕️ Go CoffeeShop Deployment Organization

## 🏢 Organization Purpose

This GitHub organization was created to support the final DevOps assignment for my internship. The goal is to provision, deploy, and operate a microservices-based web application called **Go CoffeeShop** in both **development** and **production** environments using best DevOps practices, including:

- Infrastructure as Code (Terraform)
- Environment separation (Dev and Prod)
- CI/CD pipelines (GitHub Actions)
- GitOps with ArgoCD
- Monitoring and health checks
- Secure credential management (AWS Secrets Manager)

---

## 📂 Repositories Overview

### 1. [`coffeeshop-manifests`](https://github.com/Chuc-Thien-DevOps-Final-Project/go-coffeshop)

**Purpose:**  
Stores all deployment configurations including:

- **Kubernetes YAML files** for the production environment (EKS).
- **Docker Compose** files for the development environment (EC2).
- **CI/CD pipelines** using GitHub Actions:
  - Image scanning with Trivy
  - Image push to Docker private registry
  - Auto-deployment via ArgoCD (Prod) or Docker Compose (Dev)

**Technologies:**  
Kubernetes · Docker Compose · GitHub Actions · ArgoCD · Trivy · Traefik · Secret Manager 

---

### 2. [`coffeeshop-infrastructure`](https://github.com/Chuc-Thien-DevOps-Final-Project/infrastructure)

**Purpose:**  
Contains Infrastructure-as-Code (IaC) configurations using **Terraform** to provision cloud infrastructure on AWS.

- **Dev Environment:**  
  Deploy EC2 instances running Docker Compose
- **Prod Environment:**  
  Deploy an EKS cluster with ArgoCD for GitOps-based deployment
- Uses **Terraform Workspaces** to separate environments
- Uses **Remote S3 Backend** for state management

**Technologies:**  
Terraform · AWS (EC2, EKS, RDS, VPC, IAM) · S3 Backend · AWS Secrets Manager

---

## 🧱 Architecture Overview


💡**For detailed instructions on each repository, please refer to their individual README files.**

