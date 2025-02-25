# DevOps:
DevOps is a practice for streamlining the processes of software development along
with the required IT operations to achieve continuous integration and continuous deployment. This
workshop focuses on DevOps involved in developing and deploying the API on Node platform. At
the end of the workshop, the students get an understanding of the real environment in which the
applications are built.

# Currency Converter (INR to USD)

## Introduction
This is a simple Node.js command-line application that converts Indian Rupees (INR) to US Dollars (USD). The project follows a continuous integration and development approach using GitHub Workflows, Docker, and Kubernetes. This guide provides a step-by-step implementation for beginners to set up, develop, and deploy this project.

## Prerequisites
Before starting, ensure you have the following:

### 1. Lab Environment
- **Ubuntu 24+** machine with at least **8GB RAM** and **16GB disk space**
- Latest **Node.js**
- Latest **Visual Studio Code**
- **Git** client
- **Curl**
- **Stable Internet Connectivity**

### 2. Required Accounts
- **GitHub** (for version control)
- **DockerHub** (for containerization and deployment)

## Steps to Implement

### 1. Create and Set Up the Repository
1. Create a new repository on GitHub named `jasmin-converter`.
2. Clone the repository to your local machine:
   ```sh
   git clone <repo-url>
   ```
3. Navigate to the project directory:
   ```sh
   cd jasmin-converter
   ```

### 2. Initialize the Project
1. Initialize a Node.js project with default settings:
   ```sh
   npm init -y
   ```

### 3. Develop the Application
1. Create a file `convert.js` to implement the currency conversion logic.
2. Create an `index.js` file for a simple CLI interaction to convert INR to USD.

### 4. Run and Verify the Application
1. Execute the program:
   ```sh
   node index.js
   ```

### 5. Install Testing Framework (Jest)
1. Install Jest for testing:
   ```sh
   npm install --save-dev jest
   ```
2. Create a test file `convert.test.js` to validate the conversion logic.

### 6. Run the Tests
1. Execute the test cases:
   ```sh
   npm test
   ```

### 7. Set Up GitHub Workflows for CI/CD
1. Create a `.github/workflows/ci.yml` file to automate testing on each push.
2. Push the changes to the repository and observe the workflow running on GitHub Actions.

### 8. Containerize the Application with Docker
1. Create a `Dockerfile` to containerize the application.
2. Install Docker and build the Docker image:
   ```sh
   docker build -t jasmin-converter .
   ```
3. Run the Docker container:
   ```sh
   docker run -it jasmin-converter
   ```

### 9. Develop a Simple API
1. Create a new branch `api`:
   ```sh
   git branch api
   git checkout api
   ```
2. Install Express.js:
   ```sh
   npm install express
   ```
3. Update `index.js` to expose a REST API endpoint for conversion.
4. Push the updates to GitHub and merge them into the `main` branch.

### 10. Update Dockerfile for API
1. Modify `Dockerfile` to expose port 3000.
2. Rebuild and run the container:
   ```sh
   docker build -t jasminshah123/jasmin-converter .
   docker run -d -p 3000:3000 jasminshah123/jasmin-converter
   ```
3. Test the API:
   ```sh
   curl "http://localhost:3000/convert?inr=100"
   ```

### 11. Automate Docker Deployment in GitHub Actions
1. Update `.github/workflows/ci.yml` to build and push the Docker image to Docker Hub.
2. Set up secrets for `DOCKER_USERNAME` and `DOCKER_PASSWORD` in GitHub.
3. Push all changes to GitHub and verify the deployment in Docker Hub.

### 12. Deploy with Kubernetes
1. Install **Kubernetes**, **Minikube**, and configure it.
2. Create a deployment file `jasmin.yml` to deploy the container.
3. Deploy the application to Kubernetes:
   ```sh
   kubectl apply -f jasmin.yml
   ```
4. Verify that the deployment is running:
   ```sh
   kubectl get deployments
   kubectl get pods
   ```



