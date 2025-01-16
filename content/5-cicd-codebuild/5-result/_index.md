+++
title = "Verify Results"
date = 2024
weight = 5
chapter = false
pre = "<b>5.5. </b>"
+++

#### Verify Deployment Results

Check GitHub Build Results:

- Access GitHub repository to view build overview

![github-overview](/images/6-cicd-codebuild/6.5.1.png)

Verify Frontend Build:

- Access Frontend Build project
- Review build details in **Build logs** section

![frontend-logs](/images/6-cicd-codebuild/6.5.2.png)

Verify Backend Build:

- Similarly, check Backend logs in **Build logs** section

![backend-logs](/images/6-cicd-codebuild/6.5.3.png)

Confirm ECS Configuration:

- Access ECS Task definition
- Review both Frontend and Backend configurations

![task-definition-1](/images/6-cicd-codebuild/6.5.4.png)
![task-definition-2](/images/6-cicd-codebuild/6.5.5.png)

Check Deployment Details:

- Review **Configuration and networking** section

![config-network](/images/6-cicd-codebuild/6.5.6.png)

- Verify **Deployment** information

![deployment](/images/6-cicd-codebuild/6.5.7.png)

Test Application:

- Access the application to confirm functionality

![application](/images/6-cicd-codebuild/6.5.8.png)
