         ___        ______     ____ _                 _  ___  
        / \ \      / / ___|   / ___| | ___  _   _  __| |/ _ \ 
       / _ \ \ /\ / /\___ \  | |   | |/ _ \| | | |/ _` | (_) |
      / ___ \ V  V /  ___) | | |___| | (_) | |_| | (_| |\__, |
     /_/   \_\_/\_/  |____/   \____|_|\___/ \__,_|\__,_|  /_/ 
 ----------------------------------------------------------------- 

# Breaking a Monolithic Node.js Application into Microservices

## Overview

This project demonstrates how to refactor a traditional monolithic Node.js message board application into a microservices architecture using Docker and Amazon ECS. The application allows users to create topic threads and post messages, originally implemented as a single service.

## Objectives

- Containerize a monolithic Node.js application
- Break it into microservices based on business logic (Posts, Threads, Comments)
- Set up Docker-based local development with docker-compose
- Deploy services to AWS ECS using task definitions and load balancers

## Architecture Evolution

### Monolithic Version
- A single Node.js server
- All application logic in one codebase
- One failure = full app crash

### Microservices Version
- *Post Service*: Handles user posts
- *Thread Service*: Manages discussion threads
- *Comment Service*: Handles comments on posts
- *API Gateway*: Acts as an entry point, routing to microservices

Each service runs independently in containers, enabling individual scaling and deployment.

## Technologies Used

- *Node.js* – Application backend
- *Express.js* – REST APIs
- *Docker* – Containerization
- *Amazon ECS* – Container orchestration and deployment
- *AWS CloudFormation* – Infrastructure as Code
- *NGINX* or Express Gateway – API Gateway (optional)
- *MongoDB / DynamoDB* – Optional backend (based on services)

## How to Run Locally

```bash
# Clone repo
git clone https://github.com/<your-username>/monolith-to-microservices-nodejs.git
cd monolith-to-microservices-nodejs

# Run monolith (optional)
cd monolith-app && npm install && node server.js

# OR run microservices with Docker
docker-compose up --build