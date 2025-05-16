# ☕️ Go CoffeeShop Deployment Organization

## 🏢 Organization Purpose

This GitHub organization was created to support the final DevOps assignment for my internship. The goal is to provision, deploy, and operate a microservices-based web application called **Go CoffeeShop** 🚀 in both **development** and **production** environments using best DevOps practices, including:

-   **Infrastructure as Code (IaC):** 🏗️ Terraform
-   **Environment Separation:** ↔️ Development and Production
-   **CI/CD Pipelines:** ⚙️ GitHub Actions
-   **GitOps:** 🚀 ArgoCD
-   **Monitoring and Health Checks:** 🩺
-   **Secure Credential Management:** 🔒 AWS Secrets Manager

---

## 📂 Repositories Overview

### 1. [`coffeeshop-manifests`](https://github.com/Chuc-Thien-DevOps-Final-Project/go-coffeshop)

**Purpose:** Stores all deployment configurations.

-   **Production:** ☸️ Kubernetes YAML files (EKS)
-   **Development:** 🐳 Docker Compose files (EC2)
-   **CI/CD:** ⚙️ GitHub Actions
    -   Image scanning (🔍 Trivy)
    -   Image push (📤 Docker private registry)
    -   Auto-deployment (🚀 ArgoCD - Production, 🐳 Docker Compose - Development)

**Technologies:** ☸️ Kubernetes · 🐳 Docker Compose · ⚙️ GitHub Actions · 🚀 ArgoCD · 🔍 Trivy · Traefik · 🔒 Secret Manager

---

### 2. [`coffeeshop-infrastructure`](https://github.com/Chuc-Thien-DevOps-Final-Project/infrastructure)

**Purpose:** Contains Infrastructure-as-Code (IaC) using Terraform.

-   **Development:** ☁️ EC2 instances with Docker Compose
-   **Production:** ☸️ EKS cluster with ArgoCD
-   **Environment Management:** 🗂️ Terraform Workspaces
-   **State Management:** 📦 Remote S3 Backend

**Technologies:** 🏗️ Terraform · ☁️ AWS (EC2, EKS, RDS, VPC, IAM) · 📦 S3 Backend · 🔒 AWS Secrets Manager

---


## ✅ Exam Coverage

This organization addresses the following final exam requirements:

-   ✅ Infrastructure provisioning with Terraform (Development & Production)
-   ✅ CI/CD pipeline via GitHub Actions
-   ✅ Development deployment via Docker Compose on EC2
-   ✅ Production deployment on EKS with GitOps (ArgoCD)
-   ✅ PostgreSQL via AWS RDS (Free Tier) using Secrets Manager
-   ✅ Health checks and horizontal pod autoscaling
-   ✅ System monitoring using Datadog

---

## 📚 Reference Source Code

Source Code (microservices): [https://github.com/thangchung/go-coffeeshop](https://github.com/thangchung/go-coffeeshop)

## 📬 Contact

For any questions, contact me:

📧 chucthien2@gmail.com
