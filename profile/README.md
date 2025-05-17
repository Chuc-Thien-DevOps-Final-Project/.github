# ☕️ Go CoffeeShop Deployment Organization

## 🏢 Organization Purpose

This GitHub organization was created to support the final DevOps assignment for my internship. The goal is to provision, deploy, and operate a microservices-based web application called **Go CoffeeShop** 🚀 in both **development** and **production** environments using DevOps practices.

---
## ⚙️ Summary

### 🏗️ Infrastructure as Code (IaC)

* Leveraging **Terraform** to provision core infrastructure resources, including:
    * ☁️ EC2 Instances
    * ☸️ EKS Cluster
    * VPC (Virtual Private Cloud)
    * 🛡️ Security Groups

### 🚀 Application Deployment

* **Dev (Development Environment):**
    * Deployed on a single **EC2 instance**.
    * 🐳 **Docker** and **Docker Compose** are installed on the EC2 instance.
    * Application services are defined in the `docker-compose.yml` file.
    * 🩺 Health checks are configured for PostgreSQL and RabbitMQ.
* **Prod (Production Environment):**
    * A ☸️ **EKS cluster** is provisioned using Terraform, consisting of **2 t3.large EC2 worker nodes**.
    * Application components are deployed via **Kubernetes YAML manifests**.
    * 📈 **HPA** (Horizontal Pod Autoscaler) is configured for the `proxy` and `web-frontend` Deployments.
    * 🌐 Integration with **Route 53** for DNS management and 🔒 **Cert-Manager** for automated **HTTPS** certificate provisioning.
* **💾 Database:**
    * Utilizing **Amazon RDS** with **PostgreSQL** (free-tier).
    * 🔑 Database credentials are securely managed in **AWS Secrets Manager**.
    * The RDS instance resides within a **private subnet** with Security Group rules restricting network access.

## 🔄 CI/CD (Continuous Integration/Continuous Delivery)

* **GitHub Actions** is employed to build CI/CD pipelines, which includes:
    * Automated provisioning and teardown of the development environment.
    * 🛡️ Automated **container image scanning** using **Trivy** with email notifications.
    * 📤 Pushing the validated container image to a private **ECR** (Elastic Container Registry).
    * ✍️ Automatically updating the image tag in `docker-compose.yml` and Kubernetes YAML manifests.
    * 🔔 Notifications upon pipeline completion.
* **CD (Continuous Delivery)** is implemented via **Argo CD** following a **GitOps pull-based model**.

## 📊 Monitoring

* The system is monitored using **Datadog**.
* Key performance indicators (KPIs) are collected, including:
    * CPU Utilization
    * Memory Utilization
    * HTTP Request Statistics (4xx Client Errors / 5xx Server Errors)
    * HPA Status
* 🚨 Alert if:
    * 📈 HPA current replicas `>=` HPA max replicas
    * ⚠️ CPU Usage exceeds 80% threshold
    * ⚠️ 5xx Server Errors are occurring

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
