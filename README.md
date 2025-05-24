# CloudQR: Scalable QR Code Service with DevOps Pipeline

A full-stack QR Code Generator web application built with **FastAPI** and **Next.js**, containerized with Docker, and deployed on **AWS EKS** using **Kubernetes** and **Terraform**. CI/CD workflows are powered by **GitHub Actions**.

## 🚀 Features

* Generate QR codes for any valid URL
* Download and view stored QR codes
* RESTful FastAPI backend
* Responsive Next.js frontend
* Cloud-native, scalable deployment on AWS EKS
* CI/CD with GitHub Actions

---

## 🛠️ Tech Stack

| Area     | Technology                             |
| -------- | -------------------------------------- |
| Frontend | Next.js, Tailwind CSS                  |
| Backend  | FastAPI, Python                        |
| Infra    | Terraform, AWS EKS, Kubernetes         |
| CI/CD    | GitHub Actions, Docker, Docker Hub     |
| Storage  | AWS S3 (for saving generated QR codes) |

---

## 📁 Project Structure

```
Complete-Devops-Project/
├── .github/                # GitHub Actions workflows
├── api/                    # FastAPI backend app
├── front-end-nextjs/       # Next.js frontend app
├── infrastructure/         # Terraform scripts for AWS EKS provisioning
├── backend.yaml            # Kubernetes manifest for backend deployment
├── frontend.yaml           # Kubernetes manifest for frontend deployment
├── LICENSE
└── README.md
```

---

## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Smriti-ELigar/Complete-Devops-Project.git
cd Complete-Devops-Project
```

### 2. Build and Push Docker Images

Ensure Docker is installed and running:

```bash
# Backend
docker build -t smoothy10/qr-api:latest ./api
docker push smoothy10/qr-api:latest

# Frontend
docker build -t smoothy10/qr-frontend:latest ./front-end-nextjs
docker push smoothy10/qr-frontend:latest
```

---

## ☁️ Deployment (AWS EKS)

### 1. Provision AWS EKS with Terraform

```bash
cd infrastructure/
terraform init
terraform apply
```

Make sure your AWS credentials and IAM permissions are set properly.

### 2. Deploy to Kubernetes

```bash
kubectl apply -f backend.yaml
kubectl apply -f frontend.yaml
```

---

## 🔁 CI/CD with GitHub Actions

This project includes GitHub Actions workflows that:

* Automatically build and push Docker images on pushes to `main`
* Tag images and trigger deployment pipelines

Workflow files are located in `.github/workflows/`.

---

## 🌐 Accessing the App

Once deployed, the app will be accessible via the LoadBalancer URL:

```bash
kubectl get svc qr-frontend-service
```

You’ll see an `EXTERNAL-IP` which you can open in your browser.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---


