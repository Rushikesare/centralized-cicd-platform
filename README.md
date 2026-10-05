# Centralized CI/CD Platform

A centralized CI/CD platform that automates application validation, Docker image building, deployment, and health verification using GitHub Actions, Jenkins, Docker, and AWS EC2.

## 🛠️ Technologies Used

- **Cloud:** AWS EC2
- **CI:** GitHub Actions
- **CD:** Jenkins
- **Containerization:** Docker
- **Web Server:** Nginx
- **Version Control:** Git & GitHub
- **Operating System:** Ubuntu Linux
- **Automation:** GitHub Webhooks

## 🔄 CI/CD Workflow

1. Developer pushes code to the GitHub repository.
2. GitHub Actions automatically validates the project.
3. GitHub Actions builds the Docker image.
4. GitHub Webhook triggers the Jenkins pipeline.
5. Jenkins pulls the latest source code.
6. Jenkins validates the application files.
7. Jenkins builds and tags the Docker image.
8. Jenkins deploys the application container on AWS EC2.
9. Jenkins performs an application health check.
10. Successful deployment is confirmed.

## 🚀 Key Features

- Automated CI pipeline using GitHub Actions
- Automated CD pipeline using Jenkins
- GitHub Webhook integration for automatic deployments
- Docker-based application containerization
- Application deployment on AWS EC2
- Automated Docker image build and tagging
- Application health check after deployment
- Infrastructure hosted on Ubuntu Linux
- Version-controlled source code using Git and GitHub

## 📁 Project Structure

```text
centralized-cicd-platform/
├── .github/
│   └── workflows/
│       └── ci.yml
├── app/
│   └── index.html
├── docs/
│   ├── architecture.png
│   ├── github-actions.png
│   └── jenkins-cd-proof.png
├── Dockerfile
├── Jenkinsfile
└── README.md

## Architecture

![Centralized CI/CD Platform Architecture](docs/architecture.png)

### GitHub Actions CI

The GitHub Actions workflow validates project files, validates HTML, and builds the Docker image on every push to the `main` branch.

![GitHub Actions CI](docs/github-actions.png)

## Continuous Deployment with Jenkins

Jenkins automates the deployment process after changes are pushed to GitHub.

### Jenkins CD Pipeline

The Jenkins pipeline performs the following steps:

1. Checks out the latest source code from GitHub
2. Validates application files
3. Builds the Docker image
4. Tags the Docker image
5. Removes the previous application container
6. Deploys the new Docker container on AWS EC2
7. Performs an application health check
8. Confirms successful deployment

### Jenkins Pipeline Execution

<p align="center">
  <img src="docs/jenkins-cd-proof.png" alt="Jenkins CD Pipeline" width="850">
</p>

The pipeline completed successfully with `Finished: SUCCESS`.

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
