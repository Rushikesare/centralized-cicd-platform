# Centralized CI/CD Platform

A centralized CI/CD platform that automates application build, containerization, deployment, and health verification using Jenkins, GitHub, Docker, and AWS EC2.

## Architecture

GitHub → GitHub Webhook → Jenkins → Docker → AWS EC2 → Health Check

## Technologies Used

- AWS EC2
- Ubuntu
- Git
- GitHub
- GitHub Webhooks
- Jenkins
- Docker
- Nginx
- Bash
- HTML

## Project Structure

```text
centralized-cicd-platform/
├── app/
│   └── index.html
├── Dockerfile
├── Jenkinsfile
└── README.md
