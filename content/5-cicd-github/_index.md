+++
title = "CI/CD Deployment with Github Actions"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Overview
In this section, we will learn how to implement automated application deployment using Github Actions in conjunction with AWS services such as ECR, ECS, and CodeDeploy.

![Pipeline Process](/images/4-cicd-gitlab/4.0.2.png)

#### Pipeline Process

1. **Pipeline Initiation**
   - Developer creates tag and pushes code to Github repository
   - Github Actions is automatically triggered when developer creates new tag

2. **Build**
   - Code is built into Docker image

3. **Push Image**
   - Image is pushed to Amazon ECR (Elastic Container Registry) or DockerHub

4. **Update**
   - Update ECS Task Definition for both Frontend and Backend

5. **Deployment**
   - Frontend service:
     - Update new revision of frontend service
   - Backend service:
     - Update new code deploy of backend service

#### Content

1. []()

2. []()

3. []()

4. []()

5. []()

After completing this module, you will be able to:
- Set up and manage CI/CD pipeline with Github Actions
- Automate application deployment process
- Handle issues that arise during deployment
- Apply DevOps best practices