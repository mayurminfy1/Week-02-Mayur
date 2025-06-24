# Github-Actions Take home Assignment
##  GitHub Actions CI/CD Pipeline

👉 **Open this to see successful actions: [Github Actions](https://github.com/mayurminfy1/github_action-takehome/actions)**


A fully automated pipeline that builds, containers, and deploys a Node.js web app to an EC2 instance using GitHub Actions, Docker, and GitHub Container Registry (GHCR).

---

## Project Structure
```
GITHUB-ACTION/
├── app.js                    
├── package.json              
├── package-lock.json         
├── Dockerfile                 
├── .gitignore                
└── .github/
    └── workflows/
        └── cicd-pipeline.yml  
```

---

##  Project Learning Outcomes

### Concepts You’ll Master:

| Concept                     | Explanation                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| **GitHub Actions**         | Automate your development workflow end-to-end                              |
| **Docker**                 | Package your app in a consistent, portable environment                     |
| **GitHub Container Registry (GHCR)** | Secure image hosting integrated with GitHub                        |
| **EC2 Deployment via SSH** | Real-world deployment pipeline to a Linux-based cloud server               |
| **Secrets Management**     | Securely pass credentials using GitHub Secrets                             |

---

## EC2 Deployment Overview

| Configuration     | Value                        |
|-------------------|------------------------------|
| Instance Type     | t2.micro (Free Tier)         |
| OS                | Amazon Linux 2023            |
| User              | ec2-user                     |
| Open Ports        | 22 (SSH), 3000 (Web App)     |
| Docker Installed  | Manually using `yum`         |
---

##  GitHub Repository Secrets

Add these secrets under **GitHub > Settings > Actions > Secrets and variables > Repository secrets**:

| Secret Name     | Description                                     |
|------------------|-------------------------------------------------|
| `EC2_HOST`       |  43.205.99.236            |
| `EC2_USERNAME`   | `ec2-user`  |
| `EC2_SSH_KEY`    | The **entire content** of your `.pem` key file (confidential) |

---

# ✅ Steps to Implement CI/CD with GitHub Actions, Docker & EC2

---

## 1️⃣ Setup Node.js App

- Created `GITHUB-ACTION/` folder.
- Wrote a basic Express server in `app.js`.
- Initialized `package.json` and added `.gitignore`.

---

## 2️⃣ Dockerize the App

- Created a `Dockerfile` using `node:alpine`.
- Installed dependencies and exposed port `3000`.

---

## 3️⃣ Push to GitHub

- Pushed code to GitHub repo: `github_action-takehome`.

---

## 4️⃣ Setup GitHub Actions

- Added `.github/workflows/cicd-pipeline.yml`.
- Defined `build` (push to GHCR) and `deploy` (EC2 SSH) jobs.

---

## 5️⃣ Configure Secrets

Added in GitHub repo settings:

- `EC2_HOST` → EC2 IP (`43.205.99.236`)
- `EC2_USERNAME` → `ec2-user`
- `EC2_SSH_KEY` → Contents of `.pem` key

---

## 6️⃣ Launch EC2 Instance

- Launched **Amazon Linux 2023**, **t2.micro**.
- Opened ports `22` and `3000`.
- Installed Docker manually using `yum`.

---

## 7️⃣ Trigger CI/CD

- `git push` triggered GitHub Actions:
  - Built & pushed Docker image to GHCR.
  - Logged into EC2 and deployed the container.
  
---


## ✅ Fixes & Debugging

- Fixed missing `"start"` script in `package.json`.
- Used `:main` tag to pull latest Docker image.

---



### 📸 Screenshots

| Description                   | Preview |
|------------------------------|---------|
| EC2 Instance Launched        | ![EC2 Instance](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20174117.png?raw=true) |
| Security Group Configuration | ![Security Group](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20174217.png?raw=true) |
| SSH Access to EC2            | ![SSH Access](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20174024.png?raw=true) |
| Docker Installed Manually    | ![Docker Install](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20173958.png?raw=true) |
| GitHub Actions Workflow Run  | ![Workflows](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20180051.png?raw=true) |
| Application Live on EC2      | ![Live App](https://github.com/mayurminfy1/photos/blob/main/github-actions/Screenshot%202025-06-22%20180027.png?raw=true) |

 ---

## 🌐 Access Your App

After successful deployment, visit your application in the browser using the EC2 public IP:

🔗 **[http://43.205.99.236:3000/](http://43.205.99.236:3000/)**

---


### Real-World Relevance

This is exactly how modern teams build, test, and deploy applications — automatically, reliably, and securely.

You're now ready to apply this knowledge to real-world projects or take your DevOps learning even further! 

---
---


# Kubernetes- Takehome assignment
#  MongoDB + Mongo Express Deployment on Kubernetes

A complete setup of a MongoDB database and a Mongo Express web UI deployed on a Minikube cluster using Kubernetes best practices like `Secrets`, `ConfigMaps`, `Deployments`, and `Services`.

---

### Overview

| Section         | Details |
|----------------|---------|
| **Objective** | Deploy a full-stack web app using Kubernetes on Minikube — MongoDB backend with a Mongo Express frontend. |
| **Background** | This project simulates a real-world web application architecture using Kubernetes components: Pods, Services, Secrets, and ConfigMaps. |
| **Prerequisites** | 	<ul><li>✅ Minikube installed and running</li><li>✅ kubectl configured</li><li>✅ VS Code or any text editor</li></ul>|

---

### Kubernetes Commands

| Command | What It Does |
|--------|---------------|
| `kubectl apply -f <file>.yaml` | Create Kubernetes resources |
| `kubectl get all` | View status of pods, services, deployments |
| `kubectl delete -f <file>.yaml` | Delete resources |
| `minikube service mongo-express-service` | Launch the Mongo Express UI in browser |

---

## 📁 Folder Structure

![Folder structure](https://github.com/mayurminfy1/photos/blob/main/kubernetes-takehome/Screenshot%202025-06-21%20160025.png?raw=true)

### 📸 Screenshots

| Description                   | Preview |
|-------------------------------|---------|
| Starting Minikube     | ![Starting Minikube](https://github.com/mayurminfy1/photos/blob/main/kubernetes-takehome/Screenshot%202025-06-21%20160104.png?raw=true) |
| All pods working| ![All pods](https://github.com/mayurminfy1/photos/blob/main/kubernetes-takehome/Screenshot%202025-06-21%20155933.png?raw=true) |
| Mongo-Express-Service     | ![Service](https://github.com/mayurminfy1/photos/blob/main/kubernetes-takehome/Screenshot%202025-06-21%20160002.png?raw=true) |
| Mongo Express         | ![Mongo Express](https://github.com/mayurminfy1/photos/blob/main/kubernetes-takehome/Screenshot%202025-06-21%20155749.png?raw=true) |
| CleanUp         | ![Cleanup](https://github.com/mayurminfy1/photos/blob/main/kubernetes-takehome/Screenshot%202025-06-21%20160233.png?raw=true) |


---

### Creating Secret

```
# PowerShell base64 encoding:
[Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes("my-admin-user"))
# Output: bXktYWRtaW4tdXNlcg==

[Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes("my-super-secret-password"))
# Output: bXktc3VwZXItc2VjcmV0LXBhc3N3b3Jk
```
---

## Summary

This project demonstrates container orchestration using Kubernetes:

Secure secrets with Secret

Environment management with ConfigMap

Expose services via LoadBalancer

Real-world separation of backend and frontend via Services Summary

---
---

# Docker-Advanced Assignment
# Visitor Counter App using Node.js & Redis (Manual Docker Deployment)

This is a simple two-tier web application that counts page visits using a Node.js server and a Redis database. Each time a user visits the site, the app increments the counter stored in Redis and displays the total number of visits.

---

## 📁 Project Structure

```
visitor-app/
├── Dockerfile
├── index.js
└── package.json
```
---

## Technologies Used

- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- [Redis](https://redis.io/)
- [Docker](https://www.docker.com/)

---

## Create the Docker Image for Node.js App
```
docker build -t my-visitor-app .
```
---


## Create a Docker Network
```
docker network create visitor-app-net

```
---
## Run Redis Container
```
docker run -d --name redis-server --network visitor-app-net redis


```
---

## Run Node.js Container
```
docker run -d --name web-app --network visitor-app-net -p 4000:8081 my-visitor-app



```
---

## Open in Browser
```
http://localhost:4000




```
---

### 📸 Screenshots

| Description                   | Preview |
|-------------------------------|---------|
| Creating Network and running Container     | ![Starting ](https://github.com/mayurminfy1/photos/blob/main/docker-takehome/Screenshot%202025-06-21%20215734.png?raw=true)  ![Starting ](https://github.com/mayurminfy1/photos/blob/main/docker-takehome/Screenshot%202025-06-21%20215829.png?raw=true) |
| No of counts| ![counts](https://github.com/mayurminfy1/photos/blob/main/docker-takehome/Screenshot%202025-06-21%20215908.png?raw=true) |
| CleanUp     | ![cleanup](https://github.com/mayurminfy1/photos/blob/main/docker-takehome/Screenshot%202025-06-21%20220017.png?raw=true) |

---
## Conclusion
This project demonstrates how to manually deploy a simple two-tier application using Docker. By separating the backend (Node.js app) and the data store (Redis) into isolated containers connected via a custom Docker network, we gain:

Modularity: Each component runs in its own environment.

Portability: The entire setup works across any machine with Docker installed.

Clear Networking: Using Docker's internal DNS, containers communicate reliably without hardcoding IP addresses.

Hands-On Understanding: Performing each step manually helps build foundational knowledge of how containers, images, networks, and ports work together.




