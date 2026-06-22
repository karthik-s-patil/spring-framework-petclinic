## Project Overview

This project demonstrates the implementation of a complete CI/CD (Continuous Integration and Continuous Deployment) pipeline using AWS and DevOps tools. The pipeline automates the process of building, testing, analyzing, storing, and deploying a Java web application.

## Architecture

Developer → GitHub → Jenkins → SonarQube → Nexus → Tomcat → Users

### Workflow

1. Developer pushes source code to GitHub.
2. Jenkins automatically triggers the pipeline.
3. Jenkins checks out the latest code from GitHub.
4. Maven builds the application and generates the WAR artifact.
5. SonarQube performs static code analysis and validates code quality.
6. The generated artifact is uploaded to Nexus Repository Manager.
7. Jenkins deploys the artifact to the Tomcat server.
8. Users access the deployed application through a web browser.

## Technologies Used

* AWS EC2
* GitHub
* Jenkins
* Maven
* SonarQube
* Nexus Repository
* Apache Tomcat
* Java

## Infrastructure Setup

| Service   | Purpose                       |
| --------- | ----------------------------- |
| Jenkins   | CI/CD Automation Server       |
| SonarQube | Code Quality Analysis         |
| Nexus     | Artifact Repository           |
| Tomcat    | Application Deployment Server |
| GitHub    | Source Code Management        |

## Jenkins Pipeline Stages

### 1. Source Code Checkout

Pulls the latest source code from GitHub.

### 2. Build

Builds the application using Maven.

### 3. SonarQube Analysis

Performs code quality and security checks.

### 4. Upload Artifact

Publishes the generated WAR file to Nexus Repository.

### 5. Deployment

Deploys the artifact to Apache Tomcat.


## Key Features

* Automated CI/CD workflow
* Continuous Integration with Jenkins
* Code Quality Analysis using SonarQube
* Artifact Management using Nexus
* Automated Deployment to Tomcat
* Infrastructure hosted on AWS EC2

## Outcome

Successfully implemented an end-to-end CI/CD pipeline that automates code integration, quality validation, artifact management, and deployment of a Java web application on AWS.
