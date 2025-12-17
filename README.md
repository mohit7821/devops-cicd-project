# 🚀 CI/CD Pipeline using GitHub Actions and Docker on AWS EC2

## 📌 Project Overview
This project demonstrates a complete **CI/CD pipeline** that automatically builds and deploys a **Dockerized Node.js application** on an **AWS EC2 (Ubuntu t3.micro)** instance using **GitHub Actions**.

Whenever code is pushed to the `main` branch, GitHub Actions triggers an automated deployment to the EC2 server without any manual intervention.

---

## 🛠 Tools & Technologies Used
- **Git & GitHub** – Version control and source code management  
- **GitHub Actions** – CI/CD automation  
- **Docker** – Containerization of application  
- **AWS EC2 (Ubuntu)** – Cloud server for deployment  
- **Node.js** – Sample application  

---

## 🏗 Architecture
Developer
|
| Git Push
↓
GitHub Repository
|
| GitHub Actions (CI/CD)
↓
Docker Build & Run
|
↓
AWS EC2 (Ubuntu Server)


---

## ⚙️ Project Workflow
1. Developer pushes code to the `main` branch.
2. GitHub Actions pipeline is triggered.
3. Docker image is built on the EC2 server.
4. Existing container is stopped and removed.
5. New container is deployed automatically.
6. Application becomes live on EC2.

---

## 📂 Project Structure

devops-cicd-project/
│
├── app.js
├── Dockerfile
├── README.md
└── .github/
└── workflows/
└── deploy.yml

---

## 🐳 Dockerfile Explanation
- Uses official **Node.js base image**
- Copies application code
- Exposes application port
- Runs Node.js server

---

## 🤖 GitHub Actions Workflow
The pipeline is configured to:
- Trigger on push to `main`
- SSH into AWS EC2
- Build Docker image
- Run container on port `3000`

---

## 🔐 GitHub Secrets Used
| Secret Name | Description |
|------------|------------|
| `EC2_HOST` | EC2 Public IP Address |
| `EC2_USER` | SSH username (ubuntu) |
| `EC2_KEY`  | EC2 private SSH key |

---

## ▶ How to Run Manually (Optional)
```bash
docker build -t devops-app .
docker run -d -p 3000:3000 devops-app


