#  Java Application CI/CD Pipeline

An end-to-end CI/CD pipeline implementation for a Java web application using Jenkins, Maven, SonarCloud, and Docker.

This project demonstrates automated build, static code analysis, containerization, and deployment of a cloud-ready application following DevOps best practices.

---

##  Project Objective

The objective of this project is to:

- Implement Continuous Integration (CI)
- Automate build & quality checks
- Integrate SonarCloud for static analysis
- Containerize the application using Docker
- Enable Continuous Deployment (CD)
- Simulate SaaS-style deployment workflow

This repository focuses on **CI/CD automation**, not application feature development.

---

##  CI/CD Pipeline Architecture

```
Developer
   │
   ▼
GitHub Repository
   │
   ▼
Jenkins Pipeline
   │
   ├── Checkout Code
   ├── Maven Build
   ├── SonarCloud Analysis
   ├── Docker Build
   └── Deploy Container
```

---

##  Pipeline Flow

1. Developer pushes code to GitHub
2. Jenkins automatically triggers pipeline
3. Maven builds the Java application
4. SonarCloud performs code quality analysis
5. Docker builds the application image
6. Container is deployed automatically

---

##  Tech Stack

- **GitHub** – Source Code Management
- **Jenkins** – CI/CD Automation
- **Maven** – Build Tool
- **SonarCloud** – Code Quality & Security Analysis
- **Docker** – Containerization
- **Linux** – Runtime Environment

---

##  Project Structure

```
java-application-ci-cd-pipeline/
│
├── DevOps-Project-01/
│   └── Java-Login-App/
│       ├── src/
│       ├── pom.xml
│       ├── Dockerfile
│       └── Jenkinsfile
│
└── README.md
```

---

#  Local Setup Guide

---

## 1️ Clone Repository

```bash
git clone https://github.com/sunila-k05/java-application-ci-cd-pipeline.git
cd java-application-ci-cd-pipeline/DevOps-Project-01/Java-Login-App
```

---

## 2️ Build Application Using Maven

```bash
mvn clean package
```

Generated artifact will be inside:

```
target/
```

---

## 3️ SonarCloud Analysis (Manual Run)

```bash
mvn sonar:sonar \
-Dsonar.projectKey=your_project_key \
-Dsonar.organization=your_org \
-Dsonar.host.url=https://sonarcloud.io \
-Dsonar.login=YOUR_SONAR_TOKEN
```

---

## 4️ Build Docker Image

```bash
docker build -t java-application-ci-cd .
```

Verify:

```bash
docker images
```

---

## 5️ Run Docker Container

```bash
docker run -d -p 8080:8080 --name java-app java-application-ci-cd
```

Access application:

```
http://localhost:8080
```

---

#  Jenkins Setup

---

## Start Jenkins (WAR method)

```bash
wget https://get.jenkins.io/war-stable/latest/jenkins.war
java -jar jenkins.war --httpPort=8081
```

Access:

```
http://localhost:8081
```

Retrieve initial password:

```bash
cat ~/.jenkins/secrets/initialAdminPassword
```

---

## Configure Jenkins Tools

Manage Jenkins → Global Tool Configuration:

- JDK → `jdk17`
- Maven → `maven3`

---

## Add Credentials

Add:
- GitHub credentials
- SonarCloud token (Secret Text)

---

#  What This Project Demonstrates

- Continuous Integration
- Continuous Deployment
- Automated Code Quality Checks
- Dockerized Application Deployment
- CI/CD Workflow Automation
- SaaS-style delivery model simulation

---

#  Future Improvements

- Kubernetes deployment
- AWS EC2 deployment
- Infrastructure as Code (Terraform)
- Monitoring integration (Prometheus & Grafana)
- Production-grade logging

---

#  License

This project is intended for learning and demonstration purposes.
