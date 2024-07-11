# FastAPI Kubernetes Deployer

This project is a FastAPI application written in Python that allows you to deploy a given image on Kubernetes with specified parameters like deployment name and image name. Additionally, it monitors the Kubernetes cluster using the Prometheus client. The FastAPI application itself is deployed on a Kubernetes pod.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Usage](#usage)
- [Monitoring](#monitoring)
- [Contributing](#contributing)
- [License](#license)

## Features

- Deploy Docker images to Kubernetes with specified deployment name and image name.
- Monitor the Kubernetes cluster using Prometheus.
- FastAPI application running in a Kubernetes pod.

## Prerequisites

Before you begin, ensure you have the following prerequisites:

- A Kubernetes cluster set up and running.
- kubectl configured to interact with your Kubernetes cluster.
- Docker installed on your local machine.
- [Helm](https://helm.sh/) installed for managing Kubernetes applications.
- [Prometheus](https://prometheus.io/) set up in your Kubernetes cluster.
- [Python 3.7+](https://www.python.org/downloads/) and [pip](https://pip.pypa.io/en/stable/) installed.

## Installation

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/moooazsayyed/fastapi-k8s-deployer.git
   cd fastapi-k8s-deployer
2 . Install python dependecies
   pip install -r requirements.txt
3  **Running the Application**
Deploy FastAPI Application to Kubernetes:
```
  kubectl apply -f kubernetes/deployment.yaml
```

Ensure you have a kubernetes/deployment.yaml file that defines the deployment for your FastAPI application.

Port Forwarding (Optional):
If you want to access the FastAPI application locally, you can set up port forwarding:
```
kubectl port-forward svc/fastapi-k8s-deployer 8000:80
```

Open your web browser and navigate to http://localhost:8000 if you have set up port forwarding, or use the external IP of your Kubernetes service.

**Usage**
Deploy a New Image
Send a POST request to the /deploy endpoint with the deployment name and image name.

**Monitor Kubernetes**
The application uses the Prometheus client to expose metrics. You can view these metrics by accessing the /metrics endpoint.

**Monitoring**
Ensure Prometheus is scraping the metrics endpoint of your FastAPI application. You can configure this in your Prometheus configuration.

**Contributing**
We welcome contributions! Please follow these steps to contribute to the project:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature-name).
Make your changes and commit them (git commit -m 'Add some feature').
Push to the branch (git push origin feature/your-feature-name).
Create a Pull Request.
**License**
This project is licensed under the MIT License. See the LICENSE file for details.

Author: Mooaz Sayyed
GitHub: moooazsayyed

This README file provides clear instructions on setting up, configuring, running, and using the FastAPI application for deploying images on Kubernetes and monitoring with Prometheus. It also includes sections for contributing and licensing.








