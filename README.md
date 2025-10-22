# 🚀 vProfile – CI/CD Pipeline using GitHub Actions

This repository implements a complete **CI/CD pipeline** for the `vProfile` multi-tier Java web application using **GitHub Actions**, **AWS ECR**, and **EKS**.  
The workflow automates testing, code analysis, image building, and Helm-based deployment to a Kubernetes cluster.

---

## 🧩 Tech Stack

**Application**
- Java 11 • Spring MVC • Spring Security • Spring Data JPA • JSP • MySQL 8  

**DevOps & CI/CD**
- GitHub Actions  
- Maven 3 • SonarQube • Docker  
- AWS ECR (image registry)  
- AWS EKS (Kubernetes cluster)  
- Helm (application deployment)

---

## ⚙️ CI/CD Workflow Overview

| Stage | Description |
|--------|-------------|
| 🧪 **Testing** | Runs Maven unit tests and Checkstyle validation |
| 🔍 **Static Analysis** | Executes SonarQube scan & enforces quality gate |
| 🐳 **Build & Push** | Builds Docker image and pushes to AWS ECR |
| ☸️ **Deploy to EKS** | Deploys Helm chart to EKS cluster |

Triggered automatically on every **push to the `main`** branch.  
All credentials and tokens (AWS & SonarQube) are stored securely in **GitHub Secrets**.

---

## 🗃️ Database Setup (Local Testing)

```bash
sudo apt-get update
sudo apt-get install mysql-server
mysql -u <username> -p accounts < src/main/resources/db_backup.sql
