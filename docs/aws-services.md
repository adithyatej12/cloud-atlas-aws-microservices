# AWS Services

| Service | Role in Project |
|---|---|
| Amazon EC2 | Hosted the original monolithic application |
| AWS Cloud9 | Development/build environment |
| AWS CodeCommit | Source code management |
| Amazon ECR | Container image repository |
| Amazon ECS | Container orchestration |
| AWS Fargate | Serverless container execution |
| Amazon RDS MySQL | Persistent relational database |
| Application Load Balancer | Application traffic routing |
| AWS CodePipeline | Continuous delivery automation |
| AWS CodeDeploy | Blue/green deployments |
| Amazon CloudWatch | Logs and monitoring |

## Container Platform

The microservices run on Amazon ECS using AWS Fargate.

## Image Management

Amazon ECR stores the customer and employee container images.

## Database

Amazon RDS MySQL stores persistent application data.

## Networking

The Application Load Balancer provides the external entry point and performs path-based routing.

## CI/CD

CodeCommit, ECR, CodePipeline and CodeDeploy form the continuous delivery chain.
