# Deployment

## Deployment Architecture

The deployment uses:

- Amazon ECR
- Amazon ECS
- AWS Fargate
- Application Load Balancer
- AWS CodePipeline
- AWS CodeDeploy

## Deployment Process

1. Source code is updated.
2. Container image is updated.
3. Image is stored in Amazon ECR.
4. CodePipeline detects the update.
5. A new ECS task revision is prepared.
6. CodeDeploy starts the blue/green deployment.
7. The new revision is deployed to the green environment.
8. Health checks validate the new service.
9. Traffic is shifted to the new revision.
10. The previous revision remains available temporarily for rollback.

## Customer Deployment

Pipeline:

```text
update-customer-microservice
