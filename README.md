## End to End MAchine Learning Project

This app helps to predict Math_score on the basis of Gender, race_ethnicity, parental_level_of_education, lunch, test_preparation, reading_score, writing_score
The model here used is Linear Regression with the accurancy of 88.03.

📘 Project Overview
🧠 Machine Learning Component (External Repo)

This project uses the ML pipeline, modules, and utilities from my main ML repository:
📌 https://github.com/Akshay6661/mlproject

That repository includes:

Data ingestion, transformation, training modules

Pipeline architecture

Training scripts and utilities

Model storage and loading logic

In this notebook, I only demonstrate or showcase the ML workflow, but the actual ML logic is sourced from the external ML project repo.

🐳 Dockerized Application

The application (using the ML package from the external repo) is containerized with Docker.

The Dockerfile contains instructions to install dependencies and run the ML app.

Ensures consistent behavior across local, staging, and production environments.

☁️ AWS ECR (Elastic Container Registry)

Built Docker images are pushed to AWS ECR.

ECR acts as a secure container registry for deployment.

GitHub Actions handles AWS authentication + pushing images automatically.

💻 AWS EC2 Deployment

The application runs on an AWS EC2 instance configured with Docker.

GitHub Actions remotely connects to EC2 (SSH) to:

Pull the latest image from ECR

Stop the old container

Start the updated version

This ensures every new commit automatically updates the running application.

🔄 Fully Automated CI/CD with GitHub Actions

A CI/CD pipeline is configured to:

CI: Continuous Integration

Install dependencies

Build Docker image

Run tests (if defined)

CD: Continuous Deployment

Authenticate to AWS

Push image to AWS ECR

Connect to EC2 and deploy the latest container

All deployments happen automatically on every commit or PR merge.

⭐ Key Features

Deployment-first architecture

Uses external ML project repo as dependency

Dockerized and production-ready

Automated CI/CD with GitHub Actions

AWS ECR for image storage

AWS EC2 for hosting the running application

Simple, scalable deployment flo

## steps to check till deployment 
Docker build check
workflow check
IAMuser check

## Docker setup in ECR commands in EC2 CLI

# optional
sudo apt-get update -y
sudo apt-get upgrade

# required

curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker

## Configure EC2 as self-hosted runner:

## Setup GitHub secrets:

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_REGION=us-east-1
AWS_ECR_LOGIN_URI=<demo> 506327416322.dkr.ecr.ap-south-1.amazonaws.com
ECR_REPOSITORY_NAME=simple-app
