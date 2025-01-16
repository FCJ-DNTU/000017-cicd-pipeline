+++
title = "Clone GitHub Template"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++

{{% notice tip %}}
In this section, we provide a **template** for running CI/CD with **GitHub Actions**. You can reference and clone it to streamline setup and usage, making CI/CD deployment faster and more efficient. Additionally, you can configure your own CI/CD setup to better manage your code.
{{% /notice %}}

#### Git clone code on GitHub

1. Use the previously set up EC2 instance to clone this code and make modifications within it. Once you have the code, you can adjust it as needed.

- Use the following command to clone the code:

```bash
git clone https://github.com/AWS-First-Cloud-Journey/aws-fcj-container-app.git
```

![Github](/images/5-cicd-github/5.1.1.png)

2. Modify the source code in the following location to make a sample change for CI/CD in GitHub Action:

- Path: frontend/src/components/Menu.jsx
- In line 68 of this file, you can edit it as follows:
 
![Github](/images/5-cicd-github/5.1.2.png)

{{% notice note %}}
You can edit elsewhere; this is just an example.
{{% /notice %}}

#### Code Explanation

1. First, the main.yml file contains all tasks for frontend and backend.

- Access the file with:

```bash
vi .github/workflows/main.yml
```

```
name: CI/CD Pipeline

on:
  push:
    tags:
      - '*'

jobs:
  frontend:
    uses: ./.github/workflows/frontend.yml
    secrets: inherit

  backend:
    uses: ./.github/workflows/backend.yml
    secrets: inherit
```

- In this file:
  - **name: CI/CD Pipeline** defines the workflow name.
  - **on: (...)** triggers the workflow.
  - **jobs: (...)** lists the jobs to run in CI/CD.

2. Next, the backend.yml and frontend.yml files set up specific jobs for each section. Since the configuration is similar, we'll demonstrate with backend.yml.

- Access the file with:

```bash
vi .github/workflows/backend.yml
```

```
name: Backend CI/CD

on:
  workflow_call:

env:
  IMAGE_NAME_BE: ${{ secrets.AWS_ACCOUNT_NUMBER }}.dkr.ecr.${{ secrets.AWS_REGION }}.amazonaws.com/${{ secrets.CI_PROJECT_BE_NAME }}:${{ github.ref_name }}

jobs:
  # check_changes_backend:
  #   runs-on: ubuntu-latest
  #   outputs:
  #     backend: ${{ steps.filter.outputs.backend }}
  #   steps:
  #     - uses: actions/checkout@v2
  #     - uses: dorny/paths-filter@v2
  #       id: filter
  #       with:
  #         filters: |
  #           backend:
  #             - 'backend/**'

  build-and-push:
    # needs: check_changes_backend
    runs-on: ubuntu-latest
    # if: ${{ needs.check_changes_backend.outputs.backend == 'true' }}
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Configure AWS credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ secrets.AWS_REGION }}

      - name: Login to Amazon ECR
        id: login-ecr
        uses: aws-actions/amazon-ecr-login@v1

      - name: Build, tag, and push image to Amazon ECR
        working-directory: ./backend
        run: |
          docker build -f Dockerfile -t ${{ env.IMAGE_NAME_BE }} .
          docker push ${{ env.IMAGE_NAME_BE }}

  deploy:
    needs: build-and-push
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Configure AWS credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ secrets.AWS_REGION }}

      - name: Deploy Backend
        env:
          TASK_NAME_BE: ${{ secrets.TASK_NAME_BE }}
          IMAGE_NAME_BE: ${{ env.IMAGE_NAME_BE }}
          AWS_APPLICATION_NAME: ${{ secrets.AWS_APPLICATION_NAME }}
          AWS_DEPLOYMENT_GROUP_NAME: ${{ secrets.AWS_DEPLOYMENT_GROUP_NAME }}
          REGION: ${{ secrets.AWS_REGION }}
        run: bash backend/deploy-backend.sh
```

- In this file: 
  - **name: Backend CI/CD** specifies the workflow name.
  - **on: (...)** triggers the workflow, allowing for workflow calls.
  - **env: (...)** defines environment variables for the image (currently using **ECR**, can switch to **Docker Hub**).
  - **build-and-push: (...)** is a job that builds and pushes an image to ECR.
  - **deploy: (...)** is another job that deploys the built image to ECS.
  - **run: bash backend/deploy-backend.sh** runs the deployment script.

3. Finally, access deploy-backend.sh (or deploy-frontend.sh in the frontend) to configure code for deploying to ECS.

- Access the file with:

```bash
vi backend/deploy-backend.sh
```

```
#!/bin/bash
# Retrieve the task definition from ECS
TASK_DEFINITION=$(aws ecs describe-task-definition --task-definition "$TASK_NAME_BE" --region "$REGION")

# Register a new task definition with an updated image
NEW_TASK_DEFINITION=$(echo $TASK_DEFINITION | jq --arg IMAGE "$IMAGE_NAME_BE" '.taskDefinition | .containerDefinitions[0].image = $IMAGE | del(.taskDefinitionArn) | del(.revision) | del(.status) | del(.requiresAttributes) | del(.compatibilities) | del(.registeredAt) | del(.registeredBy)')
NEW_REVISION=$(aws ecs register-task-definition --region "$REGION" --cli-input-json "$NEW_TASK_DEFINITION")
echo $NEW_REVISION | jq '.taskDefinition.revision'


# Extract the task definition ARN, container name, and container port using jq
AWS_TASK_DEFINITION_ARN=$(echo $TASK_DEFINITION | jq -r '.taskDefinition.taskDefinitionArn')
CONTAINER_NAME=$(echo $TASK_DEFINITION | jq -r '.taskDefinition.containerDefinitions[0].name')
CONTAINER_PORT=$(echo $TASK_DEFINITION | jq -r '.taskDefinition.containerDefinitions[0].portMappings[0].containerPort')

# Create the application specification (AppSpec) in JSON format
APP_SPEC=$(jq -n --arg taskDef "$AWS_TASK_DEFINITION_ARN" --arg containerName "$CONTAINER_NAME" --argjson containerPort "$CONTAINER_PORT" '{
  version: "0.0",
  Resources: [
    {
      TargetService: {
        Type: "AWS::ECS::Service",
        Properties: {
          TaskDefinition: $taskDef,
          LoadBalancerInfo: {
            ContainerName: $containerName,
            ContainerPort: $containerPort
          }
        }
      }
    }
  ]
}')

# Create the revision configuration for the deployment
REVISION=$(jq -n --arg appSpec "$APP_SPEC" '{
  revisionType: "AppSpecContent",
  appSpecContent: {
    content: $appSpec
  }
}')

# Trigger the deployment using the specified application name, deployment group, and revision
aws deploy create-deployment --region "$REGION" \
  --application-name "$AWS_APPLICATION_NAME" \
  --deployment-group-name "$AWS_DEPLOYMENT_GROUP_NAME" \
  --revision "$REVISION"
```

- Outcome:
  - ECS task definition is updated with the new image.
  - CodeDeploy triggers a deployment with the new configuration, syncing the application with the updated backend image in the current ECS service.