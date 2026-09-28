# Cloud Atlas: Monolith to Microservices and CI/CD on AWS

## Project Overview

Cloud Atlas is a cloud modernization project that demonstrates the transformation of a monolithic Node.js application into independently deployable microservices on Amazon Web Services (AWS).

The project uses containerization, serverless container compute, managed container image storage, load balancing, relational database services, and automated CI/CD pipelines.

## Objectives

- Analyze a monolithic Node.js application
- Decompose the application into microservices
- Containerize the services using Docker
- Store container images in Amazon ECR
- Deploy containers using Amazon ECS and AWS Fargate
- Use Amazon RDS MySQL as the database
- Route application traffic using an Application Load Balancer
- Implement automated CI/CD using AWS CodePipeline
- Implement blue/green deployments using AWS CodeDeploy
- Apply IP-based access control to administrative routes
- Demonstrate independent scaling of microservices

## Architecture

The final architecture consists of two Node.js microservices:

- Customer Microservice
- Employee Microservice

Both services run as containers on AWS Fargate inside an Amazon ECS cluster.

The Application Load Balancer acts as the main entry point and performs path-based routing.

The services use Amazon RDS MySQL for persistent data storage.

## AWS Services Used

| AWS Service | Purpose |
|---|---|
| Amazon EC2 | Original monolithic application |
| Amazon ECR | Container image storage |
| Amazon ECS | Container orchestration |
| AWS Fargate | Serverless container compute |
| Amazon RDS | MySQL database |
| Application Load Balancer | Traffic routing |
| AWS CodeCommit | Source code repository |
| AWS CodePipeline | CI/CD automation |
| AWS CodeDeploy | Blue/green deployment |
| Amazon CloudWatch | Monitoring and logs |
| AWS Cloud9 | Cloud development environment |

## Microservices

### Customer Microservice

Provides read-only access to the supplier catalog and is designed for public browsing traffic.

### Employee Microservice

Provides CRUD operations for supplier management through administrative routes under:

```text
/admin/*
