# React Application Deployment to AWS EC2 using GitHub Actions

This README provides guidance on deploying a React application to an AWS EC2 instance using GitHub Actions. The deployment process involves building a Docker image, pushing it to a container registry, and then deploying it to AWS EC2.

## Prerequisites

Before proceeding, ensure you have the following:

- An AWS Account
- A GitHub account with a repository for your React application.

## Secrets Configuration

Sensitive information required for the deployment process is stored as secrets in your GitHub repository. Here’s what you need to set up:

1. `AWS_ACCESS_KEY_ID`: Your AWS access key ID.
2. `AWS_SECRET_ACCESS_KEY`: Your AWS secret access key.
3. `AWS_REGION`: Your AWS secret access key.
4. `AWS_ACCOUNT_ID`: Your AWS secret access key.
5. `ECR_REPOSITORY`: Your Docker Hub username (or your container registry username).
6. `EC2_SSH_KEY`: Your Docker Hub password (or your container registry password).
7. `EC2_INSTANCE_IP`: Your AWS EC2 instance's public IP address.

To add these secrets:

1. Go to your GitHub repository.
2. Click on `Settings` > `Secrets`.
3. Click `New repository secret`.
4. Add each secret with its respective key and value.

## Docker Configuration

Your application should have a `Dockerfile` in the root of the repository. Here’s an example `Dockerfile` for a React application:

## GitHub Actions Workflow

Create a `.github/workflows/deployment.yml` file in your repository. This file defines the GitHub Actions workflow for deploying your application. Here’s an example workflow:

This workflow triggers on pushes to the `main` branch. It builds the Docker image, pushes it to Docker Hub, and then deploys it to the AWS EC2 instance.
