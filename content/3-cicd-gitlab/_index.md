+++
title = "CI/CD Deployment with Gitlab"
date = 2024
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

#### Overview

In this section, we will learn how to implement automated application deployment using Gitlab CI/CD pipeline in conjunction with AWS services such as ECR, ECS, and CodeDeploy.

![Pipeline Process](/images/4-cicd-gitlab/4.0.1.png)

#### Pipeline Process

1. **Pipeline Initiation**
   - Developer creates tag and pushes code to Gitlab repository
   - Gitlab CI/CD is automatically triggered when developer creates new tag

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

1. [Fork and Modify Code](1-forkandmodifycode)

2. [Setup Gitlab and Runner](2-setupgitlabandrunner)

3. [Modify and Add Role](3-modifyandaddrole)

4. [Create Tag and View Pipeline](4-createtagandviewpipeline)

5. [Check Results](5-checkresult)

After completing this module, you will be able to:
- Set up and manage CI/CD pipeline with Gitlab
- Automate application deployment process
- Handle issues that arise during deployment
- Apply DevOps best practices