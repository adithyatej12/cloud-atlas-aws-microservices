# CI/CD Pipeline

## Overview

The project implements automated continuous delivery using AWS CodePipeline and AWS CodeDeploy.

Two independent pipelines are used.

## Customer Pipeline

```text
CodeCommit
     |
     v
Amazon ECR
     |
     v
AWS CodePipeline
     |
     v
AWS CodeDeploy
     |
     v
ECS Fargate
