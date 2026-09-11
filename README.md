# GitHub Actions Capstone

[![PR Pipeline](https://github.com/Aniruddhakharve/github-actions-capstone/actions/workflows/pr-pipeline.yml/badge.svg)](https://github.com/Aniruddhakharve/github-actions-capstone/actions/workflows/pr-pipeline.yml)

[![Main Pipeline](https://github.com/Aniruddhakharve/github-actions-capstone/actions/workflows/main-pipeline.yml/badge.svg)](https://github.com/Aniruddhakharve/github-actions-capstone/actions/workflows/main-pipeline.yml)

[![Scheduled Health Check](https://github.com/Aniruddhakharve/github-actions-capstone/actions/workflows/health-check.yml/badge.svg)](https://github.com/Aniruddhakharve/github-actions-capstone/actions/workflows/health-check.yml)

End-to-end CI/CD pipeline built with GitHub Actions.

## Application

This project uses a simple Python Flask application with:

- `/` - Application endpoint
- `/health` - Health check endpoint

## Technologies

- Python
- Flask
- Pytest
- Docker
- GitHub Actions
- Docker Hub

## CI/CD Pipeline

The pipeline performs:

1. Automated tests on pull requests
2. Build and test on the main branch
3. Docker image build and push to Docker Hub
4. Production deployment using GitHub Environments
5. Scheduled Docker health checks every 12 hours

## Pipeline Flow

```text
Pull Request
     ↓
Build + Test
     ↓
PR Checks
     ↓
Merge to main
     ↓
Build + Test
     ↓
Docker Build + Push
     ├── latest
     └── sha-<short-commit>
     ↓
Production Deployment
     ↓
Environment Approval
     ↓
Deploy

Every 12 Hours
     ↓
Health Check
     ↓
Pull Docker Image
     ↓
Run Container
     ↓
/health
     ↓
HTTP 200