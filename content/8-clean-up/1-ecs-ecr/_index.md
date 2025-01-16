+++
title = "Delete resources in ECS and ECR"
date = 2024
weight = 1
chapter = false
pre = "<b>8.1. </b>"
+++

#### Delete ECS Resources

First, you need to delete the two services, backend and frontend.
- Go to the AWS console and search for **ECS**.
- Select the **Cluster** you created and scroll down to the **Service** section.
- Select the two running services and choose **Delete service**.

![ECS](/images/Clean-up/ecs-1.png)

- Select **Force delete**.
- Enter `delete`
- Select **Delete**.

![ECS](/images/Clean-up/ecs-2.png)

- Complete the service deletion.

![ECS](/images/Clean-up/ecs-3.png)

Next, proceed to delete Task definitions.
- Go to **Task definitions** and select all revisions.
- Expand **Action** and choose **Deregister**.

![ECS](/images/Clean-up/ecs-4.png)

- Select **Deregister**.

![ECS](/images/Clean-up/ecs-5.png)

- Perform the same steps for the frontend as you did for the backend.

![ECS](/images/Clean-up/ecs-6.png)

![ECS](/images/Clean-up/ecs-7.png)

- Complete the deletion of Task definitions.

![ECS](/images/Clean-up/ecs-8.png)

Delete ECS Cluster
- Go back to the **Cluster** and select **Delete cluster**.

![ECS](/images/Clean-up/ecs-9.png)

- Enter `delete FCJ-Lab-cluster`
- Select **Delete**.

![ECS](/images/Clean-up/ecs-10.png)

- Wait a moment for the cluster deletion to complete.

![ECS](/images/Clean-up/ecs-11.png)

#### Delete ECR Resources

First, delete the Images.
- Go to the repository in **ECR**.
- Select the existing image and choose **Delete**.

![ECR](/images/Clean-up/ecr-1.png)

- Enter `delete`
- Select **Delete**.

![ECR](/images/Clean-up/ecr-2.png)

- Image deletion successful.

![ECR](/images/Clean-up/ecr-3.png)

Next, delete the repository in **ECR**
- Select the repository you want to delete.
- Choose **Delete**.

![ECR](/images/Clean-up/ecr-4.png)

- Select **Delete**.
- Repository deletion successful.

![ECR](/images/Clean-up/ecr-5.png)

{{% notice note %}}
Repeat the same steps for the remaining ECR repositories.
{{% /notice %}}
