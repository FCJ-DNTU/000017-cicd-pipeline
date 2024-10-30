+++
title = "Check the Results"
date = 2024
weight = 4
chapter = false
pre = "<b>5.4. </b>"
+++

#### Create a tag

To apply the recent changes in the configured code, we need to create a tag, allowing GitHub Actions to automatically run. This process will deploy a new image version in the repository and automatically deploy it to ECS.

- Go back to GitHub where the code was pushed, and the secret keys were added.
- Select **Tags** to create a new tag.

![Github](/images/5-cicd-github/5.4.1.png)

- Select  **Releases**.
- Select  **Create a new release**.

![Github](/images/5-cicd-github/5.4.2.png)

- Select  **Choose a tag**.
- Enter  `v1.0.2`
- Select  **Create new tag** để tạo.

![Github](/images/5-cicd-github/5.4.3.png)

- Select **Publish release** to finish creating the tag.

![Github](/images/5-cicd-github/5.4.4.png)

#### Check the Actions Process

- Select **Actions** to view the status of workflows.
- Select the most recent workflow created.

![Github](/images/5-cicd-github/5.4.5.png)

- Check if the process encounters any errors.

![Github](/images/5-cicd-github/5.4.6.png)

![Github](/images/5-cicd-github/5.4.7.png)

#### Check Inside the AWS Console

In the AWS console, check if the CI/CD process has created the new resources.

- Check the backend images.

![Github](/images/5-cicd-github/5.4.8.png)

- Check the frontend images.

![Github](/images/5-cicd-github/5.4.9.png)

- Check the backend task definition.

![Github](/images/5-cicd-github/5.4.10.png)

- Check the frontend task definition.

![Github](/images/5-cicd-github/5.4.11.png)

- Check that the frontend service has been updated to the latest task definition.

![Github](/images/5-cicd-github/5.4.12.png)

- Check the Deployment section in CodeDeploy for the backend service.

![Github](/images/5-cicd-github/5.4.13.png)

#### Verify the Application

- Go back to the Load Balancer's DNS and check that the application reflects the code changes made in previous steps.

![Github](/images/5-cicd-github/5.4.14.png)
