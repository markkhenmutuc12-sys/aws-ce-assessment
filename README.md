# AWS CE Technical Assessment

## Overview
This project is part of my AWS Cloud Engineer technical assessment.  
It demonstrates how to build, containerize, and deploy a simple ReactJS web application using AWS services and CI/CD automation through GitHub Actions.

## Application
The application is a simple **ReactJS** app that displays:

"Hello World!"

It serves as the main observable output for this assessment.

## CI/CD Workflow Summary

### 1. **Build and Artifact Upload**
- When changes are pushed to the main branch, GitHub Actions automatically:
  - Builds the React app  
  - Zips the build output with a timestamp  
  - Uploads the artifact to an **S3 bucket**

### 2. **Docker Image Build and Push**
- Another workflow builds the Docker image and pushes it to **Amazon ECR (Elastic Container Registry)**.  
- The Docker image includes the production-ready React build served through NGINX.

### 3. **CloudFormation Deployment**
- The final step deploys the Docker image to **AWS ECS (Fargate)** using a CloudFormation template.  
- The stack creates an ECS service that automatically runs the containerized app.


## Security and Configuration
All AWS credentials and environment variables are securely stored in **GitHub Secrets**.  
They are never exposed directly in the repository or workflow files.

Secrets used:
- `AWS_ACCESS_KEY_ID`  
- `AWS_SECRET_ACCESS_KEY`  
- `AWS_REGION`  
- `S3_BUCKET`  
- `ECR_REPOSITORY`  
- `AWS_ACCOUNT_ID`


## AWS Resources Used
- **S3 Bucket** — for storing build artifacts  
- **ECR Repository** — for Docker image storage  
- **ECS Fargate** — for container deployment  

## Summary
This project demonstrates:
- Building and packaging a ReactJS app  
- Automating builds using GitHub Actions  
- Securely integrating AWS with GitHub  
- Deploying a containerized application to AWS ECS (Fargate)


**Author:** Mark Khen Mutuc  
**Date:** October 16, 2025
