# Flask CI/CD Pipeline with Jenkins, Docker & Kubernetes

This project demonstrates an end-to-end DevOps pipeline for a Flask application using Jenkins, Docker, and Kubernetes (Minikube).

## Tech Stack
- Python (Flask)
- Docker
- Jenkins (Pipeline)
- Kubernetes (Minikube)
- GitHub

## Project Flow

1. Developer pushes code to GitHub  
2. Jenkins Pipeline triggers automatically  
3. Jenkins builds Docker image  
4. Image is pushed to Docker Hub  
5. Kubernetes deploys application using Deployment + Service  
6. Flask app is exposed via NodePort

## Repository Structure
