# Docker Lab: Containerizing a Three-Tier Application
**INET 4031 - Introductions to Systems**

This lab introduces Docker and Docker Compose by having you containerize a
real, multi-service application. You will package three components: Apache,
Flask and MariaDB. These will be packaged into separate containers and wired together so they function as a complete application.

---



---

# Project Overview

This project shows how to containerize a 3-tier web application using Docker + Docker Compose. The 3 services are:

-Apache(web)
     - Serves the frontend and routes API requests
     
-Flask(app)
     - Backend logic and API endpoints
     
-MariaDB(db)
     - Stores application data

# Prerequisites

Before anything gets started, please make sure to have the following:

- Docker installed
- Docker Compose installed
- Linux VM


# Getting Started
- Clone the GitHub repository

- Create a .env file and fill all values with database credentials

- create a .gitignore


# Configuration
This application uses the environment variables stored in the .env file that include the database name, user, and password. These values are used by both the Flask application and the MariaDB service to establish connections between them. All services are defined in the docker-compose.yml file, where the db service runs MariaDB, the app service runs the Flask backend, and the web service runs Apache as the frontend.


# Verification
- Ran docker compose ps to confirm:
     - db = healthy
     - app = healthy
     - web = running
     
- Opened the frontend dashboard in a browser using the VM’s IP:
     - Verified the page loads
- Test the health endpoint
- Create a new ticket
- Test persistence
- Run the check script
       - Make sure to "sudo" or tests might fail


## Lab 13 - Kubernetes Deployment
This application was originally deployed using Docker Compose in Lab 12. In Lab 13, it was migrated to Kubernetes using k3s. The MariaDB database, Flask backend, and Apache frontend now run as Kubernetes Deployments and Services, with Secrets used for sensitive environment variables and persistent storage used for the database.

### Deploy Commands

```bash
kubectl apply -f k8s/ -n ticket-app

###Access URL

http://192.168.56.2:30080
