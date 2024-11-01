## MERN Social Media Project - Docker Setup
   This is a social media application built with the MERN (MongoDB, Express, React, Node.js) stack, designed to run seamlessly in a Docker environment. This guide will help you set up, configure, and run the application using Docker.Check MERN Git hub https://github.com/raj074/mern-social-media for further detailed layout.

  **Prerequisites**;
   - Docker installed on your machine
   - Docker Compose installed (if not included with Docker installation)

## Getting Started
Follow these steps to set up and run the application.

1. Clone the Repository
   ````bash
      git clone https://github.com/raj074/mern-social-media.git
      cd mern-social-media

2. Build and Run the Containers
   The docker-compose.yml file will handle the setup for the frontend, backend, MongoDB, Mongo Express, and NGINX.
   ````bash
      docker-compose up --build

3. Access the Application
  - Frontend (React App): http://localhost:3000
  - Backend (API Server): http://localhost:5000
  - Mongo Express: http://localhost:8081
  - WebGoat (for testing): http://localhost:8080

4. Environment Variables
   Ensure you have environment variables set up for both the frontend and backend. Common variables include:

  - For Backend
    Create a .env file in the backend directory with variables like:
      ````bash
         MONGO_URI=mongodb://mongo:27017/social-media
         JWT_SECRET=your_jwt_secret
         PORT=5000

 - For Frontend
    Create a .env file in the frontend directory with variables like:
    ````bash
       REACT_APP_API_URL=http://localhost:5000/api
       Note: MONGO_URI uses mongo as the hostname, which Docker resolves to the MongoDB container.

   
5. Docker Commands
   Here are additional Docker commands for common tasks:

  - Start Containers in Detached Mode:
   ````bash
      docker-compose up -d
   
-   Stop Containers:
   ````bash
      docker-compose down

-  View Container Logs:
   ````bash
      docker-compose logs -f
   
-  Rebuild Containers:
   ````bash
      docker-compose up --build


6. Troubleshooting
  - Port Conflicts: Ensure no other application is using ports 3000, 5000, 8080, or 8081.
  - Docker Not Starting: Try docker-compose down to remove all containers and then docker-compose up --build to restart.
  - MongoDB Connection Issues: Check that MONGO_URI is correctly set to mongodb://mongo:27017/social-media in your backend .env file.