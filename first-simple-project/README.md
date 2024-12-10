# First Simple Dockerized Node.js Project

This project demonstrates a simple Dockerized Node.js application that logs a message to the console.

## Project Structure

first-simple-project/
	├── Dockerfile
	├── app.js 
	└── README.md

### File Descriptions
- **Dockerfile**: Contains instructions to build a Docker image for the Node.js application.
- **app.js**: A simple Node.js script that prints `Hello to Docker with JS` to the console.
- **README.md**: This documentation file.

---

## Prerequisites

Ensure you have the following installed on your system:
- [Docker](https://www.docker.com/)

---

## How to Build and Run

### Step 1: Build the Docker Image
Navigate to the project directory and run the following command to build the Docker image:
```bash
docker build -t node-docker-app .
```

### Step 2: Run the Docker Container
Run the built image to see the output:
```bash
docker run -it node-docker-app
```

You should see:
```bash
Hello to Docker with JS
```

## How it Works

1. The Dockerfile specifies a lightweight Node.js image (node:16-alpine) as the base image.
2. The WORKDIR /app sets the working directory inside the container.
3. The app.js file is copied into the container.
4. The command node app.js runs the script when the container starts.

## Clean Up
To remove the Docker container and image after testing:
1. Stop any running container:
```bash
docker ps -a
docker stop <container-id>
```

2. Remove the container:
```bash
docker rm <container-id>
```

3. Remove the image:
```bash
docker rmi node-docker-app
```






