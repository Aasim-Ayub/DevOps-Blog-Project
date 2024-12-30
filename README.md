# DevOps Blog Project By Asim Ayub & Muhammad Sameed Asif

```markdown
# DevOps Blog Project

## Overview

This project is a full-stack blog application developed as part of the Web Technologies course. It allows users to create, edit, and delete blog posts, with a responsive UI for an enhanced user experience.

## Features

- **User Authentication**: Secure registration and login functionality.
- **Blog Management**: Create, edit, and delete blog posts.
- **Post Listings**: View a list of all blog posts.
- **Responsive Design**: Optimized for various devices.

## Technologies Used

- **Frontend**: React
- **Backend**: Node.js
- **Database**: MongoDB
- **Containerization**: Docker
- **Orchestration**: Kubernetes
- **CI/CD**: Jenkins

## Prerequisites

Ensure you have the following installed:

- [Docker](https://www.docker.com/get-started)
- [Kubernetes](https://kubernetes.io/docs/setup/)
- [Jenkins](https://www.jenkins.io/download/)

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Aasim-Ayub/DevOps-Blog-Project.git
   cd DevOps-Blog-Project
   ```

2. **Set Up Environment Variables**:
   - Create a `.env` file in the `api` directory with the following variables:
     ```env
     MONGO_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     ```

3. **Build and Run with Docker Compose**:
   ```bash
   docker-compose up --build
   ```

   This command will build and start the frontend, backend, and database services.

## Deployment

For production deployment, Kubernetes manifests are provided in the `k8s` directory.

1. **Apply Kubernetes Manifests**:
   ```bash
   kubectl apply -f k8s/
   ```

2. **Set Up Jenkins Pipeline**:
   - Use the provided `Jenkinsfile` to set up a CI/CD pipeline in Jenkins.
   - Ensure Jenkins has the necessary permissions and plugins to interact with your Kubernetes cluster.

## Usage

- Access the application at `http://localhost:3000`.
- Register a new account or log in with existing credentials.
- Create, edit, or delete blog posts through the user interface.

## Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the Repository**: Click on the 'Fork' button at the top right of this page.
2. **Create a New Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Commit Your Changes**:
   ```bash
   git commit -m 'Add some feature'
   ```
4. **Push to the Branch**:
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Open a Pull Request**: Navigate to the original repository and click on 'New Pull Request'.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

- **Authors**: Aasim Ayub & Muhammad Sameed Asif
- **Email**: [221020@students.au.edu.pk](mailto:221020@students.au.edu.pk)
- **Email**: [221092@students.au.edu.pk](mailto:221092@students.au.edu.pk)
```
