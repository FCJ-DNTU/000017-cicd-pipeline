+++
title = "Preparation"
date = 2024
weight = 2
chapter = false
pre = "<b>2. </b>"
+++

#### Infrastructure Setup

Before participating in the CI/CD on ECS workshop, it’s recommended that you complete the following two workshops to build a strong foundation in AWS infrastructure and the process of deploying containers on ECS:

- [Deploy Application on Docker Container](https://fcj-dntu.github.io/000015-deploy-app-docker).
- [Deploy applications on Amazon Elastic Container Service](https://fcj-dntu.github.io/000016-deploy-app-ecs/).

Completing these workshops will help you set up the essential infrastructure components for configuring CI/CD on ECS, including:

- VPC network infrastructure
- Database instance on Amazon RDS
- Image pushed to Docker Hub or Amazon ECR
- Amazon Cloud Map for service discovery
- ECS cluster hosting your application’s containers
- Application Load Balancer for load distribution
- Application deployed as a container on ECS

With these infrastructure elements in place, we’ll proceed to the next step of setting up an automated CI/CD pipeline on ECS, completing your application deployment lifecycle.

