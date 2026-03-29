# 🚀 DevOps Pipeline Implementation – Web Application

## 📌 Overview

This project demonstrates the implementation of a **complete DevOps pipeline** for a web application in an environment where no DevOps practices existed.

The goal was to automate the software delivery lifecycle using modern DevOps tools and best practices.

---

## 🛠️ Tools & Technologies

* Node.js / React (Vite)
* Jenkins (CI/CD)
* Docker
* Terraform (Infrastructure as Code)
* AWS EC2
* ESLint (Code Quality)

---

## 🏗️ Architecture

GitHub → Jenkins → Docker → AWS EC2 → Application Deployment
                ↓
             Terraform (Infrastructure)

---

## 📁 Project Structure

```
project-root/
│
├── Jenkinsfile
├── Dockerfile
├── package.json
│
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── provider.tf
│   ├── outputs.tf
│
└── README.md
```

---

## 🔁 CI/CD Pipeline (Jenkins)

The Jenkins pipeline automates the entire workflow:

### Pipeline Stages

1. **Checkout Code**

   * Pulls source code from GitHub

2. **Install Dependencies**

   ```
   npm install
   ```

3. **Lint**

   * Checks code quality using ESLint

   ```
   npm run lint
   ```

4. **Test (Optional)**

   ```
   npm test
   ```

5. **Build Docker Image**

   ```
   docker build -t indie-gems:latest .
   ```

6. **Deploy Application**

   ```
   docker run -d -p 4000:80 indie-gems:latest
   ```

---

## 🐳 Docker Setup

The application is containerized using a multi-stage Dockerfile:

* Stage 1: Build application using Node.js
* Stage 2: Serve using Nginx

### Run Locally

```
docker build -t app .
docker run -d -p 4000:80 app
```

---

## 🏗️ Infrastructure as Code (Terraform)

Terraform is used to provision AWS infrastructure.

### Resources Created

* EC2 Instance
* Security Group (ports 22, 80, 4000)
* Networking configuration

### Commands

```
cd terraform
terraform init
terraform plan
terraform apply
```

---

## 🌐 Application Access

After deployment, open in browser:

```
http://<EC2-PUBLIC-IP>:4000
```

---

## 📊 Monitoring (Optional)

Monitoring can be implemented using:

* Prometheus
* Grafana

---

## ⚠️ Challenges Faced

* Docker permission issue in Jenkins → Fixed by adding Jenkins user to Docker group
* Missing lint script → Added ESLint configuration
* JSON syntax error → Corrected package.json
* Maven used incorrectly → Replaced with npm commands

---

## 🚀 Future Improvements

* Push Docker images to DockerHub
* Add CI triggers (webhooks)
* Implement monitoring (Prometheus & Grafana)
* Use Kubernetes for deployment

---

## 👨‍💻 Author

**Prabha Patnala**
DevOps Engineer
