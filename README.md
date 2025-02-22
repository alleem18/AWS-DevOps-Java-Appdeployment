# AWS DevOps Java Web App Deployment

## Author: Aleemuddin Mohammad  
**Email:** aleemuddin.work@gmail.com  

---

## Table of Contents
- [Introduction](#introduction)
- [Technologies](#technologies)
- [Project Breakdown](#project-breakdown)
  - [P1: Set Up a Web App in the Cloud](#p1-set-up-a-web-app-in-the-cloud)
  - [P2: Connect a GitHub Repo with AWS](#p2-connect-a-github-repo-with-aws)
  - [P3: Store Dependencies with AWS CodeArtifact](#p3-store-dependencies-with-aws-codeartifact)
  - [P4: Package an App with AWS CodeBuild](#p4-package-an-app-with-aws-codebuild)
  - [P5: Deploy an App with AWS CodeDeploy](#p5-deploy-an-app-with-aws-codedeploy)
- [Setup Instructions](#setup-instructions)
- [Contact]contact)

---

## Introduction
This repository documents my journey in deploying a Java-based web application using AWS services. The deployment pipeline automates the software release process using AWS DevOps tools such as EC2, CodeArtifact, CodeBuild, CodeDeploy, and GitHub.

![Image](https://github.com/alleem18/AWS-DevOps-Java-Appdeployment/blob/main/54100DBE-88CE-4B98-966B-F22534D5C160.jpeg)

---

## Technologies
- **Amazon EC2** - Hosting environment for the web application.
- **VSCode** - IDE for remote development via SSH.
- **GitHub** - Version control system for managing code changes.
- **AWS CodeArtifact** - Centralized repository for managing dependencies.
- **AWS CodeBuild** - Automates the build process.
- **AWS CodeDeploy** - Automates the deployment process.
- **AWS S3** - Stores build artifacts and deployment files.
- **AWS IAM** - Manages access permissions and roles.

---

## Project Breakdown

### P1: Set Up a Web App in the Cloud 
- GitHub Link : https://github.com/alleem18/WebApp-AWS-Setup
- Launched an **EC2 instance**.
- Configured **SSH access**.
- Set up **VSCode remote SSH** for seamless development.
- Installed **Java and Maven**.
- Created a **Java web application** using Maven archetype.
- Edited `index.jsp` using VSCode and nano.

### P2: Connect a GitHub Repo with AWS
- GitHub Link : https://github.com/alleem18/AWS-Devops-GitHub
- Installed and configured **Git**.
- Created a local **Git repository**.
- Set up **GitHub repository** and pushed the local project.
- Managed authentication using **GitHub tokens**.
- Resolved **merge conflicts** and updated files.

### P3: Store Dependencies with AWS CodeArtifact
- GitHub Link : https://github.com/alleem18/P3-Dependencies-Codeartifact
- Created **artifact repositories** for dependency management.
- Configured `settings.xml` for Maven to connect with **CodeArtifact**.
- Compiled the web app using **AWS-managed dependencies**.
- Defined **IAM policies** to secure repository access.

### P4: Package an App with AWS CodeBuild
- GitHub Link : https://github.com/alleem18/P4-PackageApp_with_Codebuild
- Created an **S3 bucket** to store build artifacts.
- Configured **AWS CodeBuild**:
  - Defined **Source** (GitHub repository).
  - Set up **Environment** (Managed Image for Java builds).
  - Configured **Artifacts** storage in **S3**.
  - Enabled **CloudWatch logging**.
- Wrote `buildspec.yml` to automate build steps.
- Modified **IAM roles** for permissions.
- Successfully **executed the first build**.

### P5: Deploy an App with AWS CodeDeploy
- GitHub Link : https://github.com/alleem18/P5-Deploy-App-with-CodeBuild
- Configured **EC2 instance & VPC** for deployment.
- Wrote **Bash scripts**:
  - `install_dependencies.sh` - Installs required software.
  - `start_server.sh` - Starts Tomcat & HTTPD services.
  - `stop_server.sh` - Stops Tomcat & HTTPD services.
- Created **IAM role for CodeDeploy**.
- Set up **CodeDeploy application & deployment group**.
- Deployed **web app from S3 to EC2 using CodeDeploy**.
- Successfully accessed deployed application via EC2 **public IPv4 address**.
- App : GitHub Link : https://github.com/alleem18/AWS-Devops-App

---

## Setup Instructions
To set up this project locally:

1. Clone the repository:
    ```bash
    git clone https://github.com/alleem18/AWS-DevOps-App.git
    ```
2. Navigate to the project directory:
    ```bash
    cd AWS-DevOps-App
    ```
3. Install dependencies:
    ```bash
    mvn install
    ```
4. Start the server:
    ```bash
    mvn jetty:run
    ```
5. Access the application at `http://localhost:8080`

---

## Contact
If you have any questions, feel free to reach out:
- **Email**: aleemuddin.work@gmail.com

---

## Conclusion
This project showcases the full AWS DevOps pipeline for deploying a Java web application. From development on EC2 to GitHub integration, dependency management with CodeArtifact, building with CodeBuild, and automated deployment with CodeDeploy, this project streamlines cloud-based application deployment.
