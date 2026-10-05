# Centralized CI/CD Platform

A centralized CI/CD platform that automates application validation, Docker image building, deployment, and health verification using GitHub Actions, Jenkins, Docker, and AWS EC2.

## Architecture

![Centralized CI/CD Platform Architecture](docs/architecture.png)

### GitHub Actions CI

The GitHub Actions workflow validates project files, validates HTML, and builds the Docker image on every push to the `main` branch.

![GitHub Actions CI](docs/github-actions.png)

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
