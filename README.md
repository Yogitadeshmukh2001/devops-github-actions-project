# Automated CI/CD Pipeline for Flask Application

A hands-on DevOps project demonstrating an end-to-end CI/CD pipeline for a Python Flask application using Git, GitHub, GitHub Actions, Docker, Docker Hub, and AWS EC2.

## Project Overview

This project automates the process of testing, containerizing, and deploying a Flask application. Code changes are managed using Git and GitHub, automated tests are executed through GitHub Actions, the application is packaged into a Docker image, pushed to Docker Hub, and deployed on an AWS EC2 Ubuntu server.

## Technologies Used

Python | Flask | Pytest | Git | GitHub | GitHub Actions | Docker | Docker Hub | AWS EC2 | Linux

## Project Structure

devops-github-actions-project/
├── app/
│   ├── app.py
│   └── requirements.txt
├── tests/
│   └── test_app.py
├── .github/workflows/
│   └── ci.yml
├── Dockerfile
├── .dockerignore
├── .gitignore
└── pytest.ini

## Application Endpoints

- `/` - Application home page
- `/hello` - Hello API endpoint
- `/health` - Application health check

## CI/CD Workflow

Developer → Git → GitHub → GitHub Actions → Pytest → Docker Build → Docker Hub → AWS EC2 → Docker Container → Health Check

GitHub Actions automatically runs the test pipeline whenever code is pushed. After successful testing, the Docker image is built and pushed to Docker Hub. The image can then be deployed on the AWS EC2 Ubuntu server.

## Testing

Run automated tests using:

    pytest

Expected result:

    3 passed

## Docker

Build the application image:

    docker build -t devops-flask-app:1.0 .

Run the container:

    docker run -d --name devops-flask-app -p 5000:5000 devops-flask-app:1.0

Check the application:

    curl http://localhost:5000/
    curl http://localhost:5000/health

## AWS EC2 Deployment

Pull the Docker image from Docker Hub:

    docker pull docker.io/yogitadeshmukh/devops-github-actions-project:latest

Run the application on EC2:

    docker run -d --name devops-flask-app --restart unless-stopped -p 5000:5000 docker.io/yogitadeshmukh/devops-github-actions-project:latest

The application can then be accessed through the EC2 public IP on port 5000.

## GitHub Actions Secrets

The project uses GitHub Secrets for secure authentication:

- DOCKERHUB_USERNAME
- DOCKERHUB_TOKEN
- EC2_HOST
- EC2_USER
- EC2_SSH_KEY

## Project Outcome

This project demonstrates practical experience with Git and GitHub workflows, feature branches, automated testing, GitHub Actions CI/CD, Docker containerization, Docker Hub, Linux, and AWS EC2 deployment.

## Author

Yogita Deshmukh  
Cloud & DevOps Engineer  
GitHub: https://github.com/Yogitadeshmukh2001
