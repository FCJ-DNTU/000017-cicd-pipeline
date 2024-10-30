+++
title = "CI/CD Deployment with CodeBuild"
date = 2024
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

#### Overview
In this section, we will learn how to implement automated application deployment using CodeBuild in conjunction with AWS services such as ECR, ECS, and CodeDeploy.

![Pipeline Process](/images/4-cicd-gitlab/4.0.3.png)

#### Pipeline Process

1. **Pipeline Initiation**
   - Developer creates tag and pushes code to Github repository
   - CodeBuild is automatically triggered when developer creates new tag

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

1. [Github repository](1-github)

2. [Create CodeBuild Frontend](2-create-code-build-fe)

3. [Create CodeBuild Backend](3-create-code-build-be)

4. [Create tag](4-create-tag)

5. [Check result](5-result) 

After completing this module, you will be able to:
- Set up and manage CI/CD pipeline with CodeBuild triggered by Github Repository
- Automate application deployment process
- Handle issues that arise during deployment
- Apply DevOps best practices