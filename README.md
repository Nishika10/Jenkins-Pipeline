# Simple Jenkins CI/CD Pipeline (HTML + Nginx + Docker)

## Overview
This project demonstrates a **basic CI/CD pipeline using Jenkins** to automate the process of building and deploying a simple static website served by **Nginx** inside a **Docker container**.

---

## Tools & Technologies
- **Jenkins** – Continuous Integration / Continuous Deployment (CI/CD)
- **Docker** – Containerization platform
- **Nginx** – Web server for hosting static HTML content
- **Git & GitHub** – Version control and source code hosting
- **HTML/CSS** – Frontend for the demo website

---
## Steps to Reproduce Locally

1. Clone the Repository
```bash
git clone https://github.com/Nishika10/Jenkins-Pipeline.git
cd Jenkins-Pipeline
```

2. Build the Docker Image
```bash
docker build -t html-nginx-demo .
```

3. Run the Container
```bash
docker run -d --name html-nginx-container -p 8080:80 html-nginx-demo
```

Now open your browser at 👉 http://localhost:8080

## Jenkins Pipeline Setup
1. Open Jenkins Dashboard

- Make sure Jenkins is installed and running.
- Access Jenkins at: http://localhost:8080

2. Create a New Pipeline

- Click on “New Item” → Pipeline → OK

- Under Pipeline → Definition, select Pipeline script from SCM

- Choose Git and enter your repo URL

- Save and click Build Now

3. Observe Stages

- Checkout: Pulls latest code

- Build: Builds Docker image

- Deploy: Runs Nginx container automatically

## Learning Outcome

- By completing this task, you will learn:

- How Jenkins automates CI/CD pipelines

- How to containerize and deploy an app with Docker

- How to trigger builds automatically on Git commits



