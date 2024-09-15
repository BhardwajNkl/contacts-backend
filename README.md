# Contacts Backend API
## Project Overview
This is a Spring Boot backend API for a Contacts application. The API provides endpoints for:
- creating new contacts
- fetching existing contacts
- updating contacts
- deleting contacts

The application uses an in-memory database (H2) for storage and is containerized using Docker for easy deployment.

## Prerequisites
Before you start, ensure you have the following installed:

- Docker

## Running the Application
Follow these steps to build and run the application in a Docker container.

### Step 1: Clone the repository
```bash
git clone https://github.com/BhardwajNkl/contacts-backend.git
cd contacts-backend
```

### Step 2: Build the Docker image
Use the following command to build the Docker image for the application. Make sure you're in the root directory of the project, where the Dockerfile is located.
```bash
docker build -t contacts-backend-h2 .
```

### Step 3: Run the Docker container
Once the image is built, run the following command to start a container:
```bash
docker run -d -p9090:9090 --name contacts-backend-h2 contacts-backend-h2
```
**Make sure that host port 9090 is available on your machine. Otherwise, use some other host port[the first part].**

### Step 4: Access the API
Access this url in the browser to get the API documentation: http://localhost:9090/swagger-ui/index.html
You can try the APIs from this page directly or you may use tools like postman to make requests.

### Step 5: Stopping the Container
To stop the running container, first, list all running containers:
```bash
docker ps
```
Find the CONTAINER ID of the contacts-backend-h2 container and then stop it using:
```bash
docker stop <CONTAINER_ID>
```

### Step 6: Clean Up
Remove the container:
```bash
docker rm <CONTAINER_ID>
```

Remove the image:
```bash
docker rmi contacts-backend-h2
```
