1. Repository Structure
root/
│
├── crud-dd-task-mean-app/
│   ├── backend/
│   ├── frontend/
│   └── README.md
│
├── docker-compose.yaml
├── nginx.conf
├── nginx-dockerfile
│
└── .github/workflows/
    ├── backend.yml
    └── frontend.yml

2. Backend Configuration

Location: crud-dd-task-mean-app/backend/

Key Update:

Modified MongoDB URL to ensure backend connects to MongoDB inside Docker Compose.
url: "mongodb://mongodb:27017/dd_db"
Backend Dockerfile included and functional.
Backend image pushed to Docker Hub:
a7ryan/dd-backend

3. Frontend Configuration

Location: crud-dd-task-mean-app/frontend/
API route modification:
Updated API base URL so Angular frontend communicates through the reverse proxy.
const baseUrl = '/api/tutorials';
Frontend Dockerfile included and functional.
Frontend image pushed to Docker Hub:
a7ryan/dd-frontend

4. Nginx Reverse Proxy Configuration

Nginx configured to listen on port 80.
Configuration file: nginx.conf
Nginx image built and pushed:
a7ryan/dd-nginx


5. Docker Compose Setup

File: docker-compose.yaml

Components included:

Frontend container

Backend container

MongoDB container

Nginx reverse proxy

Services connected using Docker internal networking.


7. CI/CD Pipeline (GitHub Actions)

Workflow files located at:

.github/workflows/backend.yml

.github/workflows/frontend.yml

CI/CD Workflow Summary:

Builds Docker images for every push and manual trigger.

Tags images with commit SHA and latest.

Pushes images to Docker Hub.

Deployment step is ready but currently not operational due to VM SSH key error.

8. Cloud Deployment Status

A new Ubuntu VM was created for deployment.

The following were successfully configured:

Docker installation

Docker Compose installation

Firewall for port 80

Initial SSH setup

Deployment could not be completed due to:

Public SSH RSA key mismatch error.

Once SSH access is restored, deployment can be completed using:


9. Screenshots (images)

CI/CD pipeline run history

Docker image builds

Docker Hub repositories

Local application execution

Nginx reverse proxy setup

10. Deliverables Checklist

Dockerfiles for backend and frontend

Nginx configuration and Dockerfile

Docker Compose file

MongoDB setup through Docker Compose

CI/CD pipeline using GitHub Actions

Cloud VM deployment prepared but pending due to SSH authentication issue

The CI/CD pipeline and container structure are fully operational and ready for deployment once SSH access is resolved.
