# AI-Assisted CI/CD Pipeline Automation with GitHub Actions for Containerized Node.js Application on AWS

## Project Overview

This project demonstrates an end-to-end AI-assisted CI/CD pipeline using GitHub Actions, Docker, DockerHub, and AWS EC2.

The pipeline automatically builds the Node.js application, runs tests, builds and pushes a Docker image to DockerHub, and deploys the latest container to AWS EC2 — all triggered by a single git push.

GitHub Repository: https://github.com/Mohanm1995/automated-cicd-pipeline-nodejs-on-aws

DockerHub Image: https://hub.docker.com/r/mohanmanp/node-app

---

## Architecture Flow

Developer Pushes Code to GitHub  
        ↓  
GitHub Actions Pipeline Triggered  
        ↓  
Job 1: Test — Install Dependencies and Run Tests  
        ↓  
Job 2: Docker — Build Image and Push to DockerHub  
        ↓  
Job 3: Deploy — SSH into EC2, Pull Image, Run Container  
        ↓  
Containerized Node.js Application Live on AWS EC2

---

## Technologies Used

- GitHub Actions
- Docker
- DockerHub
- AWS EC2
- Ubuntu 22.04
- Node.js 22
- Linux
- Git and GitHub

---

## Features

- Automated CI/CD pipeline with 3 separate jobs
- Multi-stage CI/CD workflow with job dependencies
- AI-assisted workflow generation
- Dockerized Node.js application
- Automated EC2 deployment on every push
- DockerHub integration
- GitHub Secrets management
- SSH-based remote deployment
- Error handling implementation
- Test stage integration

---

## Project Structure

.
├── app.js  
├── package.json  
├── Dockerfile  
├── .gitignore  
└── .github  
    └── workflows  
        └── deploy.yml  

---

## GitHub Actions Workflow

Workflow Path:

.github/workflows/deploy.yml

### Job 1 — test

1. Checkout source code
2. Setup Node.js 22
3. Install dependencies
4. Run tests

### Job 2 — docker (runs only after test passes)

5. Checkout source code
6. Docker login
7. Build Docker image
8. Push image to DockerHub

### Job 3 — deploy (runs only after docker passes)

9. SSH into EC2
10. Pull latest Docker image
11. Stop and remove old container
12. Run updated container on port 3000

---

## AWS EC2 Configuration

### EC2 Details

- AMI: Ubuntu 22.04 LTS
- Instance Type: t3.small
- Docker installed
- Git installed
- Node.js installed

### Security Group Ports

| Port | Purpose |
|------|----------|
| 22 | SSH |
| 3000 | Containerized Node.js Application |
| 80 | HTTP |

---

## GitHub Secrets Used

| Secret Name | Purpose |
|-------------|----------|
| DOCKER_USERNAME | DockerHub username |
| DOCKER_PASSWORD | DockerHub password/token |
| EC2_HOST | EC2 public IP |
| EC2_USERNAME | EC2 SSH username |
| EC2_SSH_KEY | Private SSH key |

---

## Deployment Process

Whenever code is pushed to the `main` branch:

1. GitHub Actions automatically triggers the workflow
2. Application dependencies are installed and tests are executed
3. Docker image is built and pushed to DockerHub
4. GitHub Actions connects to EC2 using SSH
5. Latest Docker image is pulled on EC2
6. Existing container is stopped and removed
7. Updated container is started and served on port 3000

The pipeline completes automated deployment within approximately 1 minute from code push to live deployment on EC2.

---

## AI Utilization in This Project

AI tools were used to accelerate:

- GitHub Actions workflow generation
- Dockerfile creation
- Deployment scripting
- CI/CD pipeline structuring
- Error handling improvements

Manual implementation included:

- AWS EC2 setup and configuration
- Docker installation on EC2
- GitHub Secrets configuration
- DockerHub repository setup
- SSH authentication debugging
- authorized_keys permission troubleshooting
- YAML syntax debugging
- Deployment validation

---

## Learning Outcomes

Through this project, I learned:

- CI/CD pipeline automation with GitHub Actions
- Multi-job pipeline design with job dependencies
- Docker containerization and image management
- DockerHub integration and image versioning
- AWS EC2 provisioning and configuration
- SSH-based automated deployment
- Linux file permission troubleshooting
- GitHub Secrets management
- AI-assisted DevOps workflow implementation

---

## Final Outcome

Successfully implemented an AI-assisted automated CI/CD pipeline using GitHub Actions for deploying a containerized Node.js application on AWS EC2.

The pipeline executes 3 sequential jobs — test, docker, and deploy — and performs end-to-end automated deployment from a single git push to the main branch.

---

## Author

**Mohan M** 

AWS & DevOps Engineer (Fresher)

---
