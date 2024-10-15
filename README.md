# CI/CD Pipeline with GitHub , Docker and Jenkins
![maxraaesdefault](https://github.com/CydexCode/CI-CD-Pipeline-With-GitHub-Docker-and-Jenkins/assets/112784979/cfc74d18-62fd-4399-8997-658edcac82b0)

This repository contains code for setting up a Continuous Integration/Continuous Deployment (CI/CD) pipeline using Docker and Jenkins. The pipeline automates the process of building, testing, and deploying applications, ensuring efficiency and consistency in software development workflows.

CI/CD Pipeline with GitHub , Docker and Jenkins -> [Step by Step Tutorial](https://medium.com/@cydexcode/implementing-a-ci-cd-pipeline-with-github-jenkins-and-docker-bb5ae85c5a90)

## Overview

The CI/CD pipeline involves the following steps:
![Screenshot 2024-06-16 181705](https://github.com/CydexCode/CI-CD-Pipeline-With-GitHub-Docker-and-Jenkins/assets/112784979/718b7228-44c4-4ab9-bd4d-1ea769d00cb9)

1. **GitHub Push :**
The CI/CD process begins when code changes are pushed to a GitHub repository. This could involve new features, bug fixes, or other updates. Developers commit their changes and push them to a specific branch in the repository.

2. **Jenkins Build Trigger :**
Jenkins, an open-source automation server, is configured to monitor the GitHub repository for changes. Jenkins is connected to GitHub using a webhook that triggers the build process whenever there is a new commit to the repository.

3. **Docker Image Creation ( Pull base image and build image ) :**
Upon detecting a new commit, Jenkins pulls the base Docker image from DockerHub and builds a Docker image that contains the application and its dependencies. This ensures that the application runs in a consistent environment, regardless of where it is deployed.

4. **Docker Image Push :**
Once the Docker image is successfully built, Jenkins pushes the image to DockerHub. DockerHub serves as a registry for Docker images, making the built image available for deployment in various environments.

5. **Update Status :**
After the Docker image is pushed to DockerHub, Jenkins updates the build status on GitHub. This provides visibility into the CI/CD process, allowing developers to see whether the build succeeded or failed directly from the GitHub interface.

6. **Notification :**
Users are notified of the build status through GitHub notifications. This immediate feedback loop ensures that developers are aware of the results of their commits, facilitating quick responses to any issues.

## Getting Started

To set up the CI/CD pipeline in your environment, follow these steps:

1. **Clone Repository**: Clone this repository to your local machine using the following command:
   ```
   git clone https://github.com/CydexCode/CI-CD-Pipeline-With-GitHub-Docker-and-Jenkin
   ```
2. **Configure Jenkins**: Set up Jenkins on your server and configure it to monitor the GitHub repository for changes. Install necessary plugins like Docker Pipeline Plugin.
3. **Set Up DockerHub**: Ensure you have an account on DockerHub where Jenkins can push Docker images. 
4. **Configure Pipeline**: In Jenkins, create a new pipeline job and configure it to use the provided Jenkinsfile in this repository.
5. **Trigger Build**: Trigger a build manually or make a code change in the repository to initiate the CI/CD pipeline.

## Requirements

- GitHub account
- Jenkins server
- DockerHub account
- Docker installed on Jenkins server

CI/CD Pipeline with GitHub , Docker and Jenkins -> [Step by Step Tutorial](https://medium.com/@cydexcode/implementing-a-ci-cd-pipeline-with-github-jenkins-and-docker-bb5ae85c5a90)
