+++
title = "Create Access key and Secret key"
date = 2024
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++

#### Creating an Access Key in AWS IAM

First, log into AWS and type **IAM** in the search bar to create an access key there.

- Select **Users** if you're using a user account to complete this Workshop.
- Then, select the user account you're currently using.

![Github](/images/5-cicd-github/5.3.1.png)

- Inside your user account, click on **Security credentials**
- Scroll down to the **Access keys** section and select **Create access key**

![Github](/images/5-cicd-github/5.3.2.png)

- In the **Create access key** section, choose **Third-party service**.
- Then click **Next**

![Github](/images/5-cicd-github/5.3.3.png)

- Next, enter the tag value `access key for github action`
- Select **Create access key**

![Github](/images/5-cicd-github/5.3.4.png)

- The access key has been created. Make sure to save it in a file or another secure location for future use.

![Github](/images/5-cicd-github/5.3.5.png)

#### Creating a Secret Key in GitHub

To allow GitHub to use these values as environment variables in CI/CD, create a secret key.

- Go to the **Settings** of the repository you created in the previous section.
- Select **Secrets and variables** and **Actions** as shown in the guide.
- Click on **New repository secret** to create a new secret.

![Github](/images/5-cicd-github/5.3.6.png)

- Add the following values as shown in the image below:
  - `AWS_ACCESS_KEY_ID` Assign the access key value created in AWS.
  - `AWS_SECRET_ACCESS_KEY` Assign the secret key value created in AWS.
  - `AWS_REGION` Assign the region you’re using.
  - `AWS_ACCOUNT_NUMBER` Assign your AWS account number.
  - `CI_PROJECT_BE_NAME` Assign the name of the repository on ECR for the backend.
  - `CI_PROJECT_FE_NAME` Assign the name of the repository on ECR for the frontend.
  - `CLUSTER_NAME` Assign the ECS Cluster name.
  - `TASK_NAME_BE` Assign the backend task definition name.
  - `TASK_NAME_FE` Assign the frontend task definition name.
  - `SERVICE_NAME_BE` Assign the backend service name.
  - `SERVICE_NAME_FE` Assign the frontend service name.
  - `AWS_APPLICATION_NAME` Assign the Application name in CodeDeploy for the backend.
  - `AWS_DEPLOYMENT_GROUP_NAME` Assign the Deployment group name in the Application for the backend.

![Github](/images/5-cicd-github/5.3.7.png)

{{% notice tip %}}
Since this repository uses ECR to store images, if you want to use a different storage service like Docker Hub, make sure to add the required secret keys for logging in to Docker Hub, and update the configuration file variables accordingly.
{{% /notice %}}