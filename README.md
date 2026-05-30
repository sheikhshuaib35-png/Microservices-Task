# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```

---

# Microservices Dockerization Assignment

## Overview

This project demonstrates the containerization and orchestration of Node.js microservices using Docker and Docker Compose.

Services:

* User Service (Port 3000)
* Product Service (Port 3001)
* Gateway Service (Port 3003)

---

PREREQUISITES

Before running the application, ensure the following are installed:

* Docker
* Docker Compose

Verify installation:

docker --version
docker compose version

---

PROJECT STRUCTURE

submission/
├── user-service/
│   └── Dockerfile
├── product-service/
│   └── Dockerfile
├── gateway-service/
│   └── Dockerfile
├── docker-compose.yml
└── README.md

---

SETUP INSTRUCTIONS

1. Navigate to the project directory:

cd submission

2. Build and start all services:

docker compose up --build

To run in detached mode:

docker compose up -d --build

---

VERIFY RUNNING CONTAINERS

Check running containers:

docker ps

Expected containers:

* user-service
* product-service
* gateway-service

---

TESTING THE SERVICES

User Service:
http://localhost:3000

Or:

curl http://localhost:3000

Product Service:
http://localhost:3001

Or:

curl http://localhost:3001

Gateway Service:
http://localhost:3003

Or:

curl http://localhost:3003

---

STOPPING THE APPLICATION

docker compose down

---

TROUBLESHOOTING

1. Port Already in Use

Linux/macOS:

lsof -i :3000

Windows:

netstat -ano | findstr :3000

Terminate the conflicting process or modify the port mapping in docker-compose.yml.

2. Container Exits Immediately

Check logs:

docker logs user-service
docker logs product-service
docker logs gateway-service

Review the error messages and verify application dependencies.

3. Rebuild Containers

docker compose down
docker compose up --build

---

DOCKER NETWORK

All services communicate through a shared Docker bridge network configured in docker-compose.yml.

Service names used for communication:

* user-service
* product-service
* gateway-service

---

SCREENSHOTS INCLUDED

The following screenshots are attached with the submission:

1. Successful execution of docker compose up --build
2. Output of docker ps showing all running containers
3. User Service accessible at http://localhost:3000
4. Product Service accessible at http://localhost:3001
5. Gateway Service accessible at http://localhost:3003

---

Shekh Mohammad Shuaib

Submitted as part of the Docker and Docker Compose Microservices Containerization Assignment.
