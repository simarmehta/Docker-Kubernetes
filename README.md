# Docker and Kubernetes

This repository provides examples, resources, and tutorials for using **Docker** and **Kubernetes**. The project includes Dockerized applications, Kubernetes deployments, and configurations to help users understand containerization and orchestration.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository serves as a practical guide to using **Docker** for containerization and **Kubernetes** for container orchestration. It includes basic Docker and Kubernetes configurations, along with examples of building, deploying, and managing applications within a containerized environment.

- **Docker**: Learn how to create, manage, and run containers.
- **Kubernetes**: Get familiar with deploying, scaling, and managing containerized applications using Kubernetes.

The repository is designed to help developers gain hands-on experience with both Docker and Kubernetes.

## Features

- **Dockerized Applications**: Examples of how to create Docker images and run containers.
- **Kubernetes Deployments**: YAML files and configurations for Kubernetes resources such as Pods, Deployments, and Services.
- **Scaling and Load Balancing**: Examples of how to scale applications in Kubernetes.
- **Hands-on Tutorials**: Step-by-step guides for using Docker and Kubernetes.

## Installation

### Prerequisites

- Docker installed (for local Docker examples): [Install Docker](https://docs.docker.com/get-docker/)
- Kubernetes installed (e.g., Minikube or kubectl for local Kubernetes): [Install Kubernetes](https://kubernetes.io/docs/tasks/tools/)
- Python 3.x (for any Python-based Docker examples)

### Steps

1. Clone the repository:

    ```bash
    git clone https://github.com/simarmehta/Docker-Kubernetes.git
    cd Docker-Kubernetes
    ```

2. Install Docker and Kubernetes if not already installed by following the official guides mentioned in the prerequisites.

3. You can run Docker images or Kubernetes configurations as per the provided examples.

## Usage

### Docker Usage

1. Build a Docker image from the provided Dockerfile:

    ```bash
    docker build -t my-app .
    ```

2. Run the Docker container:

    ```bash
    docker run -d -p 5000:5000 my-app
    ```

3. View the running container:

    ```bash
    docker ps
    ```

4. Stop the container:

    ```bash
    docker stop <container_id>
    ```

### Kubernetes Usage

1. Start your local Kubernetes cluster (e.g., using Minikube):

    ```bash
    minikube start
    ```

2. Apply Kubernetes configurations:

    ```bash
    kubectl apply -f kubernetes/deployment.yaml
    kubectl apply -f kubernetes/service.yaml
    ```

3. Check the status of your Kubernetes Pods:

    ```bash
    kubectl get pods
    ```

4. To access the deployed service:

    ```bash
    minikube service my-app-service
    ```

5. Scale the application by updating the replicas in the deployment:

    ```bash
    kubectl scale deployment my-app-deployment --replicas=3
    ```

## How It Works

### Docker

Docker is used to package applications into containers. This repository includes Dockerfiles to build images and run applications in isolated environments. 

- **Dockerfile**: Contains the instructions to build a Docker image, including the base image, installation of dependencies, and application code.
- **Docker Compose**: For managing multi-container Docker applications.

### Kubernetes

Kubernetes is used to manage containerized applications in a clustered environment. This project includes Kubernetes configuration files (YAML) for deploying applications to a Kubernetes cluster.

- **Pods**: The smallest unit in Kubernetes that encapsulates containers.
- **Deployments**: Ensures the desired state of the application and manages scaling.
- **Services**: Exposes a running application to be accessible within or outside the Kubernetes cluster.

### Common Kubernetes Resources in the Repository:

- **deployment.yaml**: Defines how to deploy the application, including the number of replicas, container image, and resource limits.
- **service.yaml**: Exposes the application inside or outside the cluster using different types of services (ClusterIP, NodePort, LoadBalancer).

## Project Structure

```bash
Docker-Kubernetes/
├── docker/
│   ├── Dockerfile               # Dockerfile for building application image
│   ├── docker-compose.yml       # Docker Compose file for multi-container setup
├── kubernetes/
│   ├── deployment.yaml          # Kubernetes Deployment configuration
│   ├── service.yaml             # Kubernetes Service configuration
├── src/
│   ├── app.py                   # Example Python application
├── README.md                    # Project documentation
