+++
title = "Introduction"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

#### Architecture

![1](/images/.png)

#### Github Action CI/CD

**GitHub Actions** is an integrated automation service on GitHub that allows you to automate software development workflows from code testing to application deployment, making it easy to set up CI/CD (Continuous Integration/Continuous Deployment).

1. Continuous Integration (CI)
- Automated Build and Test: Automatically build and test code whenever changes occur, helping to catch bugs early.
- Workflows: Define workflows to automatically perform checks, build, and release code when events such as pull requests or new commits occur.
2. Continuous Deployment (CD)
- Automated Deployment: Supports automatic deployment of applications to environments like staging or production once the code is approved.
- Service Integration: Easily integrates with services like AWS, Azure, and Google Cloud.
3. Key Features
- Customization: Create custom actions or use actions from the GitHub Marketplace.
- User-Friendly Interface: Easily set up and manage workflows without deep scripting knowledge.
- Resource Management: Track workflow status and gain insights into testing and deployment processes.
4. Benefits
- Time Savings: Minimizes repetitive work for developers.
- Improved Code Quality: Enhances software quality through frequent testing and deployment.
- Flexibility: Easily adjust CI/CD processes to suit project needs.

#### Gitlab CI/CD

**GitLab CI/CD** is a crucial component of GitLab that allows the automation of software development processes through Continuous Integration (CI) and Continuous Deployment (CD).

1. Continuous Integration (CI)
- Automated Build and Test: Automates code building and testing when changes occur, helping to catch bugs early.
- Configuration in .gitlab-ci.yml: The CI/CD configuration is defined in this file, making it easy to set up pipelines.
2. Continuous Deployment (CD)
- Automated Deployment: Supports automatic deployment of applications to staging and production environments after successful tests.
- Version Management: Tracks and easily rolls back when necessary.
3. Key Features
- GitLab Runners: The components that execute jobs in the pipeline, which can be either GitLab's runners or custom ones.
- Multi-Platform Support: Integrates with various services like AWS, Google Cloud, and Azure.
- Visual Interface: Easily track pipeline progress and logs through the user interface.
4. Benefits
- Time Savings: Reduces effort spent on repetitive tasks.
- Improved Code Quality: Continuous testing helps to quickly identify bugs.
- Flexibility and Customization: Customizable processes to meet project requirements.
5. Integration with DevOps
- Supports DevOps processes, creating a rapid development lifecycle and improving collaboration between teams.

#### AWS CodePipeline CI/CD

**AWS CodePipeline** is a fully managed CI/CD service on AWS that automates the software build, test, and deployment processes. It optimizes the software development lifecycle from code to production.

1. Continuous Integration (CI) with **AWS CodeBuild**: 
- AWS CodeBuild automatically compiles source code, runs tests, and creates artifacts for deployment without needing to manage infrastructure.
- Key Features:
  - Source Code Integration: Supports pulling code from AWS CodeCommit, GitHub, Bitbucket, etc.
  - Multi-Language Support: Customizable build environments for various programming languages.
  - Auto-Scaling: Scales the build process as needed to save costs.
2. Continuous Deployment (CD) with **AWS CodeDeploy**
- AWS CodeDeploy automates the deployment of applications to environments like Amazon EC2 and AWS Lambda.
- Key Features:
  - Smooth Deployment: Supports blue/green and rolling deployment methods to minimize downtime.
  - Deployment Monitoring: Tracks the deployment process and allows rollback in case of errors.
  - Integration with AWS: Easily integrates with Amazon ECS, AWS Lambda, and Amazon EC2.
3. Integration in **AWS CodePipeline**
- Building Pipelines: Combines CodeBuild and CodeDeploy to define a complete CI/CD process from code retrieval, building, testing to deployment.
- Automated Workflow Management: Effectively automates and manages the CI/CD process, ensuring every code change is tested and deployed promptly, reducing risks and enhancing performance.

#### Monitoring

1. Monitoring with CloudWatch Container Insights

CloudWatch Container Insights is a feature within AWS CloudWatch that provides monitoring and analysis capabilities for running containers on Amazon ECS (Elastic Container Service) and EKS (Elastic Kubernetes Service). Here are some highlights of Container Insights:

- Performance Monitoring: Container Insights allows you to track critical performance metrics such as CPU, memory, and network usage for each container, helping to identify issues early and optimize application performance.
- Container Status Statistics: You can view detailed information about the operational status of containers, including their state (running, stopped, failed) and other parameters like uptime and replica count.
- Integration with AWS: Container Insights can easily integrate with other AWS services, allowing you to build comprehensive monitoring solutions and create custom reports based on container metrics.
- Visual Dashboard: AWS provides visual dashboards that enable you to monitor the status and performance of containers easily, along with the ability to set alerts for incidents.

2. Logs Router with FireLens

FireLens is a feature in AWS that helps you manage and route logs from containers to various log storage services. Here are some highlights of FireLens:

- Flexible Log Routing: FireLens allows you to easily route logs from containers to various targets, including Amazon CloudWatch Logs, Amazon S3, Elasticsearch, and many other services. This helps you manage and analyze logs effectively.
- Customization Features: You can customize how logs are routed, formatted, and processed, enabling you to create log management solutions tailored to the specific needs of your application.
- Multi-Platform Support: FireLens supports both Amazon ECS and EKS, allowing for easy integration into containerized applications across different platforms.
- Performance Optimization: By using FireLens, you can offload log writing and routing tasks from containers, which helps improve application performance.