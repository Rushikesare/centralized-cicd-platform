# Centralized CI/CD Platform

A centralized CI/CD platform that automates application validation, Docker image building, deployment, and health verification using GitHub Actions, Jenkins, Docker, and AWS EC2.

## Architecture

```text
Developer
    |
    | git push
    v
GitHub
    |
    +--------------------+
    |                    |
    v                    v
GitHub Actions        GitHub Webhook
    |                    |
    | CI                 v
    |                 Jenkins
    |                    |
    |                    v
    |                 Docker
    |                    |
    |                    v
    |                 AWS EC2
    |                    |
    |                    v
    |               Health Check
    |
    v
Docker Image Build
