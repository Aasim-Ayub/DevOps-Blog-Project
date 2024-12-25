pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'asimayub/DevOps-Blog-Project:latest' // Change to your Docker Hub username and project name
        DOCKER_CREDENTIALS_ID = 'asimayub' // Replace with your Jenkins credentials ID for Docker Hub
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Aasim-Ayub/DevOps-Blog-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t asimayub/DevOps-Blog-Project:latest ."
                }
            }
        }

        stage('Run Unit Tests') {
            steps {
                script {
                    // Example: Run tests inside the Docker container
                    sh "docker run --rm  npm test/"
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry([credentialsId: "asimayub", url: '']) {
                        sh "docker push asimayub/DevOps-Blog-Project:latest"
                    }
                }
            }
        }
    }

    post {
        failure {
            echo 'Build failed!'
        }
        success {
            echo 'Build succeeded!'
        }
    }
}
