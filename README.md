# GitHub Actions Capstone

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

The final pipeline will:

1. Run automated tests on pull requests
2. Build and test the application
3. Build and push a Docker image after merging to `main`
4. Deploy the image to the production environment
5. Perform scheduled Docker health checks

## Project Status

🚧 CI/CD pipeline is being built as part of the 90 Days of DevOps challenge#.