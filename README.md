# 🚀 CI-Pipeline - Spring Boot CI/CD Deployment Demo

A minimal **Spring Boot REST API** project created to demonstrate a complete **CI/CD pipeline workflow** using **GitHub Actions, Self-Hosted Runner, AWS EC2, Maven, and automated deployment**.

The project automatically builds, packages, and deploys the Spring Boot application whenever changes are pushed to the `main` branch.

---

# 📌 Project Overview

This project demonstrates how a developer can automate the software delivery process:

```
Developer
    |
    | git push main
    ↓
GitHub Repository
    |
    ↓
GitHub Actions Workflow
    |
    ↓
Self-Hosted Runner (AWS EC2 Ubuntu)
    |
    ↓
Maven Build
    |
    ↓
Spring Boot JAR Creation
    |
    ↓
Deploy Application
    |
    ↓
Spring Boot Service Running on Port 8081
```

---

# 🛠️ Tech Stack

| Technology         | Purpose                                |
| ------------------ | -------------------------------------- |
| Java 21            | Backend development                    |
| Spring Boot 4.1.0  | REST API framework                     |
| Spring Web MVC     | Creating REST endpoints                |
| Maven              | Build and dependency management        |
| GitHub Actions     | CI/CD automation                       |
| Self-hosted Runner | Executes pipeline on AWS EC2           |
| AWS EC2 Ubuntu     | Deployment server                      |
| Nginx              | Reverse proxy (deployment environment) |

---

# 📂 Project Structure

```
CI-Pipeline/
│
├── README.md
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
└── pipeline/
    │
    ├── mvnw
    ├── mvnw.cmd
    ├── pom.xml
    │
    └── src/
        │
        ├── main/
        │   ├── java/com/osagani/ci/pipeline/
        │   │
        │   │── PipelineApplication.java
        │   │
        │   └── controller/
        │       └── TestController.java
        │
        └── resources/
            └── application.properties
```

---

# ⚙️ Application Configuration

`application.properties`

```properties
spring.application.name=pipeline
server.port=8081
```

Application runs on:

```
http://localhost:8081
```

---

# 🔗 API Endpoint

| Method | Endpoint        | Description              |
| ------ | --------------- | ------------------------ |
| GET    | `/api/v1/tests` | Application health check |

Example response:

```
Success! CI/CD Pipeline is working
```

---

# 🔄 CI/CD Pipeline Workflow

The GitHub Actions pipeline performs the following steps:

### 1. Checkout Code

Downloads the latest source code from GitHub.

### 2. Setup Java Environment

Installs:

```
Java 21
Maven
```

### 3. Build Application

Runs:

```bash
mvn clean package
```

Creates:

```
target/pipeline-0.0.1-SNAPSHOT.jar
```

### 4. Stop Existing Application

Checks port `8081` and stops the previous running version.

### 5. Deploy New Version

Starts the latest Spring Boot JAR:

```bash
java -jar pipeline-0.0.1-SNAPSHOT.jar
```

---

# ⚡ GitHub Actions Workflow

The pipeline runs automatically when code is pushed:

```yaml
on:
  push:
    branches:
      - main
```

The job executes on an AWS EC2 self-hosted runner:

```yaml
runs-on: self-hosted
```

---

# ☁️ AWS EC2 Deployment

The application is deployed on:

```
AWS EC2
Ubuntu Linux
Java 21
Spring Boot
Port: 8081
```

The self-hosted runner allows GitHub Actions to execute deployment commands directly on the EC2 instance.

---

# 📸 Screenshots

## GitHub Actions Successful Pipeline

*Add GitHub Actions screenshot here*

Example:

```
![GitHub Actions Success](screenshots/github-actions-success.png)
```

---

## AWS EC2 Deployment

*Add EC2 deployment screenshot here*

Example:

```
![EC2 Deployment](screenshots/ec2-deployment.png)
```

---

## Running Spring Boot Application

*Add running application screenshot here*

Example:

```
![Spring Boot Running](screenshots/application-running.png)
```

---

# 🚀 Running Locally

## Clone Repository

```bash
git clone https://github.com/OsaganiDev/CI-Pipeline.git
```

Navigate:

```bash
cd CI-Pipeline/pipeline
```

---

## Build Project

Using Maven Wrapper:

Linux/Mac:

```bash
./mvnw clean package
```

Windows:

```bash
mvnw.cmd clean package
```

---

## Run Application

```bash
java -jar target/pipeline-0.0.1-SNAPSHOT.jar
```

---

# 🧪 Testing

Run:

```bash
./mvnw test
```

The project includes Spring Boot context loading tests.

---

# 🎯 Learning Objectives

This project demonstrates practical experience with:

✅ Git & GitHub workflow
✅ CI/CD concepts
✅ GitHub Actions
✅ Self-hosted runners
✅ AWS EC2 deployment
✅ Maven automation
✅ Spring Boot deployment
✅ Linux server management

---



# 👨‍💻 Author

**Osagani Perera**

GitHub:
https://github.com/OsaganiDev

---

⭐ This repository is created as a hands-on DevOps learning project demonstrating a real CI/CD deployment workflow.
