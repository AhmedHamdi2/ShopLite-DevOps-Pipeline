# ShopLite DevOps Pipeline

This project demonstrates the implementation of a full CI/CD pipeline for the ShopLite web application. The pipeline is built using Jenkins to automate the following stages:

- **Build**: Docker images for frontend and backend services.
- **Test**: Automated testing of the application components.
- **Deploy**: Deploy the services to a Kubernetes cluster using Helm.

## Architecture

The ShopLite application consists of:
- **Frontend**: React-based UI.
- **Backend**: Node.js-based API and a Python authentication service.
- **Database**: MongoDB and Redis for persistence.

The CI/CD pipeline is automated using Jenkins and ensures that the application is continuously built, tested, and deployed to a Kubernetes environment.

## Requirements

- Jenkins installed and configured with Docker and Kubernetes plugins.
- Minikube for local Kubernetes clusters.
- Helm for Kubernetes deployments.
- Docker to build images.
- GitHub repository for source code hosting.

## Setup Instructions

1. Clone this repository to your local machine.
2. Set up Jenkins with the necessary plugins (Docker, Kubernetes, GitHub).
3. Create Jenkins pipelines using the provided `Jenkinsfile`.
4. Run Jenkins jobs to automate the build, test, and deploy process.

## How to Run Locally

1. Clone the repository:

   ```bash
   git clone https://github.com/AhmedHamdi2/shoplite-devops-pipeline.git
