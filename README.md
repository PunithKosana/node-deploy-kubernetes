## Node.js Application CI/CD Pipeline
This project demonstrates the automation of building, pushing a Docker image to Docker Hub, and deploying it to an Amazon EKS cluster using GitHub Actions.

# Prerequisites:
Before setting up the pipeline, ensure the following:

# AWS Setup:
Create an Amazon EKS cluster and configure it using AWS CLI.
Ensure the Kubernetes kubectl command-line tool is installed and configured for the cluster.

# Docker Hub:
A Docker Hub account with credentials for pushing Docker images.
GitHub Secrets: Add the following secrets to your GitHub repository under Settings > Secrets and Variables > Actions:

`AWS_ACCESS_KEY_ID`: Your AWS access key ID.
`AWS_SECRET_ACCESS_KEY`: Your AWS secret access key.
`DOCKER_USERNAME`: Your Docker Hub username.
`DOCKER_PASSWORD`: Your Docker Hub password.
Kubernetes Deployment File: Include a deployment.yml file in the repository for deploying the application to EKS.

# CI/CD Pipeline Overview:
The GitHub Actions workflow automates the following steps:

# Test the Application:
Checks out the repository.
Installs dependencies and runs tests for the Node.js application.

# Build and Push Docker Image:

Builds a Docker image for the application.
Pushes the image to Docker Hub.

# Deploy to Amazon EKS:

Configures AWS credentials and kubectl for EKS.
Deploys the application using the deployment.yml file.

# Workflow Configuration:

The GitHub Actions workflow file .github/workflows/deploy.yml is set up to:

Run tests on every pull request and push to the main branch.
Build and push the Docker image upon a successful test run.
Deploy the application to EKS using the deployment.yml file.
