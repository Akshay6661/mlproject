## End to End MAchine Learning Project

This app helps to predict Math_score on the basis of Gender, race_ethnicity, parental_level_of_education, lunch, test_preparation, reading_score, writing_score
The model here used is Linear Regression with the accurancy of 88.03.


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
