DevOps Blog Project: CI/CD and Kubernetes Deployment
📖 Overview
This project is a Blog Application designed to demonstrate containerized microservices architecture using Docker, automated CI/CD pipeline with Jenkins, and deployment to Kubernetes. The application consists of two main components: a frontend and a backend, deployed as separate services and managed via Kubernetes.

📂 Repository Structure
The project is organized as follows:

📦 Blog Project
-- 📁 backend          # Backend microservice code
-- 📁 frontend         # Frontend microservice code
-- 📁 k8s              # Kubernetes manifests (Deployment, Service, Ingress, etc.)
📄 docker-compose.yml  # Multi-container setup for local development

Key Files and Folders:
backend/: Contains the source code for the backend service, built with Node.js and Express.js.
frontend/: Contains the source code for the frontend service, built with React.js.
k8s/: Holds Kubernetes YAML files to manage deployments, services, and ingress.
docker-compose.yml: Used for local development to spin up multiple containers.
Jenkinsfile: Defines the CI/CD pipeline, including build, test, and deployment steps.

🚀 How to Clone and Use This Project
Prerequisites:
Install Git.
Install Docker and Docker Compose.
(Optional) Install Kubernetes (minikube or a cluster).
Install kubectl (Kubernetes CLI).

Clone the Repository:
Open a terminal and run:

git clone https://github.com/Aasim-Ayub/DevOps-Blog-Project.git 
cd DevOps-Blog-Project
Navigate to the respective folders for backend, frontend, or Kubernetes manifests as needed.

🔧 CI/CD Pipeline
This project uses Jenkins for the CI/CD pipeline to automate building, testing, and deploying the application.

Pipeline Steps:
Clone Repository: Pulls the latest code.
Build Docker Images: Builds container images for backend and frontend services.
Push Images to Docker Hub: Uploads the Docker images to your Docker Hub repository.
Deploy to Kubernetes: Deploys the application to a Kubernetes cluster.
Setting Up the Pipeline:
Add the repository to Jenkins using the Jenkinsfile located at the root of the project.
Configure Webhooks in GitHub to trigger Jenkins builds automatically on push events.
Add Docker Hub and Kubernetes credentials in Jenkins.

🐳 Docker Commands for Manual Execution
If you prefer running the application manually without the CI/CD pipeline, follow these steps:

Build Docker Images:

docker build -t your-dockerhub-username/backend:latest ./backend
docker build -t your-dockerhub-username/frontend:latest ./frontend

Run Docker Compose Locally:

docker-compose up

Push Images to Docker Hub:

docker push your-dockerhub-username/backend:latest
docker push your-dockerhub-username/frontend:latest

Run Containers Individually (without Compose):

docker run -d --name backend -p 5000:5000 your-dockerhub-username/backend:latest
docker run -d --name frontend -p 3000:3000 your-dockerhub-username/frontend:latest

☸ Kubernetes Deployment Process
To deploy the application to Kubernetes, follow these steps:

Ensure kubectl is Configured:

Verify your Kubernetes context is set up correctly:

kubectl config current-context

Apply Kubernetes Manifests:

kubectl apply -f k8s/

Check Deployment Status:

kubectl get pods -n blog-namespace

Access the Application:

Use the Ingress IP or node port to access the frontend.

Stop Deployment (if needed):

kubectl delete -f k8s/

🛠 Development Setup
Run Locally with Docker Compose:

docker-compose up
Access the Application:

Frontend: http://localhost:3000
Backend: http://localhost:5000
Modify and test the code as needed.

🌟 Features
Microservices Architecture: Backend and frontend are containerized and independently managed.
CI/CD Pipeline: Automated build and deployment process with Jenkins.
Kubernetes Deployment: Scalable and fault-tolerant deployment.
Docker Hub Integration: Images are stored and pulled from Docker Hub for portability.
🐛 Troubleshooting
Common Issues:
Kubernetes Deployment Fails:

Ensure Docker images are pushed to the repository.
Verify the Kubernetes manifests in the k8s/ folder.
CI/CD Pipeline Errors:

Check Jenkins logs for errors, especially authentication or connection issues.
Local Development Issues:

Confirm Docker Compose is installed and working properly.