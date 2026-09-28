# System Architecture

## Overview

Cloud Atlas transforms a monolithic Node.js application into two independently deployable microservices running on AWS Fargate.

## Architecture Components

### 1. Client

Users access the application through the Application Load Balancer.

### 2. Application Load Balancer

The Application Load Balancer provides a single entry point and performs path-based routing.

Default traffic is routed to the customer microservice.

Administrative requests using `/admin/*` are routed to the employee microservice subject to IP-based access control.

### 3. Amazon ECS

The microservices are deployed inside the:

`microservices-serverlesscluster`

ECS cluster.

### 4. AWS Fargate

Fargate provides serverless container compute for the customer and employee services.

Each task is configured with:

- 0.5 vCPU
- 1 GB memory
- awsvpc networking

### 5. Amazon ECR

Two private repositories store the container images:

- customer
- employee

### 6. Amazon RDS MySQL

Both microservices use the RDS MySQL database for persistent application data.

## Architecture Flow

```text
                    Internet Users
                          |
                          v
              Application Load Balancer
                     /           \
                    /             \
                   v               v
        Customer Microservice   Employee Microservice
             Fargate                 Fargate
                   \                 /
                    \               /
                     v             v
                    Amazon RDS MySQL
